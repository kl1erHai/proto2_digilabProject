PROTO2 → Projekt mit Digilab

# Simon Says – Logik-Puzzle-Spiel

Ein speicherbasiertes Logikspiel, entwickelt mit einem **Raspberry Pi**, **Node-RED** und einem **Digilab** mit LEDs, Tastern, einem LCD und einer RGB-LED.

Dieses Projekt bildet das klassische **„Simon Says“**-Spiel nach, bei dem eine Lichtsequenz angezeigt wird und der Spieler diese durch das Drücken der Tasten in der richtigen Reihenfolge wiederholen muss. Mit jedem Erfolg wird die Sequenz länger und schwieriger!

---

## 1. Funktionen

- Visuelle folge von lichten mit LEDs
- Benutzer-Eingabe über Taster
- LCD zeigt Nachrichten und Level-Informationen an
- RGB-LED für Rückmeldung (grün = korrekt, rot = falsch)
- Spiellogik wird in Node-RED umgesetzt
- Node-RED-Dashboard zur Steuerung und Anzeige des Spielstatus

---

## 2. Benötigte Hardware

- Raspberry Pi  
- Digilab mit:
  - 4 Taster
  - 4 LEDs
  - 1 RGB-LED
  - LCD-Display
- Jumperkabel & Widerstände

---

## 3. Verdrahtung

| Komponente | Raspberry Pi GPIO (Beispiel) |
|------------|-------------------------------|
| Taster 1   | GPIO 5                        |
| Taster 2   | GPIO 6                        |
| Taster 3   | GPIO 13                       |
| Taster 4   | GPIO 19                       |
| LED 1      | GPIO 17                       |
| LED 2      | GPIO 18                       |
| LED 3      | GPIO 27                       |
| LED 4      | GPIO 22                       |
| RGB-LED    | GPIO 20 (R), 21 (G), 26 (B)   |
| LCD (I²C)  | SDA/SCL                       |
| GND        | Gemeinsame Masse              |

---

## 4. Spielablauf

1. Spielstart über einen Button im Node-RED-Dashboard oder einen physischen Taster.
2. Eine zufällige LED blinkt – das ist der erste Schritt.
3. Der Spieler muss den entsprechenden Taster drücken.
4. Wenn korrekt:
   - Eine weitere LED wird zur Sequenz hinzugefügt.
   - Das LCD zeigt das neue Level an.
5. Wenn falsch:
   - Die RGB-LED blinkt rot.
   - Das LCD zeigt „Falsch! Versuche es erneut.“

---

## 5. Node-RED Dashboard

- **Spiel starten**-Button
- Anzeige des **aktuellen Levels**
- Statusmeldung (z. B. „Richtig!“, „Falsch!“)
- (Optional) Punktediagramm und Highscore-Tracker


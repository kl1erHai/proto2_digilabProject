PROTO2 → Projekt mit Digilab

# Simon Says – Logik-Puzzle-Spiel

Ein speicherbasiertes Logikspiel, entwickelt mit einem **Raspberry Pi**, **Node-RED** und einem **Digilab** mit LEDs, Tastern, einem LCD und einer RGB-LED.

Dieses Projekt bildet das klassische **„Simon Says“**-Spiel nach, bei dem eine Lichtsequenz angezeigt wird und der Spieler diese durch das Drücken der Tasten in der richtigen Reihenfolge wiederholen muss. Mit jedem Erfolg wird die Sequenz länger und schwieriger!

---

## 1. Funktionen

- Visuelle folge von lichten mit LEDs
- Benutzer-Eingabe über Taster
- LCD zeigt Nachrichten und Level-Informationen an
- RGB-LED für Rückmeldung
    - 🟩 grün -> korrekt
    - 🟥 rot  -> falsch
- Spiellogik wird in Node-RED umgesetzt
- Node-RED-Dashboard zur Steuerung und Anzeige des Spielstatus

---

## 2. Benötigte Hardware

- Raspberry Pi  
- Digilab mit:
  - 4 Taster
  - 4 LEDs
  - 4 RGB-LED
  - LCD-Display
- Jumperkabel

---

## 3. Verdrahtung

| Komponente | Raspberry Pi GPIO             |
|------------|-------------------------------|
| Taster S5  | GPIO 16                       |
| Taster S6  | GPIO 19                       |
| Taster S7  | GPIO 20                       |
| Taster S8  | GPIO 21                       |
| LED 8      | GPIO 12                       |
| LED 7      | GPIO 13                       |
| LED 6      | GPIO 14                       |
| LED 5      | GPIO 15                       |
| RGB-LED    |
| LCD        |
| GND        | 

---

## 4. Spielablauf

1. Spielstart über einen Button im Node-RED-Dashboard oder einen physischen Taster -> Beispiel: S1.
2. Eine zufällige LED blinkt – das ist der erste Schritt. LED 8 - 5.
3. Der Spieler muss den entsprechenden Taster drücken. S5 - 8.
4. Wenn korrekt:
   - Eine weitere LED wird zur der Folge hinzugefügt.
   - Das LCD zeigt das neue Level an. Level 1 - 4
5. Wenn falsch:
   - Die RGB-LED blinkt rot.
   - Das LCD zeigt „Falsch! Versuche es erneut.“
6. Spiel muss neu gestartet werden auf dem Dashboard.

---

## 5. Node-RED Dashboard

- **Spiel starten**-Button
- Anzeige des **aktuellen Levels**
- Statusmeldung (z. B. „Richtig!“, „Falsch!“)
- (Optional) Punktediagramm und Highscore-Tracker


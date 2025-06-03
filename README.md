PROTO2 → Projekt mit Digilab

# Simon Says – Logik-Puzzle-Spiel

Ein speicherbasiertes Logikspiel, entwickelt mit einem **Raspberry Pi**, **Node-RED** und einem **Digilab** mit LEDs, Tastern, einem LCD und einer RGB-LED.

Dieses Projekt bildet das klassische **„Simon Says“**-Spiel nach, bei dem eine Folge von Lichtern angezeigt wird und der Spieler diese durch das Drücken der Tasten in der richtigen Reihenfolge wiederholen muss. Mit jedem Erfolg wird die Folge länger und schwieriger.

---

## 1. Funktionen

- Eine Folge von Lichten mit LEDs wird angezeigt.
- Benutzer-Eingabe über Tasten
- LCD zeigt Nachrichten und Level-Informationen an
- RGB-LED für Rückmeldung
    - 🟩 grün -> korrekt
    - 🟥 rot  -> falsch
- Spiellogik wird in Node-RED umgesetzt
- Node-RED-Dashboard zur Steuerung und Anzeige des Spielstatus (Start-Knopf, Level-Informationen)

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
| RGB-LED    | GPIO 18                       |
| LCD        |                               |
| GND        |                               |

---

## 4. Spielablauf

1. Das Spiel wird über einen Button im Node-RED-Dashboard gestartet.
2. Eine zufällige Folge von LEDs blinkt. Lavel 1 -> 2 LEDs, Level 2 -> 3 LEDs, usw.
3. Der Spieler muss den entsprechenden Knopf drücken von S5 bis S8. Die Knöpfe von S5, S6, S7, S8 endsprechen den LEDs LD8, LD7, LD6, LD5.  
4. Wenn die Knopf-Folge korrekt ist :
   - Die RGB-LEDs blinken grün.
   - Im Node-Red-Dashboard wird der neue Level angezeigt und der Spieler soll auf _Nächster Level_ klicken.
   - Im neuen Level wird eine weitere LED zur der Folge hinzugefügt.
   - Das LCD zeigt das neue Level an. Level 1 - 5.
6. Wenn die Knopf-Folge falsch ist:
   - Die RGB-LEDs blinken rot.
   - Das LCD zeigt „Falsch! Versuche es erneut.“
   - Im Node-Red-Dashboard muss der Spieler den Level neustarten, er soll auf _Erneut Versuchen_ klicken.
7. Das Spiel endet sobald der Spieler das Level 5 korrekt abgeschlossen hat.

---

## 5. Node-RED Dashboard

- **Spiel starten** - Button
- Anzeige des **aktuellen Levels**
- Statusmeldung (z. B. „Richtig!“ oder „Falsch!“)
- **Neuer Level** oder **Erneut Versuchen** - Buttons
- (Optional) Punktediagramm und Highscore-Tracker


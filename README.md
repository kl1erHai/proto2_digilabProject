PROTO2 → Projekt mit Digilab

# Simon Says – Logik-Puzzle-Spiel

Ein speicherbasiertes Logikspiel, entwickelt mit einem **Raspberry Pi**, **Node-RED** und einem **Digilab** mit LEDs und Tastern.

Dieses Projekt bildet das klassische **„Simon Says“**-Spiel nach, bei dem eine Folge von Lichtern angezeigt wird und der Spieler diese durch das Drücken der Tasten in der richtigen Reihenfolge wiederholen muss. Mit jedem Erfolg wird die Folge länger und schwieriger.

---

## 1. Funktionen

- Eine Folge von Lichten mit LEDs wird angezeigt.
- Benutzer-Eingabe über Tasten.
- Spiellogik wird in Node-RED umgesetzt.
- Node-RED-Dashboard zur Steuerung und Anzeige des Spielstatus (Start-Knopf).

---

## 2. Benötigte Hardware

- Raspberry Pi  
- Digilab mit:
  - 4 Taster
  - 4 LEDs
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

---

## 4. Spielablauf

1. Das Spiel wird über einen Button im Node-RED-Dashboard gestartet.
2. Eine zufällige Folge von LEDs blinkt.
3. Der Spieler muss den entsprechenden Knopf drücken von S5 bis S8. Die Knöpfe von S5, S6, S7, S8 endsprechen den LEDs LD8, LD7, LD6, LD5.  
4. Wenn die Knopf-Folge korrekt ist :
   - Wird im Dashboard **Richtig** angezeigt.
   - Der Spieler kann das Spiel neustarten.
6. Wenn die Knopf-Folge falsch ist:
   - Wird im Dashboard **Falsch** angezeigt.
7. Man hat keine Lavel in dem Spiel 

---

## 5. Node-RED Dashboard

- Eine Erklärung vom Spiel.
- **Spiel starten** - Button
- Statusmeldung (z. B. „Richtig!“ oder „Falsch!“)


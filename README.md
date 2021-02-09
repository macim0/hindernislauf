# Hindernislauf Einführung
## ~avatar avatar @unplugged

Dies ist eine Einführung in das Programmieren von Spielen mit dem @boardname@. 





## ~ @unplugged
Es soll ein Hindernislauf programmiert werden.
Ziel des Spieles: Sammle möglichst viele Punkte indem du mit den Tasten A und B den Hindernissen ausweichst, welche vom oberen Bildschirmrand nach unten bewegt werden.
![Hindernislauf](https://github.com/r00b1nh00d/Spiele_Programmieren_Lernen_Hindernislauf/blob/master/HindernislaufGIF.gif?raw=true)

## ~ @unplugged
In dieser Einführung soll erstmal nur die Spielfigur erstellt werden und in das Thema der Sprites aus dem Bereich  ``||game:Spiele||`` eingeführt werden.

## Schritt 1: Erstelle eine Spielfigur
Als erstes erstellen wir uns eine ``||Variables: Variable||`` namens ``||Variables: Spielfigur||``. Diese kommt in den Block ``||basic: Beim Start|``.
```blocks
let Spielfigur: game.LedSprite = 0

```

## Schritt 2: Einen Sprite auf die Variable speichern
Im Bereich ``||game: Spiel||`` wird mit den sogenannten Sprites gearbeitet. Diese Sprites sind wie Spielsteine oder Spielfiguren
Sie besitzen eine Position (eingeteilt in X von links nach recht und Y von oben nach unten), eine Blickrichtung, eine Helligkeit und sie können blinken.  <br>
Nimm nun aus dem Bereich ``||game: Spiel||`` den Block ``||game: erzeuge Sprite an Position x y ||``. Dieser wird in den Block ``||Variables: Setze Variable auf||`` geschoben.
Jetzt sollte im Simulator eine LED in der Mitte des Calliope Displays leuchten, eben an der Position x=2 (ganz links ist 0 und ganz rechts ist 4) und y=2 (ganz oben ist 0 und ganz unten ist 4). Ändere nun den Y-Wert auf 4 damit die Spielfigur am unteren Bildschirmrand erscheint.

```blocks 
let Spielfigur = game.createSprite(2, 4)
```

## Schritt 3: Bewegen der Spielfigur
Nun wollen wir die Spielfigur am unteren Bildschrimrand bewegen. 
Dazu benötigst du aus dem Bereich ``||Input: Eingabe||`` den Block ``||Input: Wenn Knopf A gedrückt||``, in diesen kannst du den Block ``||game: Sprite ändere x um 1 ||`` hineinschieben. <br>
Wird nun der Knopf A gedrückt sollte sich deine Spielfigur um eins nach rechts bewegen. Ändere die Zahl nun auf -1, somit bewegt sich die Spielfigur nach links.
Baue dies mit Knopf B so nach, dass sich die Fürug nach rechts bewegt. <br>
```blocks


input.onButtonPressed(Button.A, function () {
    Spielfigur.change(LedSpriteProperty.X, -1)
})

input.onButtonPressed(Button.B, function () {
    Spielfigur.change(LedSpriteProperty.X, 1)
})

let Spielfigur = game.createSprite(2, 4)
```

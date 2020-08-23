# Schere, Stein, Papier
 
## Introduction @unplugged 
![DThoch2 Logo](Bilder-und-Gifs/schere-stein-papier/Logo-DThoch2-standard.png)
 
## Step 2 wenn geschüttelt Block platzieren 
Platzieren Sie zuerst einen ``||input:wenn geschüttelt||`` Block. Ihr micro:bit Programm startet also sobald der micro:bit geschüttelt wird. 
 
```blocks
input.onGesture(Gesture.Shake, function () {
})
```
 
## Step 3  Variable hand definieren und platzieren
Definieren Sie nun eine neue Variable mit dem Namen ``||variables:hand||``.
Platzieren Sie den Block ``||variables:setze hand auf 0||`` innerhalb des ``||input:wenn geschüttelt||`` Blocks.    
       
```blocks
let hand = 0
input.onGesture(Gesture.Shake, function () {
    hand = 0
})
```
![Definition der Variable hand und Platzierung](Bilder-und-Gifs/schere-stein-papier/step-3.gif)
 
## Step 4 Zufallsblock platzieren
Ersetzen Sie die 0 durch den Block ``||math:wähle eine zufällige Zahl von 0 bis 10||`` aus der Rubrik ``||math:Mathematik||``.
Tragen Sie für die erste Zahl eine 1 und die zweite Zahl eine 3 ein. 
 
```blocks
let hand = 0
input.onGesture(Gesture.Shake, function () {
    hand = randint(1, 3)
})
```
In einem späteren Schritt wird jeder der möglichen Zahlen (1, 2 und 3) durch ein eigenes Bild ersetzt, dass dann mithilfe der LEDs auf dem micro:bit angezeigt wird.  
 
## Step 5 Bedingung: Zahl ist 1 (Papier)
Platzieren Sie den Block ``||logic:wenn wahr dann||`` unter dem Vorherigen.
Ersetzen Sie ``||logic:wahr||`` mit einem ``||logic:0 = 0||`` Block. Ersetzen Sie dann die erste 0 durch Ihre Variable ``||variables:hand||`` und die zweite 0 durch eine 1. 
Platzieren Sie nun darunter einen neuen Block ``||basic:zeige LEDs||`` und zeichnen Sie ein Rechteck. Diese Rechteck symbolisiert das Papier.       
 
```blocks
let hand = 0
input.onGesture(Gesture.Shake, function () {
    hand = randint(1, 3)
    if (hand == 1) {
        basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    }
})
```
![Bedingung wenn hand gleich 1 zeige Papier](Bilder-und-Gifs/schere-stein-papier/step-5.gif)
 
## Step 6 Schütteltest
Klicken Sie nun auf den SHAKE-Button im Simulator. Wenn Sie es oft genug versuchen, sollte irgendwann das Papier angezeigt werden.
![SHAKE betätigen](Bilder-und-Gifs/schere-stein-papier/step-6.gif)
 
## Step 7 zweite Bedingung einfügen
Klicken Sie nun auf das ``||logic:Plus||`` am Ende des ``||logic:wenn wahr dann||`` Blocks,
um einen ``||logic:ansonsten||`` Abschnitt zu erzeugen.  
 
```blocks
let hand = 0
input.onGesture(Gesture.Shake, function () {
    hand = randint(1, 3)
    if (hand == 1) {
        basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    } else {
        
    }
})
```
![Plus anklicken](Bilder-und-Gifs/schere-stein-papier/step-7.gif)
 
## Step 8 zweite Bedingung einfügen
Fügen Sie nun einen ``||basic:zeige LEDs||`` Block in den ``||logic:ansonsten||`` Abschnitt ein und zeichnen Sie eine Schere.  
 
```blocks
let hand = 0
input.onGesture(Gesture.Shake, function () {
    hand = randint(1, 3)
    if (hand == 1) {
        basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    } else {
        basic.showLeds(`
            # # . . #
            # # . # .
            . . # . .
            # # . # .
            # # . . #
            `)
    }
})
```
 
## Step 9 Dritte Bedingung hand==2 einfügen
Klicken Sie nun erneut auf das ``||logic:Plus||``, um einen ``||logic:sonst wenn dann||`` Abschnitt zu generien. 
Fügen Sie nun den Ausdruck ``||logic:hand = 2||`` in den leeren Bedingungsblock ein. Da die Variable ``||variables:hand||`` nur die Werte 1, 2 oder 3 annehmen kann deckt der Code nun alle Möglichkeiten ab. 
 
```blocks
let hand = 0
input.onGesture(Gesture.Shake, function () {
    hand = randint(1, 3)
    if (hand == 1) {
        basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    } else if (hand == 2) {
        
    } else {
        basic.showLeds(`
            # # . . #
            # # . # .
            . . # . .
            # # . # .
            # # . . #
            `)
    }
})
```
 
## Step 10 Stein einfügen
Platzieren Sie nun einen ``||basic:zeige LEDs||`` Block im zuvor angelegten Abschnitt und zeichnen Sie einen Stein.
 
```blocks
let hand = 0
input.onGesture(Gesture.Shake, function () {
    hand = randint(1, 3)
    if (hand == 1) {
        basic.showLeds(`
            # # # # #
            # . . . #
            # . . . #
            # . . . #
            # # # # #
            `)
    } else if (hand == 2) {
        basic.showLeds(`
            . . . . .
            . # # # .
            . # # # .
            . # # # .
            . . . . .
            `)
    } else {
        basic.showLeds(`
            # # . . #
            # # . # .
            . . # . .
            # # . # .
            # # . . #
            `)
    }
})
```
 
## Step 11 Schütteltest
Klicken Sie nun mehrfach auf den Shake-Knopf und überprüfen Sie ob jedes Bild irgendwann angezeigt wird. 
 
 
## Step 12 Herunterladen
Wenn Sie einen micro:bit angeschlossen haben, klicken Sie auf Herunterladen, um den Code zu übertragen.
Alternativ können Sie Ihr Programm auch am virtuellen micro:bit testen. 

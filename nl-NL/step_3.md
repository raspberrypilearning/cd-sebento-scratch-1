## Toevoegen & verwijdercode

Geweldig! Je hebt je eerste Scratch programma geschreven. Tijd om wat meer te leren over hoe je code in en uit Scratch kunt krijgen! Scratch code bestaat uit **blokken** die je samen klikt, zoals deze:

![](images/code1.png)

Je vind alle blokken in het gedeelte van **codeblokkenpalet**, waar ze zijn onderverdeeld in verschillende categorieën.

--- collapse ---
---
title: Gebruik blokken uit de verschillende categorieën
---

Klik op een categorienaam om de blokken in die categorie te zien. Hier is de **Beweging** categorie geselecteerd.

![](images/code2a.png)

Alle blokken in de geselecteerde categorie worden in een lijst weergegeven. Kies het blok dat je wilt, klik er dan op, houdt de muisknop ingedrukt en sleep het naar het **huidige sprite paneel** en laat los.

Zodra het blok zich in het **huidige sprite paneel** bevind, kun je het verplaatsen en verbinden met andere blokken.

![](images/code2b.png)

--- /collapse ---

Als je wilt zien wat een blok doet, kun je erop dubbelklikken om het uit te laten voeren! Dubbelklik op een aantal blokken om te zien wat ze doen.

--- collapse ---
---
title: De code uitvoeren
---

Normaal gesproken wil je dat je blokken automatisch worden uitgevoerd wanneer er iets specifieks gebeurt. Dit is de reden waarom de meeste van je programma's beginnen met een blok uit de categorie **gebeurtenissen**. Meestal zal dit deze zijn:

```blocks3
    wanneer op de groene vlag wordt geklikt
```

De codeblokken die zijn aangesloten op dit blok worden uitgevoerd nadat op de **groene vlag** is geklikt.

Codeblokken lopen van boven naar beneden, dus de volgorde waarin je je code bij elkaar klikt. In this example, the sprite will `say`{:class="block3looks"} `Hello!`{:class="block3looks"} before it will `play`{:class="block3sound"} the `meow`{:class="block3sound"} sound.


```blocks3
    when green flag clicked
    say [Hello!]
    play sound [meow v]
```

--- /collapse ---

Removing or deleting code blocks you don’t want in your program is easy! Just drag them back into the code blocks palette.

**Be careful:** when you drag a block into the code blocks palette, all the blocks connected to the block you drag will also be deleted, so make sure to separate code blocks you want to keep from those you want to remove. If you delete some code blocks by accident and want to get them back, you can right-click and then click on the **undo** option to get everything back.

![](images/code6.png)

--- task ---

Try adding, deleting, and undeleting some code blocks!

--- /task ---

### Alles bij elkaar brengen

Now you know how to move code around and make things happen, time to try a simple program: making the Scratch Cat walk in a circle.

--- task ---

Make sure you have the cat selected in the sprite list and then drag the following blocks together. You’ll find them in the **Events** and **Motion** lists.

```blocks3
+    when green flag clicked
+    move [10] steps
```

--- /task ---

--- task ---

Then, click on the green flag above the **Stage** a few times.

![](images/code7.png)

--- /task ---

Note: If you click too many times and the cat walks away, you can drag it back!

You should see the cat walking in a straight line...not exactly what you want, right?

--- task ---

Snap a turn block to the end to make it walk in a circle. It’s in the **Motion** list too.

```blocks3
    when green flag clicked
    move [10] steps
+    turn cw (15) degrees
```

--- /task ---

Try clicking the green flag a few more times to see the cat turn in a circle.

--- collapse ---
---
title: Hoe werkt draaien?
---

This block makes the cat turn 15 degrees of the full 360 degrees that make up a circle. You can change that number, or the number of steps, by clicking on the number and typing in a new value.

![](images/code9.png)

--- /collapse ---

--- task ---

Now save your work!

--- /task ---


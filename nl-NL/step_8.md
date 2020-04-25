## Laten we wat muggen vangen!

De papegaai beweegt, de mug vliegt, maar ze werken niet samen: als de mug recht in de bek van de papegaai vliegt, gebeurt er niets. Hoog tijd om dat te veranderen!

Eerst moet je weten of de mug de papegaai raakt. Hiervoor heb je een **besturen** blok en een **waarnemen** blok nodig.

--- task ---

Voeg een `als...dan`{:class="block3control"} **besturen** blok in de `herhaal`{:class="block3control"} lus toe bij de mug, onder het `keer om aan de rand`{:class="block3motion"} blok.

--- /task ---

--- task ---

Sleep het `raak ik...`{:class="block3sensing"} blok naar de ruimte bovenaan het `als...dan`{:class="block3control"} blok en klik op het driehoekje voor Parrot. Als je het niet hebt gewijzigd, is het 'Sprite1'.

```blocks3
    keer om aan de rand
+ als <raak ik [Sprite1 v]> dan
    einde
```

--- /task ---

--- collapse ---
---
title: Hoe werkt het?
---

Het `als...dan`{:class="block3control"} **besturen** blok moet een `Waar/Niet waar` waarde krijgen.

**Waarnemen** blokken verzamelen informatie, zoals waar de sprite is, wat het aanraakt, etc. Je gebruikt het blok

```blocks3
    < raak ik [Sprite1 v]>
```

Aan de puntige uiteinden van dit blok kun je zien dat het je de `Waar/Niet waar` waarde geeft die het `als...dan`{:class="block3control"} blok nodig heeft.

--- /collapse ---

Natuurlijk heb je zojuist een `als...dan`{:class="block3control"} blok toegevoegd zonder 'dan'.

Je kunt de mug laten verdwijnen, alsof de papegaai hem heeft opgegeten, door het blok `verdwijn`{:class="block3looks"} te gebruiken.

--- task ---

Zoek het blok `verdwijn`{:class="block3looks"} blok in de lijst **Uiterlijken** en plaats dit in `als...dan`{:class="block3control"}.

```blocks3
    als <raak ik [Sprite1 v]> dan
+ verdwijn
einde
```

--- /task ---

Zodra de papegaai de mug vangt, verdwijnt deze voorgoed. Dat is niet geweldig.

--- task ---

Zet het `verschijn`{:class="block3looks"} blok van **Uiterlijken** aan het begin van de mugcode, zodat je het spel kunt resetten.

```blocks3
    when green flag clicked
+ verschijn
maak draaistijl [links-rechts v]
herhaal
```

--- /task ---

Beter, maar je wilt niet dat de speler het spel opnieuw moet opstarten telkens wanneer hij een enkele mug vangt!

--- task ---

Pas de code aan in `als...dan`{:class="block3control"} blok zodat het er zo uitziet:

```blocks3
    keer om aan de rand
als <raak ik [Sprite1 v]> dan
verdwijn
+ wacht (1) sec.
+ ga naar x: (willekeurig getal tussen (-240) en (240)) y: (willekeurig getal tussen (-180) en (180))
+ verschijn
einde
```

--- /task ---

--- collapse ---
---
title: Hoe werkt het?
---

Je bent hier slim: als de mug verdwenen is, wacht dan, verplaats hem en laat hem opnieuw verschijnen.

Het lijkt op veel muggen, maar het is die ene sprite die zich verplaatst!

--- /collapse ---

Dat is een spel! Maar er is nog geen manier om de score bij te houden... of om te winnen. Ook dat kun je oplossen - in de volgende stap!

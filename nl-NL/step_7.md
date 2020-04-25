## Op afstand bestuurbare mug

Oké, nu is het tijd om de mug alleen te laten vliegen. Om dit te doen, heb je een nieuw soort blok nodig: een **besturen** blok.

--- task ---

Selecteer je mug sprite en sleep een `wanneer op de groene vlag wordt geklikt`{:class="block3events"} **gebeurtenissen** blok, een `herhaal`{:class="block3control"} **besturen** blok en een `neem 10 stappen`{:class="block3motion"} **beweging** blok in het **sprite paneel**:

```blocks3
+ when green flag clicked
+ herhaal
        neem (10) stappen
    einde
```

--- /task ---


--- collapse ---
---
title: Wat doet dit nieuwe blok?
---

**Besturen** blokken laten je dingen een bepaald aantal keren doen, of onder bepaalde omstandigheden.

De mug doet alles in het `herhaal`{:class="block3control"} blok steeds opnieuw, voor altijd. Als het einde is bereikt, gaat het terug naar de bovenkant van het blok en begint het opnieuw.

--- /collapse ---

--- task ---

Klik nu op de groene vlag en kijk wat er gebeurt!

--- /task ---

Nou, die mug botste gewoon tegen de zijkant van het speelveld en hij bewoog veel te snel voor je papegaai om te vangen.

Eerst moet je het vertragen. Dat is eigenlijk vrij eenvoudig, je moet het even laten wachten nadat het 10 stappen heeft gezet. Er is een **besturen** blok dat je kan helpen:

```blocks3
    wacht (1) sec.
```

--- task ---

Klik het `wacht sec.`{:class="block3control"} blok in je code en verander het nummer in `0.5`, als volgt:


```blocks3
    when green flag clicked
herhaal
        neem (10) stappen
+ wacht (0.5) sec.
    einde
```

--- /task ---

--- collapse ---
---
title: Aanpassingen maken
---

Het getal dat je instelt in het blok `wacht sec.`{:class="block3control"} geeft aan hoeveel **seconden** je wilt dat de mug wacht. `0.5` is een halve seconde.

Je kunt verschillende waarden testen om te zien welke de beste is voor de game. Vergeet niet dat je ook het aantal stappen kunt wijzigen!

--- /collapse ---

De mug beweegt nu, maar je wilt ook dat hij aan de rand omkeert. Nogmaals, er is een **beweging** blok hiervoor!

--- task ---

Zoek het `keer om aan de rand`{:class="block3motion"} blok en voeg dit toe na het `wacht sec.`{:class="block3control"} blok.

--- /task ---

--- collapse ---
---
title: Wat doet dit nieuwe blok?
---

Het blok `keer om aan de rand`{:class="block3motion"} controleert of de sprite de rand raakt en, als dit het geval is, naar links, rechts, omhoog of omlaag draait, al naar gelang.

--- /collapse ---

Dit leidt natuurlijk tot een omgekeerde mug, dus je hebt weer een `maak draaistijl`{:class="block3motion"} blok nodig.

--- task ---

Werk je code bij om de draaistijl van de mug in te stellen op `links-rechts`{:class="block3motion"}:

```blocks3
    when green flag clicked
+ maak draaistijl [links-rechts v]
herhaal
neem (10) stappen
wacht (0.5) sec.
keer om aan de rand
einde
```

--- /task ---

De mug beweegt nu heen en weer, maar alleen in een rechte lijn - een beetje te gemakkelijk voor de speler om met de papegaai te vangen! Je moet de mug minder voorspelbaar maken.

Je weet al uit een vorige stap hoe je een sprite kunt laten draaien, dus begin daar!

--- task ---

Voeg een draai toe aan de vliegende mug en klik op de groene vlag.

```blocks3
    when green flag clicked
maak draaistijl [links-rechts v]
herhaal
neem (10) stappen
+ draai (10) graden naar rechts
wacht (0.5) sec.
keer om aan de rand
einde
```

--- /task ---

Het is beter, maar het is nog erg voorspelbaar. Het moet meer willekeurig zijn. Gelukkig kan Scratch willekeurig voor je doen! Je hebt gewoon een nieuw soort blok nodig, een **functies** blok genoemd.

--- collapse ---
---
title: Wat is een functie?
---

**Functies** nemen een of meer waarden in (zoals getallen, tekst, waar niet waar) en geven een enkele waarde terug. Je kunt het soort waarde zien dat het teruggeeft door de vorm van het blok: ronde uiteinden geven cijfers of tekst, puntige uiteinden geven waar/onwaar.

```blocks3
    (() + ())

(voeg [hallo ] en [wereld] samen)

<[] = []>
```

--- /collapse ---

--- task ---

Zoek het `willekeurig getal tussen`{:class="block3operators"} **functie** blok en sluit het aan op het `draai graden`{:class="block3motion"} **beweging** blok door erop te klikken en naar het veld te slepen waar je het aantal graden instelt.

```blocks3
    when green flag clicked
maak draaistijl [links-rechts v]
herhaal
neem (10) stappen
+ draai (willekeurig getal tussen (1) en (10)) graden naar rechts
wacht (0.5) sec.
keer om aan de rand
einde
```

--- /task ---

**Opmerking**: je kunt de minimum- en maximumaantallen die het kiest zelf bepalen, maar de standaardwaarden (`1` en `10`) zijn redelijk goed voor deze game, dus je kunt ze gewoon zo laten.

--- task ---

Klik op de groene vlag om de code uit te voeren!

--- /task ---

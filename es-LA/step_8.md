## ¡Atrapemos algunos mosquitos!

El loro se mueve, el mosquito vuela, pero no interactúan: si el mosquito vuela directo al pico del loro, no pasa nada. ¡Es hora de cambiar eso!

Primero, necesita saber si el mosquito está tocando al loro. Para esto, necesitarás un bloque **Control** y un bloque **Sensor**.

--- task ---

Agrega el bloque **Control** `si...entonces`{:class="block3control"} dentro del bucle `por siempre`{:class="block3control"} del objeto mosquito, debajo del bloque `si toca un borde, rebotar`{:class="block3motion"}.

--- /task ---

--- task ---

Arrastra el bloque `tocando...`{:class="block3sensing"} al espacio en la parte superior del bloque `si...entonces`{:class="block3control"} y haz clic en el pequeño triángulo para seleccionar el nombre del objeto loro. Si no lo has cambiado, será 'Sprite1'.

```blocks3
    if on edge, bounce
+    if <touching [Sprite1 v] ?> then
    end
```

--- /task ---

--- collapse ---
---
title: ¿Cómo funciona?
---

El bloque **Control** `si...entonces`{:class="block3control"} debe recibir un valor `Verdadero/Falso`.

Los bloques **Sensores** recopilan información, como dónde está el objeto, qué está tocando, etc. Estás usando el bloque

```blocks3
    <touching [Sprite1 v] ?>
```

Por los bordes puntiagudos de este bloque, puedes saber que va a darte el valor `Verdadero/Falso` que el bloque `si...entonces`{:class="block3control"} necesita.

--- /collapse ---

Por supuesto, acabas de añadir un bloque `si...entonces`{:class="block3control"} sin añadir nada para la parte 'entonces'.

Puedes hacer que el mosquito desaparezca, como si el loro se lo comiera, usando el bloque `esconder`{:class="block3looks"}.

--- task ---

Encuentra el bloque `esconder`{:class="block3looks"} en la lista **Apariencia**, y ponlo dentro del bloque `si...entonces`{:class="block3control"}, así.

```blocks3
    if <touching [Sprite1 v] ?> then
+        hide
    end
```

--- /task ---

Ahora, una vez que el loro atrapa al mosquito, desaparece para siempre. Esto no está bien.

--- task ---

Arrastra el bloque `mostrar`{:class="block3looks"} desde la lista **Apariecia** al inicio del código del mosquito, para que puedas reiniciar el juego.

```blocks3
    when green flag clicked
+    show
    set rotation style [left-right v]
    forever
```

--- /task ---

Mejor, ¡pero no querrás que el jugador tenga que reiniciar el juego cada vez que atrapa un solo mosquito!

--- task ---

Actualiza el código dentro de tu bloque `si...entonces`{:class="block3control"} para que quede así:

```blocks3
    if on edge, bounce
    if <touching [Sprite1 v] ?> then
        hide
+        wait (1) secs
+        go to x: (pick random (-240) to (240)) y: (pick random (-180) to (180))
+        show
    end
```

--- /task ---

--- collapse ---
---
title: ¿Cómo funciona?
---

Aquí estás siendo inteligente: cuando el mosquito está oculto, espera, muévelo, y luego muéstralo de nuevo.

Parece que hay muchos mosquitos, ¡pero es un solo objeto moviéndose!

--- /collapse ---

¡Eso es un juego! Pero todavía no hay forma de mantener la puntuación...o de ganar. También puedes arreglar eso: ¡en el paso siguiente!

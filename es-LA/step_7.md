## Mosquito a control remoto

Bien, ahora es el momento de hacer que el mosquito vuele solo. Para ello, necesitarás un nuevo tipo de bloque: un bloque **Control**.

--- task ---

Selecciona tu mosquito y arrastra un **bloque de evento** `al presionar bandera verde`{:class="block3events"}, un bloque `para siempre`{:class="block3control"} **control** 7 y un movimiento de ``{: class = "block3motion"} **movimiento** bloque en el panel</strong> **sprites 13 así:

```blocks3
+    when green flag clicked
+    forever
        move (10) steps
    end
```

--- /task ---


--- collapse ---
---
title: ¿Qué hace el nuevo bloque?
---

Los bloques de **Control** hacen que tu programa haga cosas un cierto número de veces, o bajo ciertas condiciones.

El mosquito hace lo que esté en el bloque `para siempre`{:class="block3control"} una y otra vez, para siempre. Una vez que ha llegado al final, vuelve al bloque superior y comienza de nuevo.

--- /collapse ---

--- task ---

Ahora haz clic en la bandera verde y ¡observa lo que sucede!

--- /task ---

Bueno, ese mosquito se estrelló contra el costado del escenario y se movía demasiado rápido para que tu loro lo atrapara.

Primero, necesitas ralentizarlo. En realidad es bastante fácil, solo necesitas esperar un poco después de que se mueva esos 10 pasos. Hay un bloque de **control** que te ayudará aquí:

```blocks3
    esperar (1) segundos
```

--- task ---

Encaja el bloque `esperar`{:class="block3control"} en tu código, y cambia el número a `0.5`, así:


```blocks3
    when green flag clicked
    forever
        move (10) steps
+        wait (0.5) secs
    end
```

--- /task ---

--- collapse ---
---
title: Haciendo ajustes
---

El número que has establecido en el bloque `esperar`{:class="block3control"} dice cuántos **segundos** quieres que el mosquito espere. `0.5` es la mitad de un segundo.

Puedes probar diferentes valores para ver cuál es el mejor para el juego. ¡Recuerda que también puedes cambiar el número de pasos!

--- /collapse ---

El mosquito se mueve ahora, pero también necesitas que rebote en el borde. ¡Una vez más, hay un bloque **Movimiento** para esto!

--- task ---

Encuentra el bloque `si toca un borde, rebotar`{:class="block3motion"} y agrégalo después del bloque `esperar`{:class="block3control"}.

--- /task ---

--- collapse ---
---
title: ¿Qué hace el nuevo bloque?
---

El bloque `si toca un borde, rebotar`{:class="block3motion"} comprueba si el objeto está tocando el borde del Escenario y, si es así, lo hace girar a la izquierda, derecha, arriba o abajo como corresponda.

--- /collapse ---

Por supuesto, esto conducirá a un mosquito al revés, así que necesitas un bloque de `fijar estilo de rotación`{:class="block3motion"} de nuevo.

--- task ---

Actualiza tu código para establecer el estilo de rotación del mosquito a `izquierda-derecha`{:class="block3motion"}:

```blocks3
    when green flag clicked
+    set rotation style [left-right v]
    forever
        move (10) steps
        wait (0.5) secs
        if on edge, bounce
    end
```

--- /task ---

El mosquito se mueve hacia atrás y hacia adelante ahora, pero solo en línea recta, ¡es demasiado fácil que el jugador lo atrape con el loro! Necesitas hacer que el mosquito sea menos predecible.

Ya sabes por un paso anterior cómo hacer que un objeto gire, así que empieza por aquí!

--- task ---

Agrega un giro en el vuelo del mosquito y haz clic en la bandera verde.

```blocks3
    when green flag clicked
    set rotation style [left-right v]
    forever
        move (10) steps
+        turn cw (10) degrees
        wait (0.5) secs
        if on edge, bounce
    end
```

--- /task ---

Es mejor, pero todavía es demasiado predecible. Necesita ser más aleatorio. Afortunadamente, ¡Scratch puede aleatorizar por ti! Sólo necesitarás un nuevo tipo de bloque, llamado bloque **operador**.

--- collapse ---
---
title: ¿Qué es un operador?
---

Los **Operadores** toman uno o más valores (como números, texto, o Verdadero/Falso) y devuelven un valor único. Puedes saber el tipo de valor que devolverá por la forma del bloque: los extremos redondos dan números o texto, los extremos puntiagudos dan verdad/falso.

```blocks3
    (() + ())

    (unir [hola ] [mundo])

    <[] = []>
```

--- /collapse ---

--- task ---

Encuentra el bloque **operador** `número aleatorio`{:class="block3operators"}, y conéctalo al bloque **movimiento** `girar grados`{:class="block3motion"} haciendo clic en él y arrastrándolo al campo donde estableces el número de grados.

```blocks3
    when green flag clicked
    set rotation style [left-right v]
    forever 
        move (10) steps
+        turn cw (pick random (1) to (10)) degrees
        wait (0.5) secs
        if on edge, bounce
    end
```

--- /task ---

**Nota**: puedes cambiar los números mínimos y máximos, pero los valores por defecto (`1` y `10`) son bastante buenos para este juego, así que puedes dejarlos.

--- task ---

¡Ahora haz clic en la bandera verde para probar tu código!

--- /task ---

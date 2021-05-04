## Guardando la puntuación

Para llevar la puntuación, necesitarás un lugar para almacenar la puntuación, una forma de agregarla y una forma de restablecerla cuando se reinicia el juego.

--- task ---

Primero: ¡almacenarlo! Ve a la categoría de bloques **Variables** y haz clic en **Crear una variable**.

![](images/catch5.png)

Introduce `puntos` como nombre.

![](images/catch6.png)

¡Mira tu nueva variable y los bloques que tiene!

![La variable Puntos se muestra en el escenario](images/scoreVariableStage.png)

--- /task ---

--- collapse ---
---
title: ¿Qué son las variables?
---

Cuando quieres almacenar información en un programa, se usa algo llamado **variable**. Piensa en ello como una caja con una etiqueta: puedes poner algo en ella, comprobar qué hay en ella y cambiar lo que hay en ella. Encontrarás variables en **Variables**, ¡pero necesitas crearlas primero!

--- /collapse ---

Ahora necesitas actualizar la variable cada vez que el loro se come un mosquito y restablecerla cuando se reinicia el juego:

--- task ---

--- /task ---

De la sección **variables**, pon `conjunto [mi variable v] a [0]` {: class = "block3variables"} y `cambia [mi variable v] por [1]` {: class = "block3variables"} bloques. En cada uno de los bloques, haz clic en la flecha pequeña y luego elige `puntos` de la lista. Luego pon los bloques en tu programa:

--- task ---

### Código para el loro

```blocks3
    when green flag clicked
+    set [score v] to [0]
    set rotation style [left-right v]
    go to x: (0) y: (0)
```

### Código para el mosquito

```blocks3
    si <touching [Sprite1 v] ?> entonces
+ cambiar [puntos v] por [1]
        ocultar
        esperar (1) segundos
        ir a x: (número aleatorio (-240) a (240)) y: (número aleatorio (-180) a (180))
        mostrar
    final
```

--- /task ---

¡Genial! Ahora tienes puntuación y todo.

--- task ---

Finalmente, añade este código para hacer que el loro introduzca el juego:

```blocks3
    al hacer clic en bandera verde
    fijar [puntos v] a [0]
    fijar estilo de rotación [izquierda-derecha v]
    ir a x: (0) y: (0)
    decir [¡Hola! Necesito tu ayuda.] Durante (3) segundos
    di [¿Puedes ayudarme a atrapar todos los mosquitos? Usa las teclas de flecha.] durante (4) seg
    decir[Los mosquitos son insectos pequeñas que propagan enfermedades peligrosas como la malaria. durante (5) segundos
    decir [¡Por favor ayúdame a atraparlos y proteger a mis amigos!] por (3) segundos
```

--- /task ---

## Attrapons des moustiques !

Le perroquet se déplace, le moustique vole, mais ils n’interagissent pas : si le moustique atterrit dans le bec du perroquet, rien ne se passe. Il est temps de changer cela !

Premièrement, tu dois savoir si le moustique touche le perroquet. Pour cela, tu auras besoin d'un bloc **contrôle** et d'un bloc **capteurs**.

--- task ---

Ajouter le bloc `si... alors`{:class="block3control"} de **contrôle** dans la boucle `répéter indéfiniment`{:class="block3control"} sur le moustique, en dessous du bloc `rebondir si le bord est atteint`{:class="block3motion"}.

--- /task ---

--- task ---

Fais glisser le bloc `touche...`{:class="block3sensing"} dans l'espace en haut du bloc `si ... alors`{:class="block3control"}, puis clique sur le petit triangle pour sélectionner le nom du sprite du perroquet. Si tu ne l'as pas changé, ce sera « Sprite1 ».

```blocks3
    if on edge, bounce
+    if <touching [Sprite1 v] ?> then
    end
```

--- /task ---

--- collapse ---
---
title: Comment ça marche ?
---

Le bloc `si...alors`{:class="block3control"} de **contrôle** doit recevoir une valeur `Vrai/Faux`.

Les blocs **capteurs** collectent des informations, telles que l'emplacement du sprite, ce qui touche, etc. Tu utilises le bloc

```blocks3
    <touching [Sprite1 v] ?>
```

A partir de ce bloc, tu peux dire qu'il va te donner la valeur `Vrai/Faux` dont a besoin le bloc `si...alors`{:class="block3control"}.

--- /collapse ---

Bien sûr, tu viens d'ajouter un bloc `si...alors`{:class="block3control"} sans « alors ».

Tu peux faire disparaître le moustique, comme si le perroquet le mangeait, en utilisant le bloc `cacher`{:class="block3looks"}.

--- task ---

Trouve le bloc `cacher`{:class="block3looks"} dans la liste **Apparence** et mets-le à l'intérieur de `si...alors`{:class="block3control"}.

```blocks3
    if <touching [Sprite1 v] ?> then
+        hide
    end
```

--- /task ---

Maintenant une fois que le perroquet attrape le moustique, il disparaît pour de bon. C'est pas génial.

--- task ---

Place le bloc `montrer`{:class="block3looks"} d' **Apparence** au tout début du code du moustique, pour que tu puisses réinitialiser le jeu.

```blocks3
    when green flag clicked
+    show
    set rotation style [left-right v]
    forever
```

--- /task ---

C'est déjà mieux, mais tu ne veux pas que le joueur redémarre le jeu à chaque fois qu'il attrape un seul moustique !

--- task ---

Mets à jour le code dans ton bloc `si ... alors`{:class="block3control"} pour qu'il ressemble à ceci :

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
title: Comment ça marche ?
---

Tu dois être un peu malin : lorsque le moustique est caché, attends, bouge-le, puis montre-le à nouveau.

On a l'impression qu'il y a beaucoup de moustiques, mais il n'y a qu'un sprite qui se déplace !

--- /collapse ---

C'est un jeu ! Mais il n’y a encore aucun moyen de marquer des points ou de gagner. Tu peux également résoudre ce problème - à l'étape suivante !

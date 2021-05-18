## Moustique contrôlé à distance

Ok, maintenant il est temps de faire voler le moustique seul. Pour cela, tu auras besoin d'un nouveau type de bloc : un bloc **contrôle**.

--- task ---

Sélectionne ton sprite moustique et fais glisser un bloc `quand le drapeau vert est cliqué`{:class="block3events"} d'**événement**, un bloc `répéter indéfiniment`{:class="block3control"} de **contrôle** et un bloc `avancer de 10 pas`{:class="block3motion"} de **mouvement** dans le **panneau sprite** comme ceci :

```blocks3
+    when green flag clicked
+    forever
        move (10) steps
    end
```

--- /task ---


--- collapse ---
---
title: Que fait le nouveau bloc ?
---

Les blocs **contrôle** obligent ton programme à effectuer des tâches un certain nombre de fois ou dans certaines conditions.

Le moustique fait tout ce qui se trouve dans le bloc `répéter indéfiniment`{:class="block3control"} encore et encore. Une fois qu'il a atteint la fin, il retourne en haut du bloc et recommence.

--- /collapse ---

--- task ---

Maintenant, clique sur le drapeau vert et regarde ce qui se passe !

--- /task ---

Eh bien, ce moustique vient de tomber dans le côté de la scène, et il se déplaçait beaucoup trop vite pour que ton perroquet puisse l'attraper.

En premier, tu dois le ralentir. C’est en fait assez facile, il suffit d’attendre un peu de temps après avoir bougé ces 10 pas. Il y a un bloc **contrôle** qui t'aidera ici :

```blocks3
    wait (1) secs
```

--- task ---

Assemble le bloc `attendre`{:class="block3control"} dans ton code et modifie le nombre sur `0.5`, comme ceci :


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
title: Faire des ajustements
---

Le nombre que tu as défini dans le bloc `attendre`{:class="block3control"} dit combien de **secondes** tu veux que le moustique attende. `0.5` est une demi-seconde.

Tu peux tester différentes valeurs pour déterminer laquelle est la meilleure pour le jeu. N'oublie pas que tu peux également changer le nombre de pas !

--- /collapse ---

Le moustique bouge maintenant, mais tu en as aussi besoin pour rebondir sur le bord de la scène. Encore une fois, il y a un bloc **mouvement** pour cela !

--- task ---

Trouve le bloc `rebondir si le bord est atteint`{:class="block3motion"}, et ajoute-le après le bloc `attendre`{:class="block3control"}.

--- /task ---

--- collapse ---
---
title: Que fait le nouveau bloc ?
---

Le bloc `rebondir si le bord est atteint`{:class="block3motion"} vérifie si le sprite touche le bord et, si c'est le cas, il tourne à gauche, à droite, vers le haut ou vers le bas, selon le cas.

--- /collapse ---

Bien sûr, cela mènera à un moustique à l'envers. Tu as donc besoin d'un bloc `fixer le sens de rotation`{:class="block3motion"} à nouveau.

--- task ---

Mets à jour ton code pour définir le sens de rotation du moustique sur `gauche-droite`{:class="block3motion"} :

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

Le moustique se déplace maintenant en avant et en arrière, mais uniquement en ligne droite - un peu trop facile à attraper pour le joueur avec le perroquet ! Tu dois rendre le moustique moins prévisible.

Tu sais déjà, par une étape précédente, comment faire tourner un sprite alors commence par çà !

--- task ---

Ajoute un bloc tourner dans le moustique et clique sur le drapeau vert.

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

C'est mieux, mais c'est encore trop prévisible. Cela doit être plus aléatoire. Heureusement, Scratch peut ajouter du hasard pour toi ! Tu as juste besoin d'un nouveau type de bloc, appelé bloc **opérateur**.

--- collapse ---
---
title: Qu'est-ce qu'un opérateur ?
---

Les **opérateurs** prennent une ou plusieurs valeurs (comme des nombres, du texte, des valeurs vraies/fausses) et donnent une seule valeur. Tu peux indiquer le type de valeur qu'il renverra par la forme du bloc : les extrémités de l'arrondi donnent des nombres ou du texte, les extrémités pointues donnent vrai/faux.

```blocks3
    (() + ())

    (join [bonjour] [world])

    <[] = []>
```

--- /collapse ---

--- task ---

Trouve le bloc `nombre aléatoire`{:class="block3operators"} dans **opérateur** , et assemble-le dans le bloc `tourner degrés`{:class="block3motion"} dans **mouvement** en cliquant dessus et en le faisant glisser dans le champ où tu définis le nombre de degrés.

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

**Remarque** : tu peux modifier les nombres minimum et maximum qu’il choisira, mais les valeurs par défaut (`1` et `10`) sont plutôt bonnes pour ce jeu, tu peux donc les laisser.

--- task ---

Clique sur le drapeau vert pour exécuter le code !

--- /task ---

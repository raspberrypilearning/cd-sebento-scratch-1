## All the sprites

Now you have a parrot that you can move around using the arrow keys. Nice! Time to add some mosquitos for it to catch!

+ Click the **new sprite** button. Scratch doesn't have any ready-made mosquito costumes so you are going to draw one!

![](images/spritesPaintNew.png)

If your mosquito is a bit big compared to your parrot, you can use **grow** and **shrink** to make them both the right size. 

![](images/sprites2.png)

+ Click on **grow** or **shrink** and then click on one of the sprites to make it get bigger or smaller.

Nice! Later, you're going to add some code to make the mosquito move around on its own, without help from the player. Your player will be the parrot, trying to catch the mosquito.

--- collapse ---
---
title: What about the backwards parrot?
---

It does look a little funny to have that parrot flying backwards. Just like you’d usually turn around rather than walking backwards, the parrot would turn around rather than flying that way. Luckily for you, Scratch has a block for this!

The `point in direction`{:class="blockmotion"} block lets you pick the direction your sprite is pointing in. You can type in any number, but it comes with the four you'll need most already in there: `up`, `down`, `left` and `right`. You’ll find it in the **motion** blocks section. 

--- /collapse ---

+ Grab the `point in direction`{:class="blockmotion"} block from **motion** and snap a couple of them into your parrot’s code, like this: 

```blocks
    when [left arrow v] key pressed
    point in direction (-90)
    move (10) steps
```

```blocks
    when [right arrow v] key pressed
    point in direction (90)
    move (10) steps
```

+ Change the steps from `-10` to `10`.

If you tried moving the parrot around after you added the `point in direction`{:class="blockmotion"} blocks, you might have noticed something a little strange happening. The parrot may not be turning quite right! 

![Upside down parrot](images/spritesUpsideDown.png)

--- collapse ---
---
title: Why does it go upside down?
---

The problem here is that the parrot sprite started, as all sprites do, with the `all around` **rotation style**, and what you need it to have is the `left-right` style.

As usual, there’s a block for that and it’s in **motion**! 

--- /collapse ---

+ Look in the **motion** category for the block `set rotation style`{:class="blockmotion"}.

+ Add the block to your reset code from earlier and set the rotation style to `left-right`, like this: 

```blocks
    when green flag clicked
    set rotation style [left-right v]
    go to x: (0) y: (0)
```

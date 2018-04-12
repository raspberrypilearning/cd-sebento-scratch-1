## Flycatching!

The parrot moves, the mosquito flies, but they don’t interact: If the mosquito flies right into the parrot’s beak, nothing happens. Time to change that!

First, you need to know if the mosquito is touching the parrot. For this, you'll need a **control** block and a **sensing** block. 

+ Add the `if... then`{:class="blockcontrol"} **control** block into the `forever`{:class="blockcontrol"} loop on the mosquito, after the `if on edge bounce`{:class="blockmotion"}.

+ Drag the `touching...`{:class="blocksensing"} block into the space at the top of the `if... then`{:class="blockcontrol"} block and click the little triangle to pick the sprite name (if you haven’t changed it, it'll be Sprite1)

```blocks
    if on edge, bounce
    if <touching [Sprite1 v] ?> then
    end
```

--- collapse ---
---
title: How does it work?
---

The `if... then`{:class="blockcontrol"} **control** block needs to be given a true/false value. 

**Sensing** blocks collect information, like where the sprite is, what it’s touching, etc. You're using the block

```blocks
    <touching [Sprite1 v] ?>
```

From those pointy ends, you can tell it’s going to give you the true/false value `if... then`{:class="blockcontrol"} needs.

--- /collapse ---

Of course, you’ve just added an `if... then`{:class="blockcontrol"} with no 'then'. 

You can make the mosquito vanish, as if the parrot ate it by using the `hide`{:class="blocklooks"} block.

+ Find the `hide`{:class="blocklooks"} block in **looks** and put it inside the `if... then`{:class="blockcontrol"}. 

```blocks
    if <touching [Sprite1 v] ?> then
        hide
    end
```

Now once the parrot catches the mosquito it disappears for good. That’s not great. 

+ Put the `show`{:class="blocklooks"} block, also from **looks** in at the very start of the mosquito code, so you can reset the game. 

```blocks
    when green flag clicked
    show
    set rotation style [left-right v]
    forever
```

Better, but you don’t want the player restarting every time they catch one mosquito! 


+ Update the code inside your `if... then`{:class="blockcontrol"} block to look like this:

```blocks
    if on edge, bounce
    if <touching [Sprite1 v] ?> then
        hide
        wait (1) secs
        go to x: (pick random (-240) to (240)) y: (pick random (-180) to (180))
        show
    end
```

--- collapse ---
---
title: How does it work?
---

You are being clever here — when the mosquito is hidden, wait, move it, then show it again. 

It looks like lots of mosquito, but it’s that one sprite moving around! 

--- /collapse ---

That’s a game! There’s no way to keep score, though... or to win. You can fix that too! You'll do this on the next card.
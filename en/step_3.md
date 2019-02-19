## Adding & removing code

Great! You’ve written your first Scratch program. Time to learn a little more about getting code in and out of Scratch! Scratch code is made up of **blocks** that you snap together, such as these:

![](images/code1.png)

You will find all blocks in the **code blocks palette**,where they are broken up into different categories. 

--- collapse ---
---
title: Using blocks from the different categories
---

Clicking on a category name to see the blocks in that category. Here, the **Motion** category is selected. 

![](images/code2a.png)

All of the blocks in the selected category are shown in a list. You can pick the one you want, click on it, hold down the mouse button, and then just drag it onto the **current sprite panel** and let go. 

Once the block is in the **current sprite panel**, you can move it around and connect it to other blocks.

![](images/code2b.png)

--- /collapse --- 

If you want to see what a block does, you can double-click on it to make it run! Try double-clicking on some of the blocks to see what they do.

--- collapse ---
---
title: Running the code
---

Normally, you want your blocks to run automatically whenever something specific happens. This is why most of your programs will start with a block from the **events** category. Most often, it will be this one: 

```blocks3
    when green flag clicked
```

The code blocks connected to this block will run after the **green flag** is clicked.

Code blocks run from top to bottom, so the order in which you snap your code together in matters. In this example, the sprite will `say`{:class="block3looks"} `Hello!` before it will `play`{:class="block3sound"} the `meow` sound. 

![](images/code4.png)

--- /collapse ---

Removing or deleting code blocks you don’t want in your program is easy! Just drag them back into the code blocks palette.

**Be careful:** when you drag a block into the code blocks palette, all the blocks connected to the block you drag will also be deleted, so make sure to separate code blocks you want to keep from those you want to remove. If you delete some code blocks by accident and want to get them back, you can right-click and then click on the **undo** option to get everything back.

![](images/code6.png)

--- task ---
Try adding, deleting, and undeleting some code blocks! 
--- /task ---

### Putting it all together

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
title: How does turning work?
---

This block makes the cat turn 15 degrees of the full 360 degrees that make up a circle. You can change that number, or the number of steps, by clicking on the number and typing in a new value.

![](images/code9.png)

--- /collapse ---

--- task ---
Now save your work!
--- /task ---


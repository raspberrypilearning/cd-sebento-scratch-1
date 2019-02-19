## Keeping score

To keep score, you’ll need somewhere to store the score, a way of adding to it, and a way of resetting it when the game is restarted.

--- task ---

First: storing it! Go to the **Variables** blocks category and click **Make a Variable**.

![](images/catch5.png)

Enter `score` as the name. 

![](images/catch6.png)

Check out your new variable and the blocks for it!

![The score variable is displayed on the stage](images/scoreVariableStage.png)

--- /task ---

--- collapse ---
---
title: What are variables?
---

When you want to store information in a program, you use something called a **variable**. Think of it like a box with a label on it: you can put something in it, check what’s in it, and change what’s in it. You’ll find variables under **Variables**, but you need to create them first! 

--- /collapse ---

Now you need to update the variable whenever a mosquito is eaten, and to reset it when the game is restarted:

--- task ---

--- /task ---

From the **Variables** section, take the `set [my variable v] to [0]`{:class="block3variables"} and `change [my variable v] by [1]`{:class="block3variables"} blocks. In each of the blocks, click on the little arrow and then choose `score` from the list. Then put the blocks into your program: 

--- task ---
### Code for the parrot

```blocks3
    when green flag clicked
+    set [score v] to [0]
    set rotation style [left-right v]
    go to x: (0) y: (0)
```

### Code for the mosquito

```blocks3
    if <touching [Sprite1 v] ?> then
+        change [score v] by [1]
        hide
        wait (1) secs
        go to x: (pick random (-240) to (240)) y: (pick random (-180) to (180))
        show
    end
```
--- /task ---

Cool! Now you’ve got a score and everything. 

--- task ---
Finally, add this code to make the parrot introduce the game:

```blocks3
    when green flag clicked
    set [score v] to [0]
    set rotation style [left-right v]
    go to x: (0) y: (0)
    say [Hello! I need your help.] for (3) secs
    say [Can you help me catch of all the mosquitos? Use the arrow keys.] for (4) secs
    say [Mosquitos are small flies that spread dangerous diseases like malaria.] for (5) secs
    say [Please help me catch them and protect my friends!] for (3) secs
```
--- /task ---

---
title: Desert Race
level: Level 2
language: en-GB
stylesheet: scratch
embeds: "*.png"
note: "notes for club leaders.md"
materials: "*.sb2"
---

# Introduction { .intro}
This game is a two player game where you race a parrot and a lioness across the desert. Each player has to press a key as fast as they can to move their animal, the first one to reach the edge of the screen wins.

![screenshot](desertrace_screenshot.png)

# STEP 1: Create the scene and add the sprites { .activity}

## Activity Checklist { .check}
>>>>>>> scratch2

1. Select the Stage, and add the **Nature/desert** backdrop.
ticking off the boxes below:
2. Add a new sprite, select the **Lioness** sprite that you will find in the **Animals** folder.
3. Add another sprite, select the **Parrot** sprite that you will find in the **Animals** folder. `Shrink`{.blocklightgrey} it so that it is roughly the same size as the lioness sprite.

# STEP 2: Make the lioness and the parrot move { .activity}

We want the sprite to move when you press a key.

## Activity Checklist { .check}

1. First select the lion sprite and set it to `move (4) steps`{.blockblue} when you press the **‘L’** key.

```blocks
when [l v] key pressed
    move (4) steps
```

2. Next, select the parrot sprite and set it to `move (4) steps`{.blockblue} when you press the **‘A’** key.

```blocks
when [a v] key pressed
    move (4) steps
```

## Test Your Project { .flag}

__Click the green flag__ 
Do your lioness and parrot move across the screen when you press the ‘A’ and ‘L’ keys?

## Save your project { .save}

# STEP 3: Starting the race { .activity}

We need to have a way to start the race and to know who has won. __First we create a start button.__

## Activity Checklist { .check}

1. Add a new sprite from a file. Choose the **button3** sprite which is inside **“Things”**.
2. Edit the costume of the button sprite, add the text **‘start’** to it and click OK. Move the sprite to the middle of the stage.
3. Now add a script that shows the sprite when the project is run:

```blocks
    when FLAG clicked
    show
```
4. Now we want the button to count down from 3 and then say go and then `hide`{.blockblue} when it is clicked. Add another script like this one:

```blocks
when this sprite clicked
    say [3] for (1) secs
    say [2] for (1) secs
    say [2] for (1) secs
    say [GO!] for (1) secs
    hide
```

## Test Your Project { .flag}
__Click on the green flag.__

When you press the start button does it countdown to the start of the race before disappearing?

## Save your project { .save}

We only want the racers to move after the race has started and we want to know when the race has finished so we need a variable to hold that information.

1. Add a variable for all sprites called `racing`{.blockorange}. Untick the box next to it so it does not show on the stage.
2. Now set **racing** to be **0** when the project is first started. Change your `when flag clicked`{.blockyellow} script from before to look like this:

```blocks
when FLAG clicked
    show
    set [racing v] to (0)
```
3. Next, set the **racing** variable to be 1 when the starting countdown has finished.
4. Now we need to stop the lion and the parrot from moving unless the racing variable is set to be 1. Click on the parrot sprite. __Add a control block to the script__ that only allows the parrot to move if __racing = 1__.

```blocks

    when [a v] key pressed
    if <(racing) = [1]>
        move (4) steps
```
5. Now do the same for the lion sprite.

## Test Your Project { .flag}
__Click on the green flag.__

Does the lioness or the parrot move only after the countdown has finished?

We want to know who wins the race and reset it when it has finished so you can
race again.

## Save your project { .save}

# STEP 4: Finishing the race { .activity}

## Activity Checklist { .check}

1. Add a block to the parrot’s script that sets the **racing** variable to be 0 when the sprite touches the edge of the screen.

```blocks
when [a v] key pressed
if <(racing) = [1]>
    move (4) steps
    if <touching [edge v]?>
    set (racing) to [0]
```
2. Now we want the parrot to let us know if it wins the race. Record a new sound for the Parrot sprite that will be played when the parrot wins. Click `sounds`{.blocklightgrey} and then record the sound of the parrot winning the race!
3. Now add blocks that `play`{.blockpurple} the sound you recorded and makes the parrot say it has won:

```blocks
    when [a v] key pressed
    if <(racing) = [1]>
        move (4) steps
        if <touching [edge v]?>
            set (racing) to [0]
            play sound [recording1 v]
            say [The Parrot Wins! v] for (3) secs   
```
4. Now repeat these steps for the lioness.

## Test Your Project { .flag}
__Click on the green flag.__

Can you press the start button and race by pressing the ‘A’ and ‘L’ keys?
Do the sprites make their winning sound and say they’ve won when they reach the end of the race?

## Save your project { .save}

# STEP 5: Resetting the game { .activity}

After the race is finished we need to tell the other sprites we have won and reset the game so we can play again.

__We need the winning sprite to broadcast that it has won.__

## Activity Checklist { .check}

1. Click on the Parrot sprite.
Add a block that broadcasts a **"finished”** message after the sprite says it has won.

```blocks
when [a v] key pressed
if <(racing) = [1]>
    move (4) steps
    if <touching [edge v]?>
        set (racing) to [0]
        play sound [recording1 v]
        say [The Parrot Wins! v] for (3) secs
        broadcast [finished v]
```

2. Now we need to add a new script that listens for the finished broadcast and moves the parrot back to the start. What happens if you change the value that **x** is set to?

```blocks
when I receive [finished v]
    set x to (-170)
```
3. Now add the same script for the lioness. Test different **x** values to make sure the lion and the parrot line up at the start.
4. We also want to put the lion and the parrot in the same position when the project is run, so add another script to each that moves them to the start when we click the flag.

```blocks
when FLAG clicked
    set x to (-170)
```
5. Now click on the button sprite and add a script that shows it when it receives the finished message.

## Test Your Project { .flag}

__Click on the green flag.__

Can you race against a friend, one of you moving the parrot by pressing ‘A’ and the other moving the Lion by pressing ‘L’?

## Save your project { .save}

##Challenge 1: Add a booster { .challenge}

* __Try to add a booster__ that you can use once each race that moves the parrot or the lion __30 steps in 1 go.__
* __Add a new costume__ with fire coming out behind for each sprite and make it appear when the boost is pressed.
* __Create another sound__ that the sprite will make when the boost is pressed.

```blocks
when [p v] key pressed
if <<(racing) = [1]> and <(boosted) = [0]>>
    switch to costume [parrot-boost v]
    set [boosted v] to [1]     
    move (4) steps
    if <touching [edge v]?>
         set (racing) to [0]
        play sound [recording1 v]
        say [The Parrot Wins! v] for (3) secs
        broadcast [finished v]
```
    
## Test Your Project { .flag}

## Save your project { .save}

##Challenge 2: Use custom blocks to simplify your script { .challenge}

The code to check if the race has finished is now used in two places for each sprite: when the sprite is moving normally and when it's moving with the booster. We can simplify our script using a custom block which is a chunk of code that gets used in more than one place. It's a bit like making up our own Scratch code block!

1.  Choose the Parrot's script.
2. Select the `More Blocks`{.blocklightgrey} palette and then click the `Make a Block`{.blocklightgrey} button. 
3. Give the custom block a name by typing **"finished"** into the pink box. Then click OK.
4. You'll now see a `define finished`{.blockpurple} block appear in the scripts window. Drag it to a clear area.
5. Detach the `if`{.blockyellow}`touching edge?`{.blocklightblue}`then`{.blockyellow} block and drag it to the `define finished`{.blockpurple} block.


```blocks
define finished
 if <touching [edge v]?>
     set (racing) to [0]
     play sound [recording1 v]
     say [The Parrot Wins! v] for (3) secs
     broadcast [finished v]

when [q v] key pressed 
if <<(racing) = [1]> and <(boosted) = [0]>>
    switch to costume [parrot-boost v]
    set [boosted v] to [1]     
    move (4) steps
finished
```
Can you drag the `finished`{.blockpurple} block from the palette and use it like any other code item?

Delete the other `if`{.blockyellow}`touching edge?`{.blocklightblue} block from your script and replace it with another `finished`{.blockpurple} custom block.

Does this make your code easier to read? Can you create a similar custom block for the lioness sprite?

## Test Your Project { .flag}

## Save your project { .save}

__Well done you’ve finished, now you can enjoy the game!__

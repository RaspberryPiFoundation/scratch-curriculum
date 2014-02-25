---
title: Fruit machine
level: Level 2
stylesheet: scratch
language: en-GB
embeds: "*.png"
note: "notes for club leaders.md"
materials: "*.sb2"
...

# Introduction {.intro}
This is a game that has three sprites that change costume. You have to stop 
them when they’re showing the same picture (like a fruit machine!).

![screenshot](fruitmachine_screenshot.png)
>>>>>>> scratch2

# STEP 1: Create a sprite that changes costumes { .activity}

## Activity Checklist { .check}

__Let’s import the different pictures for the game__

+ Start a new scratch project. Delete the cat by right clicking it and 
  clicking Delete

+ Add a new Backdrop from the library. Choose the **rays** backdrop from the 
  **Other** category and then delete the original blank stage. 

+ Now add a new sprite from the library. Choose an image from any folder. We 
  used **things/Bananas**, but you can use any image you want to.

+ Click on the blue '**i**' next to the sprite's picture in the Sprites 
  window. Rename the sprite to 'Fruit 1'.

+ Now click the Costumes tab and import two more things so there are three 
  costumes in total (we used **things/apple** and **things/watermelon-a**, but 
  you can use any images you like).

__Now we’ve got some costumes, we want the sprite to change between them.__

# STEP 2: Making the picture change { .activity}

## Activity Checklist { .check}

+ Click the `Scripts` {.blocklightgrey} tab.

+ Click `Events`{.blockgrey} and drag a `when flag clicked` { .blockyellow} 
  into the scripts area. This will be triggered when we click the green flag.

+ Click the Control tab and add a `forever` { .blockyellow} and attach it so it 
  snaps to the bottom.

+ **Click the green flag** in the top right. Notice that a yellow outline is 
  around our script. It’s running because we clicked the green flag, which 
  triggers this.

+ Now click `Looks`{.blockgrey} and drag in a `next costume` { .blockpurple}

+ How do we slow it down so it isn’t changing so quickly? Click the 
  `Control`{.blockgrey} tab and drag in a `wait 1 secs` { .blockyellow}

+ Adjust the time until it’s repeating at a faster pace (a time of 0.5s looks 
  good). 

```blocks
when FLAG clicked
forever    	
    next costume
    wait (0.5) secs
```

## Test Your Project { .flag}
__Click the green flag.__ 
Do the costumes change at a sensible rate?

## Save your project { .save}

## Things to try { .try}

Adjust the time in the `wait 0.5 secs` {.blockyellow} block. What numbers do 
you think would make the game too easy, or too hard?

# STEP 3: Making it stop when we click on it {.activity}

## Activity Checklist { .check}

**Great! We can make the sprite change costumes forever, but how do we make 
it stop when we click on it?**

One way to do it is by using a variable to remember the state of the Sprite. 

+ Create a new variable by clicking `Data` {.blockgrey} and 
  `Make a variable`{.blocklightgrey}. Call it `stopped`{.blockorange} and 
  make it for only this sprite.

+ At the start of the game, the sprite won't have been clicked so we'll set 
  the variable to **"NO"**. 

```blocks
when FLAG clicked
set [stopped v] to (NO)
forever 
  next costume
  wait (0.1) secs
```

+ Now we'll set the variable `stopped`{.blockorange} to  **"YES"** when 
  someone clicks on the sprite.  
```blocks
when this sprite clicked
set [stopped v] to (YES)
```

+ Finally we need to make the sprite stop changing costume when the variable 
  `stopped`{.blockorange} changes to "YES". Add an `if...then` { .blockyellow} 
  loop and use a new **equals** `[] = []`{.blockgreen} operator block (found 
  under the *Operators* tab) to check if `stopped`{.blockorange}  is still "NO".

```blocks
when FLAG clicked
set [stopped v] to (NO)
forever	
  if <(stopped) = [NO]> then
    next costume
    wait (0.5) secs
```

## Test Your Project { .flag}
__Click the green flag, wait for a moment, then click on the sprite.__ 

Does it change costume before you click on it? 

Does it stop when you do click on it?

__Start the program again.__ Does it stop when you put the mouse pointer on 
it, without clicking? Does the sprite stop when you click anywhere else on 
the Stage? 

Keep an eye on the `stopped`{.blockorange} variable watcher on the stage. Does 
it say "YES" and "NO" at the right times?

+ Now you know the `stopped`{.blockorange} variable is working properly, hide 
  the watcher either by right-clicking it on the stage, or clearing the 
  checkbox next to it in the *Variables* tab.

## Save your project { .save}

# Step 4: Creating the other sprite {.activity}
__Now we need to make the other sprites so we can play our game!__

## Activity Checklist { .check}

+ **Duplicate the sprite** (Fruit 1) by right-clicking on it in the bottom right 
  corner.

+ Duplicate it again so there are **3** sprites on the screen.

+ Move each sprite so they are in a line. Make them a bit smaller with if you 
  need to.

+ Change the names of the new sprites to "Fruit 2" and "Fruit 3" by clicking on
  the blue '**i**"''

## Test Your Project { .flag}
__Click the green flag.__ All the sprites should change. Try to stop them all 
on the same picture by clicking on each one in turn!

## Save your project { .save}

# Step 5: Start each sprite with a random costume { .activity}
__Let's make the sprites change to a random costume when the green flag is 
clicked.__

When you start the game just after you’ve loaded it, all the sprites show the 
same costume and change in unison. It would make the game more interesting 
(and harder) if they changed in a less predictable way. 

## Activity Checklist { .check}

+ If you look under the `costumes`{.blocklightgrey}  tab for a sprite then 
you'll see that each costume has a number. You can specify which costume a 
sprite is wearing using either its name or its number.

+ To make the sprite start with a random costume, let's add a 
  `switch costume to` { .blockpurple} block with 
  `pick random (1) to (3)` { .blockgreen} to choose the costume number. 

+ We can also use exactly the same block in the `forever`{.blockyellow} loop 
  so that the sprite switches to a different costume each time it changes 
  during the game.
```blocks
when FLAG clicked
set [stopped v] to (0)
switch costume to <pick random (1) to (3)>
forever	
  if <(stopped) = [NO]> then	
    switch costume to <pick random (1) to (3)>
    wait (0.5) secs
```

+ Do the same thing for each of your sprites. 

## Test Your Project { .flag}
__Click the green flag.__ All the sprites should change their costumes 
unpredictably.

How would we need to change our script if we added another costume?
 
## Save your project { .save}

##Things to try { .try}
 
 __Make the game harder__ 

Change the difficulty of the game somehow. Just making the costumes change 
quicker is fairly easy. Can you come up with something more imaginative. Some 
ideas you might like to try:

+ Change the number of costumes each sprite has.
+ Make some sprites have unique costumes.
+ Have different times between costume changes. 

__Have fun coming up with your own things!__

Every time you make a change, think about whether it makes the game easier or 
harder. Is the game too easy or too hard? How can you adjust the difficulty 
so it’s just right?

## Step 6: Display a message when the game has finished. { .activity}
__Let's show the player a "Game Over" message when they've finished__

## Activity Checklist { .check}

First of all, let's create a different Backdrop to display when the game has 
finished.

+ Click on the stage and then the `Backdrops`{.blocklightgrey} tab. Change the 
  name of the existing backdrop to **Game On**. 

+ Duplicate the backdrop and then add some text to the copy that says 
  **Game Over**. You can change the size of the text by clicking on it and then 
  dragging one of the corners. Rename this backdrop to be **Game Over**.

+ Click on the `Scripts`{.blocklightgrey} tab for the stage and set the 
  "Game On" backdrop to be the one displayed when the game is started. 	

+ How can we detect when all the sprites have stopped? The easiest way is to 
  have another variable that tracks the number of sprites that are still 
  spinning. When the game starts, the Stage should show the "Game On" 
  background and set the `sprites spinning`{.blockorange} variable.
```blocks
when FLAG clicked
set [sprites spinning v] to (3)
switch backdrop to [Game On v]
```

+ Every time a sprite stops spinning, the sprite will reduce the number by 1 
  and then ask the Stage to check if the game is over. Add this script to all
  the sprites.
```blocks
when this sprite clicked
change [sprites spinning v] by -1
set [stopped v] to (YES)
broadcast [check for end v]
```

+ The Stage needs to check if the game has finished and change the background.
  Add this script to the stage.
```blocks
when I receive [check for end v]
if <(sprites spinning) = (0)
  switch backdrop to [Game Over]
```

## Test Your Project { .flag}
__Click the green flag.__ Does the backdrop change to the "Game On" one?

Do the sprites keep spinning?

Do the sprites stop when you click on them?

Does the "Game Over" message appear when you stop all of the sprites?

Click the green flag again. Click one of the sprites a few times. What happens
when you click on one sprite a lot?

+ Each sprite should only change the `sprites spinning`{.blockorange} variable
  when it's clicked __and__ it was spinning. Change the script in all the 
  sprites to check this.
```blocks
when this sprite clicked
if <(stopped) = (NO)>
  change [sprites spinning v] by -1
end 
set [stopped v] to (YES)
broadcast [check for end v]
```

## Test Your Project { .flag}
__Click the green flag.__ Does the "Game Over" message appear when all 3 
sprites are stopped?

Does the "Game Over" message appear when one sprite is clicked a lot?

## Save your project { .save}

# Step 7. Tell the player whether they've won or lost. { .activity}

__The aim of the game is to click on the sprites so they stop while showing 
the same costume. It would be nice to also display a message that told you 
whether you'd won or lost.__

We'll do this with another variable, `winning costume`{.blockorange}, that 
records what costume all the sprites should end up on. 

When the game starts, we don't know what the winning costume will be, so the
`winning costume`{.blockorange} will be **0**. 

When the first sprite is clicked, we know what all the other sprites will have 
to be to win the game, so we can record that. When the other sprites are 
clicked, they can check if they're showing the same costume. If they're not, 
they should set `winning costume`{.blockorange} to **LOSE**.

When the last sprite is clicked, the stage can check if 
`winning costume`{.blockorange} is **LOSE** or not and show either a **You 
win!** or **You lose!** message.

## Activity Checklist { .check}

+ Change the text on the "Game Over" backdrop to "You Win!" and rename the 
  backdrop to "Win".

+ Duplicate the "Win" backdrop, rename it "Lose", and change the text to 
  "You Lose!"

+ Create the `winning costume`{.blockorange} variable and set its value to 
  **0** when the game starts by modifying the script on the Stage.
```block
when FLAG clicked
set [winning costume v] to (0)
set [sprites spinning v] to (3)
switch backdrop to [Game On v]
```

+ Change the scripts in __each__ sprite to set the winning costume 
  appropriately. 
```blocks
when this sprite clicked
if <(stopped) = (NO)>
  change [sprites spinning v] by -1
end 
set [stopped v] to (YES)
if <(winning costume) = 0>
  set [winning costume v] to (costume #)
end
if <not <(winning costume) = (costume #)>>
  set [winning costume v] to (LOSE)
end
broadcast [check for end v]
```

+ Back on the stage, modify the script that changes the background when the 
  game ends so that it looks at the value of `winning costume`{.blockorange}.
```blocks
when I receive [check for end v]
if <(sprites spinning) = (0)
  if <(winning costume) = (LOSE)>
    switch backdrop to [Lose]
  else
    switch backdrop to [Win]
```  
 
## Test Your Project { .flag}
__Click the green flag.__ Does any message disappear when the game starts? 
Does the correct message appear when you lose the game? How about when you win
the game? What happens when you click on a sprite several times in a game?

## Save your project { .save}

__Well done you’ve finished the basic game. There are more things you can do 
to your game though. Have a go at this challenge!__

##Challenge: Make the game get harder and easier over time { .challenge}

Different people will have different skills at playing the game. __How could 
you make the game adjust its difficulty depending on the player?__

One way you could do it is to __adjust the speed the costumes change at__. 
You can use a variable, called `delay`{.blockorange}, to give the duration of 
each sprite’s wait block. If the player wins the round, the delay can be 
reduced a little (to make the game harder). If the player loses the round, 
the delay can be increased a little (to make the game easier). 

You'll also need to think about how to reset the difficulty level of the game.


## Save your project { .save}

__Well done you’ve finished, now you can enjoy the game!__

Don’t forget you can share your game with all your friends and family by 
clicking on __Share__ on the menu bar!

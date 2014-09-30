---
title: Ghostbusters
level: Level 1
language: en-GB
stylesheet: scratch
embeds: "*.png"
materials: ["Ghostbusters.sb2","Timer Scratchcard.pdf"]
...

# Introduction { .intro }

This project is like the game __Whack-a-Mole__. You get points for hitting the ghosts that appear on the screen. The aim is to get as many points as possible in 30 seconds!

![screenshot](ghostbsuters_screenshot.png)

# Step 1: Create a flying ghost { .activity }

## Activity Checklist { .check }

+ Start a new scratch project.
+ Remove the cat sprite and replace the background with the **nature/woods** background.
+ Use the `Choose sprite from library` button to add a new ghoul sprite to the project (use the **fantasy/ghost1** costume).
+ Now we want to make our ghost move. Add a `Variable` for this sprite only called `speed` { .blockorange }.
+ On the **Stage**, the stage monitor for this variable should say “__Ghost1 speed__”. If it just says “speed”, delete the variable and create it again, for this sprite only. Uncheck the box next to the speed block in the **Data palette** so it does not show on the Stage. The speed variable will control how fast the ghost moves. We use a variable so that we can change how fast the ghost moves as the game progresses.
+ We want the ghost to start moving when the game starts, __so make a script like this__:
```blocks
    when FLAG clicked
        set [speed v] to [5]
        forever
            move (speed) steps
```

## Test Your Project { .flag }

Click the green flag and see what your ghost does.

Why does it get stuck on the edge of the screen?

## Save your project { .save }

## Activity Checklist { .check }

+ To stop the ghost getting stuck we need to make her go back the other way when she touches the edge of the screen. Edit your existing script by adding an `if on edge, bounce` { .blockblue } block below your `move`{ .blockblue }`speed`{ .blockorange }`steps`{ .blockblue } block.
```blocks
    when FLAG clicked
        set [speed v] to [5]
        forever
            move (speed) steps
            if on edge, bounce
```

+ To stop the ghost flipping upside down, click on the `rotation style: left-right` button in the Sprite Summary area.

## Test Your Project { .flag }

Click the green flag.

+ Does the ghost move from side to side across the screen?

## Save your project { .save }

## Things to try { .try }

+ Try changing the value of the speed variable to make the ghost fly faster or slower.
+ How would you make the ghost get faster the longer it flies? (This is a tricky one, so don’t worry if you can’t see how to do it. You’ll get more clues as you work through the project.)

# Step 2: Make the ghost appear & vanish randomly { .activity .new-page }

To make the game more fun, we want the ghost to appear and vanish randomly. We’ll do that with another script that runs at the same time as the one that moves the ghost. This new script needs to hide the ghost for a random time, then show it for a random time, and repeat that forever (or until the game finishes).

## Activity Checklist { .check }

+ Create this script for the ghost:
```blocks
    when FLAG clicked
    forever
        hide
        wait (pick random (2) to (5)) secs
        show
        wait (pick random (3) to (5)) secs
```

## Test Your Project { .flag }

Click the green flag.

+ Does the ghost move from side to side across the screen and vanish and appear again randomly?

## Save your project { .save }

## Things to try { .try }

+ Try changing the range of the random numbers. What happens if you pick very big numbers or very small numbers? (Does this give you any more clues for how to make the ghost speed up the longer the game is played?)

# Step 3: Make the ghost disappear when it's clicked { .activity }

To turn this into a game, we need to give the player something to do. They need to click on the ghost to make it disappear. When the ghost is clicked, we want it to disappear and play a sound.

## Activity Checklist { .check }

+ In the **Sounds** tab, add a new sound **Electronic/fairydust**, using the `Choose sound from library` button.
+ Add this script to the ghost:
```blocks
    when this sprite clicked
        hide
        play sound [Fairydust v]
```

## Test Your Project { .flag }

Click the green flag.

+ Does the ghost disappear and play the sound when you click it?

## Save your project { .save }

## Things to try { .try }

+ Ask your volunteer if you can record your own sound to play.

# Step 4: Add a score and timer { .activity .new-page }

We’ve got a ghost, but now we want to make a game! We want to score points every time we click on the ghost but we also want to have a time limit on the game. We can use a variable for the score and the timer.

## Activity Checklist { .check }

+ Create a new `Variable` for all sprites called **score**, and alter the script for the ghost to increase this variable by one when it is clicked.
```blocks
	when this sprite clicked
    	hide
	   play sound [Fairydust v]
	   change [score v] by (1)
```

+ Switch to the **Stage** and create a **new variable** called **time_left**.
+ Add a new script that occurs when the green flag is clicked to set `time_left` { .blockorange } to **30** and reset the score to **0**. Then use a `repeat until` { .blockyellow } block to wait a second and then reduce `time_left` { .blockorange } by one. This should repeat until `time_left` is 0, at which point use `stop all` { .blockyellow } to stop the game.
```blocks
	when FLAG clicked
    	set [time_left v] to (30)
    	set [score v] to (0)
    	repeat until <(time_left) = [0]>
    		wait (1) secs
    		change [time_left v] by (-1)
    	end
    	stop [all v]
```

## Test Your Project { .flag }

Click the green flag.

## Save your project { .save }

## Things to try { .try }

+ How might you make the ghost speed up as the game goes on?

Well done you’ve finished the basic game. There are more things you can do to your game though. Have a go at this challenge!

## Challenge: add more ghosts { .challenge }

If one ghost is good, more must be better! Let’s have three ghosts flying around.

1. Duplicate the ghost by **right-clicking** it in the sprite list.
2. For each ghost **adjust the size of the sprite** so the ghosts are different sizes.
3. For each ghost change the **speed variable** so that they fly at different speeds.
4. Move the ghosts around the canvas so that they are not all together.

## Test Your Project { .flag }

Click the green flag.

+ Do you have three ghosts that move from side to side across the screen, randomly appear and disappear, and disappear when you click on them?

## Save your project { .save }

## Things to try { .try }

+ How many ghosts is a good number for the game?
+ Can you make the ghosts look different? You could either edit their costumes, or use some blocks from the Looks palette to change them.
+ Can you make the ghosts be worth different points?
+ How about making the fastest (and smallest) ghost worth 10 points?

Well done, you’ve finished! Now you can enjoy your game!

Don’t forget you can share your game with all your friends and family by clicking on **Share** on the menu bar!

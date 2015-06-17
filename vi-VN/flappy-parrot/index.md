---
title: Flappy Parrot
level: Level 2
language: en-GB
stylesheet: scratch
embeds: "*.png"
materials: "*.sb2"
...

# Introduction { .intro}
__In this project we’ll make our own version of the highly popular mobile game Flappy Bird. This project requires Scratch 2.0.__
Press the space bar to flap and try to navigate through the gaps in the pipes!

![screenshot](flappy_screenshot.png)

#**Step 1:** Make Flappy fall {.activity}

## Activity Checklist { .check}

+ Start a new Scratch project. Delete the cat by right-clicking it and selecting Delete
+ Replace the background with an outdoor landscape. **desert** is a good choice.
+ Add the Flappy character. You'll need a sprite with costumes for wings up and wings down. **parrot** is a good choice.
+ Change the name of your sprite to __Flappy__.
+ Give Flappy the following script:

```blocks
when FLAG clicked
	go to x: (-50) y: (0)
	forever
		change y by (-3)
```

## Test Your Project { .flag}

__Click the green flag__, does Flappy start in the middle of the screen and then fall to the bottom?

## Save your project { .save}

#**Step 2:** Make Flappy fly {.activity}

*Next, we want Flappy to flap upwards when you press the space bar.*

##Activity Checklist { .check}

+ Click on the __Costumes__ tab and name the costumes **wings up** and **wings down**.
+ Now switch back to the __Scripts__ tab and add this script:

```blocks
when [space v] key pressed
	switch costume to [wings down v]
	repeat (10)
		change y by (6)
	end
	switch costume to [wings up v]
	repeat (10)
		change y by (6)
	end
```

## Test Your Project { .flag}

__Click the green flag__, are you able to control Flappy with the space bar? Do you notice that sometimes you press the space bar but Flappy doesn't move? We'll fix that next...

## Save your project { .save}

#**Step 3:** Fix the controls {.activity}

*We'd like Flappy to respond every time we press the space bar. But when we push the space bar Flappy begins two loops of movements. If we push the space bar again before these loops have finished, Scratch ignores the second press. To solve this, we'll use a variable to count up how many flaps we need to do.*

##Activity Checklist { .check}

+ Disconnect the blocks under the `when space key pressed` {.blockbrown} and put them to the side (we'll use them in a few moments.)
+ Make a new variable `For this sprite only` {.blockgrey} and call it `flaps` {.blockorange}.
+ Add the following script by draging in the blocks you put aside:

```blocks
when FLAG clicked
	set [flaps v] to [0]
	switch costume to [wings up v]
	forever
		repeat until <(flaps) = [0]>
			change [flaps v] by (-1)
			switch costume to [wings down v]
			repeat (10)
				change y by (6)
			end
			switch costume to [wings up v]
			repeat (10)
				change y by (6)
			end

```

+ Finally, add to your `when space key pressed` {.blockbrown} event:

```blocks
when [space v] key pressed
	change [flaps v] by (1)
```

## Test Your Project { .flag}

__Click the green flag__, does Flappy now flap once for each time you press the space bar?

## Save your project { .save}

#**Step 4:** Add the pipes {.activity}

*Next we'll add some obstacles for Flappy to fly through.*

##Activity Checklist { .check}

+ Click on the `Paint new sprite` {.blockgrey} button.
+ Name your costume **pipe**.
+ If the costume is in `Bitmap Mode` {.blockgrey} click on the `Convert to vector` {.blockgrey} button.
+ Click on the `Zoom -` {.blockgrey} so that you can see the entire drawing area.
+ Click on the `Rectangle` {.blockgrey}, pick a colour, and click on the `Filled rectangle` {.blockgrey} button.
+ Click and drag two boxes, one from the top middle and one from the bottom middle as shown:

![screenshot](pipe_design.png)
 
+ You can shade your pipes by clicking on the `Color a shape` {.blockgrey} button and click on the `Horizontal gradient` {.blockgrey} button. Choose two shades of the same colour one for the foreground and one for the background. When you click to fill the shapes, the colours will fade between your chosen colours.
+ Name your sprite **Pipe**.

## Save your project { .save}

#**Step 5:** Make the pipes move {.activity}

*Next we'll make the pipes move and arrange them randomly to provide an obstacle course for Flappy.*

##Activity Checklist { .check}

+ Click on your **Pipe** sprite and select the `Scripts` {.blockgrey} tab.
+ Add the following scripts:

```blocks
when FLAG clicked
	hide
	set size to (200)%
	forever
		create clone of [myself v]
		wait (2) secs

when I start as a clone
	go to x: (240) y: (pick random (-80) to (80))
	show
	repeat (120)
		change x by (-4)
	end
	delete this clone
```

## Test Your Project { .flag}

__Click the green flag__, do pipes appear with gaps to fly through at different heights? If you find it difficult to navigate Flappy through the pipes without touching them, you can make the gap bigger in the **pipe** sprite by editing the costume.

## Save your project { .save}

#**Step 6:** Detect collision with the pipes {.activity}

*To make the game a challenge, the player needs to guide Flappy through the gaps without touching the pipes or the edges of the screen. Now we'll add some blocks to detect if Flappy hits something.*

##Activity Checklist { .check}

+ Let's add a sound to play when Flappy collides. Click on the **Flappy** sprite then on the `Sounds` {.blockgrey} tab.
+ Click the `Choose sound from library` {.blockgrey} button.
+ Pick a collision sound for **Flappy**. The **screech** sound is good.
+ Now click back on the `Scripts` {.blockgrey} tab.
+ Add the following script:

```blocks
when FLAG clicked
	wait until ((touching [edge v]?) or (touching [Pipe v]?))
	play sound [screech v]
	say [Game Over!]
	broadcast [GameOver v]
	stop [other scripts in sprite v]
```

+ Click on the **Pipe** sprite and add a script:

```blocks
when I receive [GameOver v]
	stop [other scripts in sprite v]
```

## Test Your Project { .flag}

__Click the green flag__, does the game end when Flappy touches a pipe or the edge of the screen?

## Save your project { .save}

#**Step 7:** Add scoring {.activity}

*The player should score a point every time Flappy makes it though a pipe. Let's add that next.*

##Activity Checklist { .check}

+ Let's add a sound to play when Flappy scores a point. Click on the **Pipe** sprite add a score sound. **bird** is a good choice.
+ Now click back on the `Scripts` {.blockgrey} tab.
+ Make a new variable `For all sprites` {.blockgrey} and call it `score` {.blockorange}.
+ Add a block to set the score to 0 when the flag is clicked.
+ Add the following block:

```blocks
when I start as a clone
	wait until <(x position) < ([x position v] of [Flappy v])>
	change [score v] by (1)
	play sound [bird v]
```

## Test Your Project { .flag}

__Click the green flag__, does the player score points for flying Flappy through the pipes?

## Save your project { .save}

##Things to try { .try}
1. __How many ways can you make this game easier or harder?__
2. __Well done you’ve finished the basic game. There are more things you can do to your game though. Have a go at these challenges!__

##Challenge 1: add a high score { .challenge}

+ Make a new variable and tick the `Cloud variable (stored on server)` {.blockgrey} box. Call the variable `hi-score` {.blockorange}
+ when the game is over check if you need to set a new high score:

```blocks
when I receive [GameOver v]
	if <(score) > (hi-score)> then
		set [hi-score v] to (score)
	end
	stop [other scripts in sprite v]
```

##Test Your Project { .flag}
__Click the green flag__, does your score update the hi score?

##Save your project { .save}

##Challenge 2: add gravity { .challenge}

When something falls under gravity it doesn't usually fall at a fixed rate. For this challenge we will make Flappy fall as if under gravity.

+ Add a new variable `For this sprite only` {.blockgrey} to **Flappy** and call it `rise` {.blockorange}.
+ Change Flappy's falling script:

```blocks
when FLAG clicked
	set [rise v] to [0]
	go to x: (-50) y: (0)
	forever
		change y by (rise)
		change [rise v] by (-0.4)
```

+ And change Flappy's flapping script:

```blocks
when FLAG clicked
	set [flaps v] to [0]
	switch costume to [wings up v]
	forever
		repeat until <(flaps) = [0]>
			change [flaps v] by (-1)
			switch costume to [wings down v]
			change [rise v] by (8)
			wait (0.2) secs
			switch costume to [wings up v]
			wait (0.2) secs
```

##Test Your Project { .flag}
__Click the green flag__, does Flappy now accelerate when falling and flapping?

##Save your project { .save}

##Challenge 3: fall off screen { .challenge}

When the player loses make Flappy fall off the bottom of the screen before ending the game.

+ Replace the `broadcast GameOver` {.blockbrown}  block with `broadcast Fall` {.blockbrown}
+ Now add the following scripts:

```blocks
when I receive [Fall v]
	repeat (10)
		turn ccw (5) degrees

when I receive [Fall v]
	repeat until <(y position) < [-180]>
		change y by (rise)
		change [rise v] by (-0.4)
	end
	hide
	broadcast [GameOver v]
```

+ Don't forget to add a `show` {.blockpurple} block and reset Flappy's direction when the game restarts.

##Test Your Project { .flag}
__Click the green flag__, does Flappy now fall off the screen after hitting a pipe? Does Flappy reappear in the correct orientation when restarting the game.

##Save your project { .save}

__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!



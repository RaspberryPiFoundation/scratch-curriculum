Level 1

#Caça às bruxas

__Introduction:__
This project is like the game __Whack-a-Mole__. You get points for hitting the witches that appear on the screen. The aim is to get as many points as possible in 30 seconds!

##￼STEP 1: Create a flying witch

1. Start a new scratch project.
2. Remove the cat sprite and replace the background with the nature/woods
background.
3. Use the new sprite from file button to add a new witch
sprite to the project (use the fantasy/witch1 costume). 

Now we want to make our witch move

4. Add a Variable for this sprite only called speed .
On the Stage, the stage monitor for this variable should say “Sprite1 speed”.
If it just says “speed”, delete the variable and create it again, for this sprite only. Uncheck the box next to the speed block in the
Variables palette so it does not show on the Stage.
The speed variable will control how fast the witch moves. We use a variable so that we can change how fast the witch moves as the game progresses.
5. We want the witch to start moving when the game starts, so make a script like this:

```scratch

  when FLAG clicked

	set speed to 5

	forever

		move speed steps

	(end forever)
```
		
###Test Your Project
__Click the green flag__ and see what your witch does. Why does she get stuck on the edge of the screen?

6. To stop the witch getting stuck we need to make her go back the other way when she touches the edge of the screen. Below your
move speed steps block add an if on edge, bounce block.

```scratch

	when FLAG clicked

	set speed to 5

	forever

		move speed steps

		if on edge, bounce

	(end forever)
```
7. To stop the witch flipping upside down, click on the __only face left-right button__ in the Sprite Summary area.

###Test Your Project
__Click the green flag.__ 
Does the witch move from side to side across the screen?

Save your project

###Things to try
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼__Try changing the value of the speed variable to make her fly faster or slower.__

__How would you make the witch get faster the longer she flies?__
(This is a tricky one, so don’t worry if you can’t see how to do it. You’ll get more clues as you work through the project.)

##STEP 2: Make the witch appear & vanish randomly

To make the game more fun, we want the witch to appear and vanish randomly. We’ll do that with another script that runs at the same time as the one that moves the witch. This new script needs to hide the witch for a random time, then show her for a random time, and repeat that forever (or until the game finishes).

Create this script for the witch:

```scratch

	when FLAG clicked

	forever

		hide

		wait pick random 2 to 5 secs

		show

		wait pick random 3 to 5 secs

	(end forever)
```
###Test Your Project
__Click the green flag.__ 
Does the witch move from side to side across the screen and vanish and appear again randomly?

Save your project

###Things to try
__Try changing the range of the random numbers. What happens if you pick very big numbers or very small numbers?__
(Does this give you any more clues for how to make the witch speed up the longer the game is played?)

##￼STEP 3: Make the witch disappear when she’s clicked

To turn this into a game, we need to give the player something to do. They need to click on the witch to make her disappear. When the witch is clicked, we want her to disappear and play a sound.

1. In the Sounds tab, import the sound electronic/fairydust. 

2. Add this script to the witch:

```scratch

	when sprite1 clicked

	hide

	play sound Fairydust
```
###Test Your Project
__Click the green flag.__ 

Does the witch disappear and play the sound when you click it?

Save your project

##Step 4: Add a score and timer

We’ve got a witch, but now we want to make a game! We want to score points every time we click on the witch but we also want to have a time limit on the game. We can use a variable for the score and the timer.


1. Create a new Variable for all sprites called score, and alter the script for the witch to increase this variable by one when she is clicked.

```scratch

	when sprite1 clicked

	hide

	play sound Fairydust

	change score by 1
```
2. Switch to the Stage and create a new variable (this time just for the stage) called timer. Add a new script that occurs when the green flag is clicked to set timer to 30 and reset the score to 0. Then use a repeat until block to wait a second and then reduce timer by
one. This should repeat until timer is 0, at which point use stop all to stop the game.

```scratch

	when FLAG clicked

	set timer to 30

	set score to 0

	repeat until timer = 0

		wait 1 secs

		change timer by -1

	(end repeat)

	stop all
```


###Test Your Project
__Click the green flag.__ 

Save your project

###Things to try
__How might you make the witch speed up as the game goes on?__


__Well done you’ve finished the basic game. There are more things you can do to your game though. Have a go at this challenge!__

##Challenge: add more witches

If one witch is good, more must be better! Let’s have three witches flying around.
1. Duplicate the witch by right-clicking it in the sprite list.
2. For each witch adjust the size of the sprite so the witches are different sizes.
3. For each witch change the speed variable so that they fly at different speeds.
4. Move the witches around the canvas so that they are not all together.

###Test Your Project
__Click the green flag.__ 

Do you have three witches that move from side to side across the screen, randomly appear and disappear, and disappear when you click on them?

Save your project

###Things to try
1. How many witches is a good number for the game?
￼￼2. Can you make the witches look different? You could either edit their costumes, or use some blocks from the Looks palette to change them.
3. Can you make the witches be worth different points? How about making the fastest (and smallest) witch worth 10 points?


__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!

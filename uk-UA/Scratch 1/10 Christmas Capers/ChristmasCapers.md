---
title: Christmas Capers
level: Scratch 1
language: uk-UA
stylesheet: scratch
embeds: "*.png"
materials: ["notes for club leaders/*.*"]
...


#Christmas Capers

__Introduction:__
__In this project we’ll create a game with scrolling backgrounds, scoring and a festive game over screen.__
A disaster in a toy factory has sent presents flying into the sky, help Rudolf to save Christmas by catching the presents!

##STEP 1: Make Rudolph fly

1. Start a new Scratch project. Delete the cat by right-clicking it and selecting Delete
2. Replace the background with SkyBackground.png.
3. Use the new __sprite from file__ button to add the Rudolph sprite to the project (use the __Rudolph.png__ file)
4. Rename the sprite to __Rudolph__.
5. Make Rudolph follow the mouse by using the following script:


```scratch
when FLAG clicked
go to front
forever
	go to mouse-pointer
(end forever)
```

###Test Your Project

__Click the green flag and move the mouse__, does Rudolph follow the mouse?

6. To make the game more interesting we will add some moving snowy hills to make it look like Rudolf is flying. Use the __new sprite from file__ button to add the Snow sprite to the project (use the __SnowHills.png__ file).
7. Rename the sprite to __Snow1__.
8. Create a new variable by clicking variables and make a variable. Call it ScrollX and make it for all sprites, then uncheck the box next to it to remove
it from the stage. This will be used to control how the hills move.
9. Add the following script to make the hills move:

```scratch
when FLAG clicked
set y to 0
forever
	set x to ScrollX
	change ScrollX by -1
	if ScrollX < -480
		set ScrollX to 0
	(end if)
(end forever)
```

###Test Your Project

__Click the green flag__, do the hills move? What happens as the hills move to the side of the screen?

10 Let’s fix the issue with the snowy hills flickering when they reach the right of the screen. Add more hills to the stage use the __new sprite from file__ button to add the Snow sprite to the project again (use the SnowHills.png file).
11 Rename the sprite to __Snow2__.
12 Add the following script to the Snow2 sprite to allow the 2nd set of hills to follow closely behind the first:

```scratch
when FLAG clicked
set y to 0
forever
	set x to ScrollX + 479
(end forever)
```

###Test Your Project

__Click the green flag__, do the hills move? Has the issue with the flickering trees been fixed?

__Save your project__

##STEP 2: Falling Presents

1. We now need to add in the presents for Rudolph to collect. Use the __new sprite from file__ button to add the Present sprite to the project (use the Present.png file).
2. Rename the sprite to __Present__.
3. __Create a new variable__ by clicking __variables__ . Call it `Stop` and make it for this sprite only, then uncheck the box next to it to remove it from the stage. This will be used to control when the present should be removed from the game.
4. __Create another variable__ and call it `Speed` and make it for this sprite only, then uncheck the box next to it to remove it from the stage. This will be used to control the speed that the present falls down the screen.
5. Add the following script to the __Present__ sprite to allow it to fall from the sky. Note that we will use `pick random` to make the present appear in a different place each time.
6. By using the `touching [ Rudolph ]` command we can make the present disappear when touched, we can use this later to keep a score.


```scratch
when FLAG clicked
forever
	set Stop to 0
	go to x: pick random -230 to 230 y: pick random 50 to 170
	set Speed to -1
	repeat until Stop = 1
		change y by Speed
		if y position of Present < -160
			set Stop to 1
		(end if)
		if touching Rudolph?
			set stop to 1
		(end if)
	(end repeat)
(end forever)
```

###Test your project

__Click the green flag,__ do the presents fall from the sky? Do they disappear when Rudolph touches them or they hit the ground?

7 Let’s make the game more interesting by changing the colour of the presents each time they fall. Do this by using the change colour command.
8 Change the speed of each present by replacing set Speed to -1 with the
pick random command, try different values such as -10 to -1. Your script should now look like this.


```scratch
when FLAG clicked
forever
	set Stop to 0
	go to x: pick random -230 to 230 y: pick random 50 to 170
	change colour effect by pick random 1 to 100
	set Speed to -1
	repeat until Stop = 1
		change y by Speed
		if y position of Present < -160
			set Stop to 1
		(end if)
		if touching Rudolph?
			set stop to 1
		(end if)
	(end repeat)
(end forever)
```

###Test Your Project
__Click the green flag,__ do the presents fall at different speeds and colours?

##STEP 3: Scoring and Sound Effects

1. __Let’s change our script to keep track of a score within the game.__ We can then use this later to work out when the game over message should appear.
2. Create a new __variable__ by clicking variables . Call it `Score` and make it for all sprites. Leave this variable ticked so it appears on the screen.
3. Change the script behind the __Present__ sprite to look like this. Note we have both added sound effects with the `play drum` command and also
`change [ score ] by 1` when Rudolph touches the present.


```scratch
when FLAG clicked
forever
	set Stop to 0
	go to x: pick random -230 to 230 y: pick random 50 to 170
	change colour effect by pick random 1 to 100
	set Speed to -1
	repeat until Stop = 1
		change y by Speed
		if y position of Present < -160
			play drum 57 for 0.2 beats
			set Stop to 1
		(end if)
		if touching Rudolph?
			play drum 39 for 0.2 beats
			set stop to 1
			change Score by 1
		(end if)
	(end repeat)
(end forever)
```

4 Let’s add some music to the game, import the sound file __Jingle_Bells.mp3__ to the __Stage__.

```scratch
when FLAG clicked
set ScrollX to 0
set Score to 0
play sound Jingle_Bells
```

5 Add the following script to the __Stage__, this will __set our score to 0__ when the game is started. It will also play Jingle Bells while the game is being played.

Note, if at first the music sounds ‘choppy’ save your project, close Scratch and then open your project again.

###Test Your Project

__Click the green flag,__ does the score change when Rudolph touches a present?

__SAVE YOUR PROJECT__

##STEP 4: Game over

1. __Let’s change our script to keep track of a score within the game.__ We can then use this later to work out when the game over message should appear.
2. Change the script on the __Stage__ so when the __Score reaches 10__ we will
`broadcast` a __GameOver__ message.

```scratch
when FLAG clicked
set ScrollX to 0
set Score to 0
play sound Jingle_Bells
forever 
	if score = 10
		broadcast GameOver and wait
	(end if)
(end forever)
```

3. We now need to add in our GameOver message. Use the __new sprite from file__ button to add the __GameOver__ sprite to the project (use the GameOver.png file).
4. Rename the sprite to __GameOver__.
5. __Add the following script to the GameOver sprite.__ This will `hide` the picture when the game starts and `show` it when the GameOver message is received.


```scratch
when FLAG clicked
hide

when I receive GameOver
go to front
show
stop all
```

###Test Your Project

__Click the green flag,__ does the score change when Rudolph touches a present? 

__SAVE YOUR PROJECT__

##Challenge: Make the game harder

* Can you make the presents wobble on their way down the screen?
* Can you add more than one present to the game at the same time? 
* Change the game over message to appear after 20 presents are collected. 
* Can you reduce the score by 1 when a present hits the ground?

__Well done you’ve finished, now you can enjoy the game.__
Have a very Merry Christmas!

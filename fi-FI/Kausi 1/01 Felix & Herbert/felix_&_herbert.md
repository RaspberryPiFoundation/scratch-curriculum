Level 1

#Felix & Herbert

__Introduction:__
We are going to make a game of catch with __Felix the cat__ and __Herbert__ the mouse. You control Herbert with the mouse and try to avoid getting caught by Felix. The longer you avoid him the more points you score, but don’t get caught because your score will go down!

##STEP 1: Felix follows the mouse pointer

1. Start a new project.
2. Click on the stage next to the sprite and switch to the Backgrounds tab, and then import the background indoors/hall. Delete the original blank background.
3. Change the name of the sprite to Felix.
4. Make sure Felix only points left-right by clicking this button:
5. Create this script:

```scratch

	When FLAG clicked

	forever

		point towards mouse-pointer

		move 10 steps

		next costume

		play drum 62 for 0.3 beats

	(end forever)
```
		
###Test Your Project
__Click the green flag.__
Does Felix follow the mouse pointer? Does it look like he’s walking when he moves? Does he move at the right speed?

Save your project

##STEP 2: Felix chases Herbert

__Next, we want Felix to chase Herbert the mouse, rather than the mouse pointer.__

1. Create another sprite using the choose new sprite from file button and selecting animals/mouse1.
2. Change the name of the sprite to Herbert.
3. Edit the costume and make it smaller than Felix.
Try six clicks on the shrink button:
4. Make sure Herbert only points left-right. 5. Give Herbert this script:


```scratch
	
	When FLAG clicked
	forever
		go to mouse-pointer
		point towards Felix
	(end forever)
```

###Test Your Project
__Click the green flag.__

Does Herbert move with the mouse pointer? Does Felix chase Herbert?

Save your project.

##STEP 3: Felix says when he's caught Herbert

__We want Felix to know when he’s caught Herbert, and tell us.__


1. Change Felix’s script to be this:

```scratch
	
	when FLAG clicked
	forever
		point towards mouse-pointer
		move 10 steps
		next costume
		play drum 62 for 0.3 beats
		if touching Herbert
			say Caught you! for 1 secs
		(end if)
	(end forever)
```

###Test Your Project
__Click the green flag.__

Does Felix say when he’s caught Herbert?

Save your project.

##STEP 4: Herbert turns into a ghost when he’s caught

__Instead of Felix saying something, we want Herbert to turn into a ghost when he’s caught.__

1. Change Felix’s script to send this message when he catches Herbert.

```scratch
	
	when FLAG clicked
	forever
		point towards mouse-pointer
		move 10 steps
		next costume
		play drum 62 for 0.3 beats
		if touching Herbert
			broadcast caught
			play drum 58 for 0.2 beats
			wait 1 sec
		(end if)
	(end forever)
```
2. Import a new costume into Herbert from fantasy/ghost2-a.
3. Edit the costume to make it smaller.
Six clicks on the shrink button should do.
4. Change the names of Herbert’s
costumes so the mouse costume is
called ‘alive’ and the ghost costume is called ‘dead’.
5. Create a new script for Herbert to turn him into a ghost:

```scratch
	
	when I receive caught
	switch to costume dead
	wait 0.5 secs
	switch to costume alive
```
	
###Test Your Project
__Click the green flag.__

Does Herbert turn into a ghost when he’s caught?
Does Felix play the right sounds at the right time?
Does Felix still stay still for long enough for Herbert to get away

Save your project

##STEP 5: Keep Score

__Let’s add a score so we know how well we do at keeping Herbert alive.
We’ll start the score at zero and increase it by one every second. If Felix catches Herbert, we’ll reduce the score by one hundred.__

1. Make a variable, for all sprites, called Score. Click on Variables in the top menu, make a variable and name it score
2. On the stage, create these two scripts

```scratch
	
	when FLAG clicked
	set score to 0
	forever
		change score by 1
		wait 1 secs
	(end forever)
	
	when I receive caught
	change score by -100
```
	
###Test Your Project
__Click the green flag.__

Does the score go up by one every second?
Does the score go down by one hundred when Herbert is caught?
What happens when Herbert is caught before score reaches one hundred? Does the score go back to zero when you start a new game?

Save your project

__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar

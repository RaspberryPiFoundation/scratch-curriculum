Level 2

#Desert Race

__Introduction:__
This game is a two player game where you race a parrot and a lion across the desert. Each player has to press a key as fast as they can to move their animal, the first one to reach the edge of the screen wins.


##STEP 1: Create the scene and add the sprites

1. Select the Stage, and add the desert background.
ticking off the boxes below:
2. Add a new sprite, select the lion sprite that you will find in the animals folder.
3. Add another sprite, select the parrot sprite that you will find in the animals folder.



##STEP 2: Make the lion and the parrot move


We want the sprite to move when you press a key.


1. First select the lion sprite and set it to move 4 steps when you press the ‘L’ key.

```scratch

	when l key pressed
	move 4 steps
```

2. Next, select the parrot sprite and set it to move 4 steps when you press the ‘A’ key.

```scratch

	when a key pressed
	move 4 steps
```

###Test Your Project
__Click the green flag__ 
Do your lion and parrot move across the screen when you press the ‘A’ and ‘L’ keys?

Save your project


##STEP 3: Starting the race

We need to have a way to start the race and to know who has won. __First we create a start button.__

1. Add a new sprite from a file. Choose the button sprite which is inside “things”.
2. Edit the costume of the button sprite, add the text ‘start’ to it and click OK. Move the sprite to the middle of the stage.
3. Now add a script that shows the sprite when the project is run:

```scratch

	when FLAG clicked
	show
```
4. Now we want the button to count down from 3 and then say go and then hide when it is clicked. Add another script like this one:

```scratch

	when StartRace clicked
	say 3 for 1 secs
	say 2 for 1 secs
	say 1 for 1 secs
	say GO! for 1 secs
	hide
```
###Test Your Project
__Click on the green flag.__

When you press the start button does it countdown to the start of the race before disappearing?

Save your project

We only want the racers to move after the race has started and we want to know when the race has finished so we need a variable to hold that information.

5. Add a variable for all sprites called racing. Untick the box next to it so it does not show on the stage.
6. Now set racing to be 0 when the project is first started. Change your `when FLAG clicked` script from before to look like this:

```scratch

	when FLAG clicked
	show
	set racing to 0
```
7. Next, set the racing variable to be 1 when the starting countdown has finished.
8. Now we need to stop the lion and the parrot from moving unless the racing variable is set to be 1. Click on the parrot sprite. __Add a control block to the script__ that only allows the
parrot to move if __racing = 1__.

```scratch

	when a key pressed
	if racing = 1
		move 4 steps
	(end if)
```
9. Now do the same for the lion sprite.

###Test Your Project
__Click on the green flag.__

Does the lion or the parrot move only after the countdown has finished?

We want to know who wins the race and reset it when it has finished so you can
race again.

##STEP 4: Finishing the race

1. Add a block to the parrot’s script that sets the racing variable to be 0 when the sprite touches the edge of the screen.

```scratch

	when a key pressed
	if racing = 1
		move 4 steps
		if touching edge?
			set racing to 0
		(end if)
	(end if)
```
2. Now we want the parrot to let us know if it wins the race. Record a new sound for the Parrot sprite that will be played when the parrot wins. Click __sounds__ and then record the sound of the parrot winning the race!
3. Now add blocks that play the sound you recorded and makes the parrot say it has won:

```scratch

	when a key pressed
	if racing = 1
		move 4 steps
		if touching edge?
			set racing to 0
			play sound recording1
			say The Parrot Wins! for 3 secs
		(end if)
	(end if)
```
4. Now repeat these steps for the lion.

###Test Your Project
__Click on the green flag.__

Can you press the start button and race by pressing the ‘A’ and ‘L’ keys?
Do the sprites make their winning sound and say they’ve won when they reach the end of the race?

Save your project

##STEP 5: Resetting the game

After the race is finished we need to tell the other sprites we have won and reset the
game so we can play again.

__We need the winning sprite to broadcast that it has won.__

1. Click on the Parrot sprite.
Add a block that broadcasts “finished” after the sprite says it has won.

```scratch

	when a key pressed
	if racing = 1
		move 4 steps
		if touching edge?
			set racing to 0
			play sound recording1
			say The Parrot Wins! for 3 secs
			broadcast finished
		(end if)
	(end if)
```
2. Now we need to add a new script that listens for the finished broadcast and moves the parrot
back to the start. What happens if you change the value that x is set to?

```scratch

	when I receive finished
	set x to -175
```
3. Now add the same script for the lion. Test different x values to make sure the lion and the parrot line up at the start.
4. We also want to put the lion and the parrot in the same position when the project is run, so add another script to each that moves them to the start
when we click the flag.

```scratch

	when FLAG clicked
	set x to -175
```
5. Now click on the button sprite and add a script that shows it when it receives the finished message.
###Test Your Project
__Click on the green flag.__


Can you race against a friend, one of you moving the parrot by pressing ‘A’ and the
other moving the Lion by pressing ‘L’?

Save your project

##Challenge: Add a booster

* __Try to add a booster__ that you can use once each race that moves the parrot or the lion __30 steps in 1 go.__
* __Add a new costume__ with fire coming out behind for each sprite and make it appear when the boost is pressed.
* __Create another sound__ that the sprite will make when the boost is pressed.

###Test Your Project

Save your project


__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!

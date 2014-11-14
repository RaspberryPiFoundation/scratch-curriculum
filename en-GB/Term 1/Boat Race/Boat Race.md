---
title: (Beta) Boat Race
level: Term 1
language: en-GB
stylesheet: scratch
embeds: "*.png"
materials: ["BoatRace.sb2","Resources/*.*"]
...

#Heads Up! { .beta}
This project is in Beta. That means we're still testing it, and there's a small chance there could be some bugs or typos. If you're a club leader trying out this project, please complete <a href="https://docs.google.com/forms/d/15QLeJ_aDklioXl5cUyUK1KqZ7lUhCiewl3qiwXOg41M/viewform?usp=send_form" target="_blank">this short questionnaire</a> (or email projects@codeclub.org.uk) to let us know how it went!

# Introduction { .intro }

You are going to learn how to make a game, in which you'll use the mouse to control a boat. You must try to get to the desert island, avoiding the wooden barriers. The white arrows boost your boat and make it go faster.

<div class="scratch-preview">
	<iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/29125780/?autostart=false" frameborder="0"></iframe>
	<img src="boat-final.png">
</div>

# Step 1: Controlling a boat { .activity }

## Activity Checklist { .check }

+ Start a new project, and delete the cat sprite, so that your project is empty.

+ For this project, you should have a 'Resources' folder, containing all of the images you'll need. Make sure that you can find this folder, and ask your club leader if you can't find it.

	![screenshot](boat-resources.png)

+ From this 'Resources' folder, import 'background.png' as the stage backdrop and 'boat.png' as a new sprite.

+ Rename your sprite 'Player 1', shrink it slightly, and move it to the bottom of the stage. 

	Your project should look like this:

	![screenshot](boat-bg.png)	

+ You are going to control the boat with your mouse. Add this code to your boat:

	```blocks
		when flag clicked
		point in direction (0 v)
		go to x: (-215) y: (-160)
		forever
			point towards [mouse-pointer v]
			move (1) steps
		end
	```

+ Test out your boat, by clicking the flag and moving the mouse. Does the boat sail towards the mouse?

	![screenshot](boat-mouse.png)

+ Have a look what happens when the boat reaches the mouse pointer.

	To stop this happening, you'll need to add an `if` {.blockcontrol} block to your code, so that the boat only moves if it is more than 5 pixels away from the mouse.

	```blocks
		when flag clicked
		point in direction (0 v)
		go to x: (-215) y: (-160)
		forever
			if < (distance to [mouse-pointer v]) > [5] > then
				point towards [mouse-pointer v]
				move (1) steps
			end
		end
	```

+ Test out your boat again, to check whether the problem has been fixed.

## Save your project { .save }

# Step 2: Crashing! { .activity }

Your boat can sail through the wooden barriers! Let's fix that.

## Activity Checklist { .check }

+ You'll need 2 costumes for your boat, one normal costume, and one for when the boat crashes. Duplicate your boat costume, and name them 'hit' and 'not hit'.

+ Click on your 'hit' costume, and choose the 'Select' tool to grab bits of the boat and move and rotate them around. Make your boat look as if it's crashed.

	![screenshot](boat-hit-costume.png)

+ Add this code to your boat, inside the `forever` {.blockcontrol} loop, so that it crashes when it touches any brown wooden barriers:

	```blocks
		if <touching color [#A36400]?> then
			switch costume to [hit v]
			say [Noooooo!] for (1) secs
			switch costume to [not hit v]
			point in direction (0 v)
			go to x: (-215) y: (-160)
		end
	```

	This code is inside the `forever` {.blockcontrol} loop, so that your code keeps checking if the boat has crashed.

+ You should also make sure that your boat always starts looking like it's 'not hit'.

+ Now if you try to sail through a wooden barrier, you should see that your boat crashes and moves back to the start.

	![screenshot](boat-crash.png)

## Save your project { .save }

## Challenge: Winning! {.challenge}
Can you add another `if` {.blockcontrol} statement to your boat's code, so that the player wins when they get to the desert island?

When the boat gets to the yellow sand, it should say 'YEAH!' and then the game should stop. You'll need to use this code:

```blocks
	say [YEAH!] for (1) secs
	stop [all v]
```

![screenshot](boat-win.png)

## Save your project { .save }

## Challenge: Sound effects {.challenge}
Can you add sound effects to your game, for when the boat crashes, or reaches the island at the end. You could even add background music (see the previous 'Rock Band' project if you need help with this).

## Save your project { .save }

# Step 4: Time Trial { .activity }

Let's add a timer to the game, so that the player has to get to the desert island as fast as possible.

## Activity Checklist { .check }

+ Add a new variable called `time` {.blockdata} to your game. You can also change the display of your new variable. If you need help, have a look at the 'Balloons' project.

	![screenshot](boat-variable.png)

+ Add this code to your _stage_, so that the timer counts up until the boat reaches the desert island:

	```blocks
		when flag clicked
		set [time v] to [0]
		forever
			wait (0.1) secs
			change [time v] by (0.1)
		end
	```

+ That's it! Test out your game and see how quickly you can get to the desert island!

	![screenshot](boat-variable-test.png)

## Save your project { .save }

# Step 4: Obstacles and power-ups { .activity }

This game is _far_ too easy - let's add things to make it more interesting.

## Activity Checklist { .check }

+ First let's add some 'boosts' to your game, which will speed up the boat. Edit your stage backdrop and add in some white booster arrows.

	![screenshot](boat-boost.png)

+ You can now add some code to your boat's `forever` {.blockcontrol} loop, so that it moves 2 _extra_ steps when touching a white booster.

	```blocks
		if <touching color [#FFFFFF]?> then
			move (3) steps
		end
	```

+ You can also add in a spinning gate, which your boat has to avoid. Add in a new sprite called 'Gate', which looks like this:

	![screenshot](boat-gate.png)

+ Make sure that the colour of the gate is the same as the other wooden barriers.

	![screenshot](boat-colour.png)

+ Set the center of the gate sprite.

	![screenshot](boat-center.png)

+ Add this code to your gate, to make it spin slowly:

	```blocks
		when flag clicked
		forever
			turn right (1) degrees
		end
	```

+ Test out your game. You should now have a spinning gate that you must avoid.

	![screenshot](boat-gate-test.png)

## Save your project { .save }

## Challenge: More obstacles! {.challenge .new-page}
Can you add more obstacles to your game? Here are some ideas to help you:

+ You could add more wood to your backdrop, to make your game more difficult.

![screenshot](boat-wood.png)

+ You could add green slime to your backdrop, which slows the player down when they touch it. You can use a `wait` {.blockcontrol} block to do this:

```blocks
	wait (0.01) secs
````

![screenshot](boat-algae.png)

+ You could add a moving object, like a log or a shark! These blocks may help you:

```blocks
	move (1) steps
	if on edge, bounce
````

If your new object isn't brown, you'll need to add to your boat code:

```blocks
	if <  <touching color [#A36400]?> or <touching [shark v]?> > then
	end
```

![screenshot](boat-log.png)

## Save your project { .save }

## Challenge: More boats! {.challenge .new-page}
Can you turn your game into a race between 2 players? 

+ Duplicate the boat, rename it 'Player 2' and change it's colour.

![screenshot](boat-p2.png)

+ Change Player 2's starting position, by changing this code:

```blocks
	go to x: (-215) y: (-160)
```

+ Delete the code that uses the mouse to control the boat:

```blocks
	if < (distance to [mouse-pointer v]) > [5] > then
		point towards [mouse-pointer v]
		move (1) steps
	end
```

...and replace it with code to control the boat using the arrow keys. 

This is the code you'll need to move the boat forward:

```blocks
	if < key [up arrow v] pressed? > then
		move (1) steps
	end
```

You'll also need code to `turn` {.blockmotion} the boat when the left and right arrow keys are pressed.

## Save your project { .save }

## Challenge: More levels! {.challenge .new-page}
Can you create additional backdrops, and allow the player to choose between levels? 

```blocks
	when [space v] key pressed
	next backdrop
```

## Save your project { .save }

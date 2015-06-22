---
title: Boat Race
level: Scratch 1
materials: ["Club Leader Resources/*.*","Project Resources/*.*"]
notes: "Boat Race - notes.md"
layout: project
---

# Introduction { .intro }

You are going to learn how to make a game, in which you'll use the mouse to navigate a boat to a desert island.

<div class="scratch-preview">
	<iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/63957956/?autostart=false" frameborder="0"></iframe>
	<img src="boat-final.png">
</div>

# Step 1: Planning your game { .activity }

## Activity Checklist { .check }

+ Start a new Scratch project, and delete the cat sprite so that your project is empty. You can find the online Scratch editor at <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Click on your stage backdrop and plan out your level. You should add:
	+ Wood that your boat has to avoid;
	+ A desert island that your boat has to get to.

	Here's how your game could look:

	![screenshot](boat-bg.png) 

# Step 2: Controlling the boat { .activity }

## Activity Checklist { .check }

+ If your club leader has given you a 'Resources' folder, click 'Upload sprite from file' and add the 'boat.png' image. You should shrink the sprite and put it in it's starting position.

	![screenshot](boat-boat.png)

	If you don't have the boat.png image, you can draw your own boat instead!

+ You are going to control the boat with your mouse. Add this code to your boat:

	```blocks
		when flag clicked
		point in direction (0 v)
		go to x: (-190) y: (-150)
		forever
			point towards [mouse-pointer v]
			move (1) steps
		end
	```

+ Test out your boat, by clicking the flag and moving the mouse. Does the boat sail towards the mouse?

	![screenshot](boat-mouse.png)

+ What happens if the boat reaches the mouse pointer?

	To stop this happening, you'll need to add an `if` {.blockcontrol} block to your code, so that the boat only moves if it is more than 5 pixels away from the mouse.

	![screenshot](boat-pointer.png)	

+ Test out your boat again, to check whether the problem has been fixed.

## Save your project { .save }

# Step 3: Crashing! { .activity .new-page }

Your boat can sail through the wooden barriers! Let's fix that.

## Activity Checklist { .check }

+ You'll need 2 costumes for your boat, one normal costume, and one for when the boat crashes. Duplicate your boat costume, and name them 'normal' and 'hit'.

+ Click on your 'hit' costume, and choose the 'Select' tool to grab bits of the boat and move and rotate them around. Make your boat look as if it's crashed.

	![screenshot](boat-hit-costume.png)

+ Add this code to your boat, inside the `forever` {.blockcontrol} loop, so that it crashes when it touches any brown wooden bits:

	```blocks
		if <touching color [#603C15]?> then
			switch costume to [hit v]
			say [Noooooo!] for (1) secs
			switch costume to [normal v]
			point in direction (0 v)
			go to x: (-215) y: (-160)
		end
	```

	This code is inside the `forever` {.blockcontrol} loop, so that your code keeps checking if the boat has crashed.

+ You should also make sure that your boat always starts looking like it's 'normal'.

+ Now if you try to sail through a wooden barrier, you should see that your boat crashes and moves back to the start.

	![screenshot](boat-crash.png)

## Save your project { .save }

## Challenge: Winning! {.challenge}
Can you add another `if` {.blockcontrol} statement to your boat's code, so that the player wins when they get to the desert island?

When the boat gets to the yellow desert island, it should say 'YEAH!' and then the game should stop. You'll need to use this code:

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

Let's add a timer to your game, so that the player has to get to the desert island as fast as possible.

## Activity Checklist { .check }

+ Add a new variable called `time` {.blockdata} to your stage. You can also change the display of your new variable. If you need help, have a look at the 'Balloons' project.

	![screenshot](boat-variable.png)

+ Add this code to your __stage__, so that the timer counts up until the boat reaches the desert island:

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

# Step 5: Obstacles and power-ups { .activity }

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

+ You can also add in a spinning gate, which your boat has to avoid. Add in a new sprite called 'gate', which looks like this:

	![screenshot](boat-gate.png)

	Make sure that the colour of the gate is the same as the other wooden barriers.

+ Set the center of the gate sprite.

	![screenshot](boat-center.png)

+ Add code to your gate, to make it spin slowly `forever` {.blockcontrol}.

+ Test out your game. You should now have a spinning gate that you must avoid.

	![screenshot](boat-gate-test.png)

## Save your project { .save }

## Challenge: More obstacles! {.challenge .new-page}
Can you add more obstacles to your game? Here are some ideas:

+ You could add green slime to your backdrop, which slows the player down when they touch it. You can use a `wait` {.blockcontrol} block to do this:

```blocks
	wait (0.01) secs
````

![screenshot](boat-algae.png)

+ You could add a moving object, like a log or a shark!

![screenshot](boat-obstacles.png)

These blocks may help you:

```blocks
	move (1) steps
	if on edge, bounce
````

If your new object isn't brown, you'll need to add to your boat code:

```blocks
	if <  <touching color [#603C15]?> or <touching [shark v]?> > then
	end
```

## Save your project { .save }

## Challenge: More boats! {.challenge .new-page}
Can you turn your game into a race between 2 players?

+ Duplicate the boat, rename it 'Player 2' and change its colour.

![screenshot](boat-p2.png)

+ Change Player 2's starting position, by changing this code:

```blocks
	go to x: (-190) y: (-150)
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

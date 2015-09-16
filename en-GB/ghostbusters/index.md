---
title: Ghostbusters
description: Learn how to make a ghost-catching game!
layout: project
notes: "Ghostbusters - notes.md"
---

# Introduction { .intro }

You are going to make a ghost-catching game!

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="https://scratch.mit.edu/projects/embed/60787262/?autostart=false" frameborder="0"></iframe>
  <img src="images/ghost-final.png">
</div>

# Step 1: Animating a ghost { .activity }

## Activity Checklist { .check }

+ Start a new Scratch project, and delete the cat sprite so that your project is empty. You can find the online Scratch editor at <a href="http://jumpto.cc/scratch-new" target="_blank">jumpto.cc/scratch-new</a>.

+ Add in a new ghost sprite, and a suitable stage backdrop.

	![screenshot](images/ghost-ghost.png)

+ Add this code to your ghost, so that it repeatedly appears and disappears:

	```blocks
		when flag clicked
		forever
			hide
			wait (1) secs
			show
			wait (1) secs
		end
	```

+ Test out your ghost's code, by clicking the green flag.

## Save your project { .save }

# Step 2: Random ghosts { .activity }

Your ghost is really easy to catch, because it doesn't move!

## Activity Checklist { .check }

+ Instead of staying in the same position, you can let Scratch choose random x and y coordinates instead. Add a `go to` {.blockmotion} block to your ghost's code, so that it looks like this:

	```blocks
		when flag clicked
		forever
			hide
			wait (1) secs
			go to x:(pick random (-150) to (150)) y:(pick random (-150) to (150))
			show
			wait (1) secs
		end
	```

+ Test our your ghost again, and you should notice that it appears in a different place each time.

## Save your project { .save }

## Challenge: More randomness {.challenge}
Can you make your ghost `wait` {.blockcontrol} a random amount of time before appearing? Can you use the `set size` {.blocklooks} block to make your ghost a random size each time it appears?

## Save your project { .save }

# Step 3: Catching ghosts { .activity }

Lets allow the player to catch ghosts!

## Activity Checklist { .check }

+ To allow the player to catch a ghost, add this code:

	```blocks
		when this sprite clicked
		hide
	```

+ Test out your project. Can you catch ghosts as they appear? If you find it difficult to catch the ghosts, you can play the game in fullscreen mode by clicking this button:

	![screenshot](images/ghost-fullscreen.png)

## Challenge: Adding a sound { .challenge }
Can you make a sound each time a ghost is caught?

## Save your project { .save }

# Step 4: Adding a score { .activity .new-page }

Let's make things more interesting by keeping score.

## Activity Checklist { .check }

+ To keep the player's score, you need a place to put it. A __variable__ is a place to store data that can change, like a score.

	To create a new variable, click on the 'Scripts' tab, select `Data` {.blockdata} and then click 'Make a Variable'.

	![screenshot](images/ghost-score.png)

	Type 'score' as the name of the variable, make sure that it is available for all sprites, and click 'OK' to create it. You'll then see lots of code blocks that can be used with your `score` {.blockdata} variable.

	![screenshot](images/ghost-variable.png)

	You'll also see the score in the top-left of the stage.

	![screenshot](images/ghost-stage-score.png)

+ When a new game is started (by clicking the flag), you should set the player's score to 0:

	```blocks
	when flag clicked
	set [score v] to [0]
	```

+ Whenever a ghost is caught, you need to add 1 to the player's score:

	![screenshot](images/ghost-change-score.png)

+ Run your program again and catch some ghosts. Does your score change?

## Save your project { .save }

# Step 5: Adding a timer { .activity }

You can make your game more interesting, by only giving your player 10 seconds to catch as many ghosts as possible.

## Activity Checklist { .check }

+ You can use another variable to store the remaining time left. Click on the stage, and create a new variable called 'time':

	![screenshot](images/ghost-time.png)

+ This is how the timer should work:

	+ The timer should start at 10 seconds;
	+ The timer should count down every second;
	+ The game should stop when the timer gets to 0.

	Here's the code to do this, which you can add to your __stage__:

	```blocks
		when flag clicked
		set [time v] to [10]
		repeat until <(time) = [0]>
			wait (1) secs
			change [time v] by (-1)
		end
		stop [all v]
	```

	This is how you add the `repeat until`{.blockcontrol}`time`{.blockdata}`= 0`{.blockoperators} code:

	![screenshot](images/ghost-timer-help.png)

+ Drag your 'time' variable display to the right side of the stage. You can also right-click on the variable display and choose 'large readout' to change how the time is displayed.

	![screenshot](images/ghost-readout.png)

+ Ask a friend to test your game. How many points can they score? If your game is too easy, you can:

	+ Give the player less time;
	+ Make the ghosts appear less often;
	+ Make the ghosts smaller.

	Test your game a few times until you're happy that it's the right level of difficulty.

## Save your project { .save }

## Challenge: More objects {.challenge}
Can you add in other objects to your game?

![screenshot](images/ghost-final.png)

You'll need to think about the objects you're adding. Think about:

+ How big is it?
+ Will it appear more or less often than the ghosts?
+ What will it look/sound like when it has been caught?
+ How many points will you score (or lose) for catching it?

If you need help adding another object, you can reuse the steps above!

## Save your project { .save }

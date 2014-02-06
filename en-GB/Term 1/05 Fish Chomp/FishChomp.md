---
title: Fish Chomp
level: Level 2
language: en-GB
stylesheet: scratch
embeds: "*.png"
note: "notes for club leaders.md"
...

# Introduction { .intro}
We’re going to make a Fish Chomp game! Guide the large Hungry Fish and try to eat all the prey that are swimming around.

![screenshot](fishchomp_screenshot.png)

# STEP 1: Create a sprite that follows the mouse { .activity}
__Let’s make the Hungry Fish swim around the sea!__

## Activity Checklist { .check}

1. Start a new Scratch project.
2. Select the Stage, then select the Stage’s Backdrop tab. Import the
background **Nature/underwater3** using `choose background from library`{.blocklightgrey}. Finally, remove **backdrop1**.
3. Change the name of Sprite1 to 'Hungry Fish' by clicking on the blue 'i' symbol.
4. Import Hungry Fish’s costume, **resources/hungry-fish.png** then remove its existing **costume1** and **costume2**.
5. Click on the blue '**i**' symbol again,  and make sure the sprite can only flip left-right.
6. Now create a script for Hungry Fish to follow the mouse around the sea like this:

```blocks
when FLAG clicked
    forever    	
        point towards [mouse pointer v]
        move (3) steps
```

## Test Your Project { .flag}

__Click the green flag.__ 
Move the mouse pointer around the sea. Does the fish follow the pointer?
What happens if you don’t move the mouse pointer and the fish catches up with it? What does it look like? Why does it do this?

1. You can stop the Hungry Fish flipping like crazy if you make it only move when it’s not too near the mouse pointer
(The `distance to`{.blocklightblue} block is in the `Sensing`{.blocklightgrey} palette).

```blocks
when FLAG clicked
    forever if <(distance to [mouse-pointer v]) > (10)>
        point towards [mouse-pointer v]
        move (3) steps
```

## Save your project { .save}

## Things to try { .try}

If you want, you can put different numbers in the script. How does that change how Hungry Fish moves? Change the distance threshold to a large number (e.g. 100), or a small number (e.g. 1). Change the amount the fish moves to a large number (e.g. 20) or a small number (e.g. 1 or even 0).


# STEP 2: Add some prey { .activity}
__It's time to make something for the Hungry Fish to try to eat!__

## Activity Checklist { .check}

1. Create a new sprite from the library, using **Animals/starfish**. 
2. Use the `Shrink`{.blocklightgrey} sprite tool (above the Stage) to make the sprite smaller.
3. Create a script to make the prey swim around. We want them to move randomly, so let’s make it move forward a bit, then turn a random amount left or right, then do it again.

```blocks
when FLAG clicked
	forever		
        move (2) steps
        turn right (pick random (-20) to (20)) degrees
        if on edge, bounce  
```

## Test Your Project { .flag}

__Click the green flag__ and watch the prey swim around. Does it swim like you expect? Does it swim realistically?

__At the moment, the Hungry Fish and the prey don’t interact with each other. We’ll sort that out in the next step.__

## Save your project { .save}

## Things to try { .try}

* Try changing the numbers in the `pick random`{.blockgreen} and move blocks. How do they make the prey move differently?
* What does the `if on edge, bounce`{.blockblue} block do? Take it out and see what happens.

#STEP 3: Hungry Fish eats the prey { .activity}

__Now we want to make the Hungry Fish eat the prey!__ Once the Hungry Fish has caught the prey in its mouth, two things need to happen:
* The Hungry Fish needs to close its mouth and make a "chomp" sound.
* The prey needs to disappear, then reappear a short while later.

## Activity Checklist { .check}

1. First, let’s make the prey disappear if it is touching the Hungry Fish, and then reappear 3 seconds later. Use the `touching`{.blocklightblue} block to see if it is touching the fish.

```blocks

forever    	
		move (2) steps
		turn right (pick random (-20) to (20)) degrees
		if on edge, bounce
		if <touching [Hungry Fish v]?> then
			hide
			wait (3) secs
			show
```

## Test Your Project { .flag}
__Try out your game again – can you spot any problems?__ Notice that the prey disappears no matter where it touches the Hungry Fish. Also, the fish could just wait 3 seconds and eat the prey the moment it reappears – this isn’t very fair!

2. How could we make sure the prey only disappears if it is touching the Hungry Fish’s mouth? Well, we could use the `touching color`{.blocklightblue} block, and see if it is touching the fish’s blue teeth. To do this, replace the `touching`{.blocklightblue} block with a `touching color`{.blocklightblue} block in your script, click on the color in the block and then click again on the fish’s teeth.
3. Next we can make the prey move to a random point on the screen before reappearing using a `go to`{.blockblue} block, and giving it a random value for **x** and **y**.

```blocks
when FLAG clicked
	forever		
		move (2) steps
		turn right (pick random (-20) to (20)) degrees
		if on edge, bounce
		if <touching color [#FFFFFF]?> then
			hide
			wait (3) secs
			go to x:(pick random (-220) to (220)) y: (pick random (-170) to (170))
			show
```
    
## Test Your Project { .flag}

Try the game again – does the prey only vanish when it touches the fish’s mouth? And does it re-appear in a random point on the screen instead of where it was eaten?

4. The fish needs to know when it has eaten something so it can play a sound and change its skin. To do this, we can have the prey `broadcast`{.blockyellow} the fact that it’s been eaten before vanishing.

```blocks

when FLAG clicked
forever		
	move (2) steps
	turn right <pick random (-20) to (20)> degrees
	if on edge, bounce
	if <touching color [#FFFFFF]?>
		broadcast [got me v]
		hide
		wait (3) secs
		go to x:<pick random (-220) to (220)> y: <pick random (-170) to (170)>
		show
	
```
__Now we want the fish to respond to this message by making a “chomp” sound and snapping its jaws.__

5. Add the **resources/mouth-closed.png** costume and the **resources/chomp.mp3** sound to the Hungry Fish sprite.
6. Then, add a new script to the Hungry Fish to respond to the message `broadcast`{.blockyellow} by the prey. This script should make the fish play the **'chomp'** sound and `switch to`{.blockpurple} the mouth-closed costume, wait briefly and then switch back.

```blocks
when I receive [got me v]
	play sound [chomp v]
	repeat (2)
		switch to costume [mouth-closed v]
		wait (0.5) secs
		switch to costume [hungry-fish v]
```

__Now our Hungry Fish is ready to eat, let’s fill the ocean with prey. Right-click on the prey sprite and click “duplicate” several times.__

## Test Your Project { .flag}
Click the green flag.
Does the Hungry Fish eat the prey? Does it eat each of the different prey?

## Save your project { .save}

##Things to think about
Why do we need to add a `show`{.blockblue} block to the start of the prey’s script? Think about what would happen if the prey is eaten, then the game is stopped before it reappears. What would happen if the game was restarted then?

__Well done you’ve finished the basic game. There are more things you can do to your game though. Are you ready for a challenge?__


## Challenge 1: Make the prey move differently { .challenge}

At the moment, all the prey move in the same way. __Can you make one of them move differently?__ __Hint:__ Don’t spend too long on this bit without looking at the other activities in this project.

__Pick one of the prey to experiment on.__ If they have the same costumes, make it a different colour with the `set color effect`{.blockpurple} block. That way, you can tell it apart from the rest of the prey.

Make this prey move slower than the others. __Hint:__ Look at the `move 2 steps`{.blockblue} block.


## Test Your Project { .flag}
Does the prey move slower? Does this make the game better?
If you can do that, __try making one of the prey move quicker than the others.__


Does the prey still move in a sensible way? Do these changes make the game better?
__Hint:__ If your prey swims around in circles, check the values of the `pick random`{.blockgreen} block in the `turn`{.blockblue} block.

How about you make each of the prey behave differently, using different combinations of these changes?

Do any of these changes make the game better? Do they make the game more interesting, more fun, harder, or easier? Are any of those “better”?

## Save your project { .save}

## Challenge 2: Make the prey avoid the Hungry Fish { .challenge}

The prey in this game are really stupid! They just swim around randomly until they’re eaten. Real prey swim away from predators. __Let’s make one of the prey swim away from the Hungry Fish.__

There’s no block in Scratch that tells you the direction that another sprite is in. But you can make one sprite point towards another, then make it turn around to face away. The blocks you need are in the `Motion`{.blocklightgrey} palette.

Using that idea, __make one of the prey always point away from the Hungry Fish.__ 

You might find that your prey gets stuck in the corner if it is always swimming away from the fish. You might want to have the prey only try to escape when the fish gets close. __Hint:__ Look back at how we used the `distance to`{.blocklightblue} block ealier in the game. 

## Test Your Project { .flag}
Does this make the prey harder to catch? Does it make the game better?

## Save your project { .save}

## Challenge 3: Add a score { .challenge}
It’s not enough just to eat lobsters. How do you know you’re better at the game than your friends? __You need a way to keep score so lets add a score board.__ Look at the __Keep Score scratch card__ for an idea of how to do it. 

Where should you put the block that changes the score?

Make sure the score goes back to zero at the start of the game. Where should you put that block?

## Test Your Project { .flag}
Does the score go to zero at the start of the game? Does it go up every time you eat prey?

## Save your project { .save}

## Challenge 4: Add a countdown { .challenge}

__Give yourself a time limit in the game.__ How many prey can you eat in thirty seconds?

Look at the __Timer scratch card__ for how to add a timer to the game. Start with the game lasting thirty seconds.

## Test Your Project { .flag}
Does the timer start at 30?

Does it go down at the right speed?

Can you catch prey while the timer is going?

Does the game stop when the timer reaches zero?

## Save your project { .save}

## Challenge 5: Add a bonus score { .challenge}
Award a large bonus score if you can eat all three lobsters at the same time. How can you tell how many prey have been eaten?

__Hint:__ One way to do this __uses a variable to count how many prey are swimming around.__

## Save your project { .save}

## Challenge 6: Change the game: keep a prey alive! { .challenge}
Sometimes, you can have great new ideas by taking an existing idea and doing the opposite.

__Modify the game so that, instead of you controlling a fish that tries to eat the others, you control one prey in a sea with lots of Hungry Fish.__ How long can you last before you’re eaten? Instead of having a score, how about giving the prey 3 lives and ending the game when they're all gone?

## Save your project { .save}

__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!

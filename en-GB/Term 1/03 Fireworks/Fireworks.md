Level 1

#Fireworks

__Introduction:__
In this project, we’ll create a fireworks display over a city.

##STEP 1: Create a rocket that flies towards the mouse

__Let’s import the different pictures for the game__

1. Start a new Scratch project. Delete the cat by right clicking it and clicking Delete
2. Replace the background with outdoor/city-with-water
3. Use the __new sprite from file__ button to add a Rocket sprite
to the project (use the Resources/Rocket.png costume).
4. Make the rocket hide when the green
flag is clicked.

Now we want to make the rocket move towards the mouse when the mouse is clicked.

5. Add a when space key pressed control block, and under this make the rocket appear and glide towards the mouse

```scratch

	when FLAG clicked

	hide

	
	when space key pressed
	show
	glide 1 secs to x: mouse x y: mouse y
```
		
###Test Your Project
__Click the green flag, place your mouse over the stage and press the space bar.__

Does the rocket appear and move to the mouse?
What happens if you move the mouse and press space again?

6. Fireworks don’t tend to fly from side to side, so lets make sure it always glides towards the mouse from the bottom of the screen. Before we show the rocket, use the go to block tell it to
move to below the bottom of
the screen, but stay in the same place horizontally.

```scratch

	when FLAG clicked

	hide

	
	when space key pressed
	go to x: mouse x y: -200
	show
	glide 1 secs to x: mouse x y: mouse y
```

###Test Your Project
__Click the green flag, place your mouse over the stage and press the space bar.__ 
Does the rocket fly towards the mouse from the bottom of the screen? What happens if you move the mouse and press space again?

7. Finally, lets make this work by using the mouse button instead of the space bar. To do this, we can wrap our script in a __forever if mouse down__.
Then swap the __when space key pressed__ control block for __when flag clicked__ and last but not least make
sure the rocket is hidden when everything starts up.

```scratch

	when FLAG clicked
	hide
	forever if mouse down?
		go to x: mouse x y: -200
		show
		glide 1 secs to x: mouse x y: mouse y
	(end forever)
```
###Test Your Project
__Click the green flag, and then press the mouse button over the stage. Click again at another point.__ 

###Things to try
1. Try changing where the rocket moves to be fore gliding towards the mouse to make it arc a little.
2. Try making some rockets a little slower or faster than others.

Save your project.

##STEP 2: Make the rocket explode

1. The first step to make the rocket explode is to make it play a bang sound Resources\bang before it starts moving, and then hide itself once it reaches the mouse. To import a sound go
to the Sounds tab and click import

```scratch

	when FLAG clicked
	hide
	forever if mouse down?
		go to x: mouse x y: -200
		play sound bang
		show
		glide 1 secs to x: mouse x y: mouse y
		hide
	(end forever)
```
2. Next, make the rocket broadcast a new message when it explodes. We’ll listen for this message later on.

```scratch

	when FLAG clicked
	hide
	forever if mouse down?
		go to x: mouse x y: -200
		play sound bang
		show
		glide 1 secs to x: mouse x y: mouse y
		hide
		broadcast explode
	(end forever)
```
###Test Your Project
__Click the green flag.__ 
Make sure the rocket plays a noise and hides when it reaches the mouse.

3. Import a new sprite using Resources/firework1.png
4. When it receives the explode message, it should hide itself and then move to the position of the rocket using the go to block, show itself, and then vanish again a second later.

```scratch

	when I receive explode

	hide

	go to x: x position of rocket y: y position of rocket

	show

	wait 1 sec

	hide
```
###Test Your Project
__Send another rocket flying.__ 
Does it get replaced with the explosion graphic when it explodes?
What happens if you hold the mouse button down whilst moving the mouse? (Don’t worry, we’ll fix this later on).

Save your project

##STEP 3: Make each explosion unique

1. Now we can make each explosion even more unique by using the set color effect block, and have it pick a random colour between 1 and 200 before showing it.

```scratch

	when I receive explode

	hide

	set colour effect to pick random 1 to 200

	go to x: x position of rocket y: y position of rocket

	show

	wait 1 sec

	hide
```

###Test Your Project
__Click the green flag.__ 

Does each explosion have a different colour?

2. Lets add a number of different possible explosion graphics as costumes, using Resources/firework2.png and Resources/firework3.png, and switch between them for each rocket, again before showing it.

###Test Your Project
__Click the green flag.__ 

Does each rocket have a different explosion graphic?

3. Finally, lets make the explosion grow over time as opposed to simply appearing. Instead of waiting a second, set the size of the sprite to 5% before we show it, and then once it’s shown, increase the size by 2 fifty times, using a repeat block.

```scratch

	when I receive explode

	hide

	set colour effect to pick random 1 to 200

	go to x: x position of rocket y: y position of rocket

	set size to 5%

	show
	
	repeat 50
		change size by 2
	(end repeat)

	hide
```
###Test Your Project
__Click the green flag.__ 

Does the explosion graphic spread out from the centre of the rocket and slowly grow?

###Things to try
Why not try making each explosion more unique by altering the size and speed of growth for the explosion.

Save your project

##Step 4: Fixing the Broadcast Bug
Remember earlier we had a bug involving holding down the mouse button?
This occurs because when the rocket broadcasts its explosion, it will immediately repeat the if loop and send out another explosion message, before the last one has finished displaying.


1. To fix this, we can replace the broadcast block with a broadcast and wait block. This way, the loop will not repeat until the explosion finishes exploding.

```scratch

	when FLAG clicked
	hide
	forever if mouse down?
		go to x: mouse x y: -200
		play sound bang
		show
		glide 1 secs to x: mouse x y: mouse y
		hide
		broadcast explode and wait
	(end forever)
```
###Test Your Project
__Click the green flag, hold down the mouse button and move the mouse around the stage.__ 

Does the explosion graphic appear in the right place and at the right time?

Save your project

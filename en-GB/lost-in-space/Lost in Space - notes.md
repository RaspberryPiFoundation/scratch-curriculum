---
title: Lost in Space — Volunteer Notes
---

#Introduction:
In this project, children will learn how to combine code blocks to create a simple animation.

#Resources
For this project, Scratch 2 should be used. Scratch 2 can either be used online at [jumpto.cc/scratch-on](http://jumpto.cc/scratch-on) or can be downloaded from [jumpto.cc/scratch-off](http://jumpto.cc/scratch-off) and used offline.

You can find a completed version of this project <a href="http://scratch.mit.edu/projects/26818098/#editor">online</a>, or it can be downloaded by clicking the 'Project Materials' link for this project, which contains:

+ LostInSpace.sb2

#Learning Objectives
+ Loops:
	+ `Repeat` {.blockcontrol} loops;
	+ `Forever` {.blockcontrol} loops.

This project covers elements from the following strands of the [Raspberry Pi Digital Making Curriculum](http://rpf.io/curriculum):

+ [Use basic programming constructs to create simple programs.](https://www.raspberrypi.org/curriculum/programming/creator)

#Challenges
+ "Improving your animation" - altering the numbers in a short program;
+ "Make your own animation" - applying the learning to make a new animation.

#Frequently Asked Questions
+ Children may need reminding to 'reset' a sprite's position, size and other effects at the start of their animation. This can be easily achieved by adding some of the following blocks to the start of their animations:

```blocks
	go to x:(0) y:(0)
```

```blocks
	set size to (100)%
```

```blocks
	clear graphic effects
```

+ The 'spaceship' sprite will move sideways unless it is rotated 90 degrees clockwise. Rotating the spaceship is part of the project instructions, but another sprite can be substituted for the spaceship if this is causing problems.

	![screenshot](images/space-rotate.png)
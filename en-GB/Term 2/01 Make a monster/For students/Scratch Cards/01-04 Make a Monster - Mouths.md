---
title: Scratch Card - Mouths and talking
level: Level 4
language: en-GB
stylesheet: scratch
embeds: "*.png"
materials: "*.sb2"
...

## Activity Checklist {.check}

+ To make your monster talk, you can just use the `Say`{.blockpurple} sprite.
```blocks
	when [space v] key pressed
		say [Hello!] for (2) secs
```
+ To make it a bit more impressive, you could make the monsters **mouth open** and **close** whilst it is talking. To do this, edit the sprite that contains the mouth - create a new `costume`{.blockpurple} that has a closed mouth. By switching between the two, you can animate the mouth opening and closing.
```blocks
	repeat (8)
		wait (0.1) secs
		switch to costume [mouthClosed v]
		wait (0.1) secs
		switch to costume [mouthOpen v]
	end
```
+ To hook the two up, have the block that does the `say` {.blockpurple} broadcast a message that the other block can react to.
```blocks
	when [space v] key pressed
		broadcast [talk v]
		say [Hello!] for (2) secs

	when I receive [talk v]
		repeat (8)
			wait (0.1) secs
			switch to costume [mouthClosed v]
			wait (0.1) secs
			switch to costume [mouthOpen v]
		end
```
+ To make this a bit more flexible, use a variable to control the `talkTime`{.blockorange} the monster says something for, and also to control how many times the animation loop is repeated.
```blocks
	when [space v] key pressed
		set [talkTime v] to (2)
		broadcast [talk v ]
		say [Hello!] for (talkTime) secs

	when [a v] key pressed
		set [talkTime v] to (4)
		broadcast [talk v]
		say [Something a bit longer] for (talkTime) secs

	when I receive [talk v]
		repeat ((talkTime) * (4))
			wait (0.1) secs
			switch to costume [mouthClosed v]
			wait (0.1) secs
			switch to costume [mouthOpen v]
		end
```

**(Notice how we multiply `talkTime` by 4 to make sure the loop repeats enough times?)**

+ You can also make your monster speak using sound by using one of the sound blocks. Just be sure to import the sounds first in the sounds tab.
```blocks
	when I receive [talking v]
		play sound [Screech v]
```

Why not try adding sounds to other events, you could use a spooky hovering sound for a ghost drifting around the screen!

If you have a microphone on your computer you can even record your own sounds, surprise your classmates by recording a loud monster ROOOAAAAARRRRR!!!

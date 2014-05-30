---
title: Scratch Card - Wheels
level: Level 4
language: en-GB
stylesheet: scratch
embeds: "*.png"
materials: "*.sb2"
...

## Activity Checklist { .check}

+ To make a wheel appear to move, we want to **rotate** it by a small amount and move it by a small amount when we receive a **movement broadcast**.
```blocks
	when I receive [moved left v]
		change x by ((move speed) * (-1))
		turn ccw (15) degrees

	when I receive [moved right v]
		change x by (move speed)
		turn cw (15) degrees
```
+ If you wanted, you could replace the values with variables like `move speed`{.blockorange}, so you could control the speed in all directions from one place.

**(Notice how we have to multiply moveSpeed by -1 to get the negative value?)**

---
title: Scratch Card - Tentacles
level: Level 4
language: en-GB
stylesheet: scratch
embeds: "*.png"
materials: "*.sb2"
...

## Activity Checklist { .check}

+ To make a tentacle wiggle, we could **rotate** it and **resize** it by a `random`{.blockgreen} small amount using a variable, and then wait a short period before reverting back.
```blocks
	set [tentacleRotation v] to (pick random (1) to (10))
	set [tentacleSize v] to (pick random (1) to (10))
	change size by (tentacleSize)
	turn ccw (tentacleRotation) degrees
	wait (0.5) secs
	change size by ((tentacleSize) * (-1))
	turn cw (tentacleRotation) degrees
```

**(Notice how we multiply the tentacleSize by -1 to get the negative value?)**

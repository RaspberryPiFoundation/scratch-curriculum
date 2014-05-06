---
title: Scratch Card - Legs
level: Level 4
language: en-GB
stylesheet: scratch
embeds: "*.png"
materials: "*.sb2"
...

## Activity Checklist { .check}

+ Using two **leg sprites** we can make our monsters appear to walk. To do this we need to set up a **variable** that switches between two states, one for our leg swinging forward and another for backwards (we’ll reverse these states for the other leg).

To do this we need to first set up a `step`{.blockorange} variable, then every time our moving broadcast is received, **increase the variable by one**. If the variable goes higher than one (we can test this with the greater than operator `>`{.blockgreen}) we reset it back to **zero**.

```blocks
	when FLAG clicked
		set [move speed v] to [5]
		set [step v] to [0]

	when I receive [moved left v]
		change [step v] by [1]
		if < (step) > [1] >
			set [step v] to [0]
		end

	when I receive [moved right v]
	change [step v] by [1]
	if < (step) > [1] >
		set [step v] to [0]
	end
```
+ Now we can set our legs to swing by checking against our `step`{.blockorange} variable. **When the variable is set to zero** we can change the direction of our leg (here we’ve used a fixed `direction`{.blockblue} to stop our legs going mad if our variable and angle don’t match up, but maybe you want your monster to do that!).

Don’t forget to move you legs along with your body using your `move speed`{.blockorange} variable.

```blocks
	when I receive [moved right v]
		change x by (move speed)
		if < (step) = [0] >
			point in direction (180 v)
		else
			point in direction (165 v)
		end

	when I receive [moved left v]
	change x by ((move speed) * [-1])
	if < (step) = [1] >
		point in direction (165 v)
	else
		point in direction (180 v)
	end
```

**You could use the same sort of actions to make simple waving arms or even flapping bird wings.**

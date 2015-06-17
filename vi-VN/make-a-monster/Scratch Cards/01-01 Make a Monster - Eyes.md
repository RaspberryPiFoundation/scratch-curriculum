---
title: Scratch Card - Eyes
level: Level 4
language: en-GB
stylesheet: scratch
embeds: "*.png"
materials: "*.sb2"
...

## Activity Checklist { .check}

+ You can give your monster eyes that follow your mouse pointer all over the screen. Your monster can have as many eyes as you like, even eight like a spider! Because we always want our monster eyes to follow our mouse pointer we need to use the `forever`{.blockyellow} block. Once **green flag** scripts have started we `forever`{.blockyellow} want our eyes to point in the direction of the mouse and re-adjust every fraction of a second.
```blocks
	when FLAG clicked
		forever
			point towards [mouse pointer v]
			wait (0.2) secs

	when I receive [moved right v]
		change x by (move speed)

	when I receive [moved left v]
		change x by ((move speed) * (-1))
```

Notice we also use broadcast to move our eyes along with our body and other parts. What else can you make the eyes do? If you move your mouse cursor between your monster’s eyes, it will go cross eyed!

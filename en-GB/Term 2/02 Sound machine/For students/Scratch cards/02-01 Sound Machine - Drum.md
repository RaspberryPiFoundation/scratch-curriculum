---
title: Scratch Card - Drum
level: Level 5
language: en-GB
stylesheet: scratch
embeds: "*.png"
materials: "*.sb2"
...

## Activity Checklist { .check}

+ Import a new sprite and choose Things -> Drum. Name the sprite “Drum”.
+ We want the drum to make a sound when we click it or press the `space`{.blockbrown} key.
```blocks
    when this sprite clicked
        broadcast [drum v]

    when [space v] key pressed
        broadcast [drum v]
```

+ Now we need to make a sound when it receives `drum`{.blockbrown}. You can change the number if you want to change the sound the drum makes.
```blocks
    when I receive [drum v]
        play drum (48 v) for (0.2) beats
```

+ Try changing the appearance to make it obvious which instrument was played.
```blocks
    when I receive [drum v]
        play drum (48 v) for (0.2) beats
        set size to (110) %
        wait (0.1) secs
        set size to (100) %
```

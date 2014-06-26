---
title: Scratch Card - Piano
level: Level 5
language: en-GB
stylesheet: scratch
materials: "*.sb2"
...

## Activity Checklist { .check}

+ Draw a piano by creating black and white rectangles. ![costume1](piano-costume-1.png)
+ Now create a script which plays a note when the “a” key is pressed.
```blocks
    when [a v] key pressed
        broadcast [piano-1 v]

    when I receive [piano-1 v]
        play note (60 v) for (0.5) beats
```

+ Create two more notes when you press “s” and “d” on the keyboard.
```blocks
    when [a v] key pressed
        broadcast [piano-1 v]

    when [s v] key pressed
        broadcast [piano-2 v]

    when [d v] key pressed
        broadcast [piano-3 v]

    when I receive [piano-1 v]
        play note (60 v) for (0.5) beats

    when I receive [piano-2 v]
        play note (64 v) for (0.5) beats

    when I receive [piano-3 v]
        play note (67 v) for (0.5) beats
```

+ Copy the costume 3 times. Fill in a different key on each one. ![costume3](piano-costume-3.png) ![all costumes](piano-costumes.png)
+ Make each note switch to a different costume and then switch back to `costume1`{.blockblue}.
```blocks
    when I receive [piano-1 v]
        switch to costume [costume2 v]
        play note (60 v) for (0.5) beats
        switch to costume [costume1 v]

    when I receive [piano-2 v]
        switch to costume [costume3 v]
        play note (64 v) for (0.5) beats
        switch to costume [costume1 v]

    when I receive [piano-3 v]
        switch to costume [costume4 v]
        play note (67 v) for (0.5) beats
        switch to costume [costume1 v]
```

# Challenge: Create a way to change the instrument.

```blocks
    when [up-arrow v] key pressed
        set instrument to (pick random (1) to (99))
```

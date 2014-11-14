---
title: Simone Ballerina
level: Level 2
language: en-GB
stylesheet: scratch
...

# Introduction { .intro }

In this project, you will create a memory game where you have to memorise and repeat a sequence of random colours!

![screenshot](finished_screenshot.png)

# Step 1: Create a random colour sequence { .activity }

Let’s generate the random sequence. We also want to make the ballerina's dress flash different colours to represent the sequence.

## Activity Checklist { .check }

+ Start a new Scratch project. Delete the cat by right clicking it and clicking **Delete**.
+ Replace the background of the stage with **Indoors/spotlight-stage**.
+ Select a main character for the game. If you really don't want a ballerina then choose something else. It doesn't have to be a person, but it needs to be able to show different colours.
+ Create 4 costumes for you sprite and edit the main colour of them using the *Fill tool* to be different.
+ Rename your character to something memorable E.g. Simone
+ In Variables *Make a list* called *sequence* *For this sprite only*

```blocks
when FLAG clicked
delete (all v) of [sequence v]
repeat (4)
    add (pick random (1) to (4)) to [sequence v]
    switch to costume (item (last v) of [sequence v]
    wait (1) secs
```

## Test Your Project { .flag }

Click the green flag.

+ Does the dress change colour 4 times?
+ Is it hard to tell when you get the same colour twice in the sequence?

## Things to try { .try }

+ Try playing a sound after each costume change, so that you can tell if it is the same colour twice in a row.

## Save your project { .save }

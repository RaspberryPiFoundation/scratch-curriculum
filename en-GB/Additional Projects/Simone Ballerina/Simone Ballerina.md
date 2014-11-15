---
title: Simone Ballerina
level: Level 2
language: en-GB
stylesheet: scratch
embeds: "*.png"
...

# Introduction { .intro }

In this project, you will create a memory game where you have to memorise and repeat a sequence of random colours!

![screenshot](finished_screenshot.png)

# Step 1: Create a random colour sequence { .activity }

Let’s generate the random sequence. We also want to make the ballerina's dress flash different colours to represent the sequence.

## Activity Checklist { .check }

+ Start a new Scratch project. Delete the cat by right clicking it and clicking **Delete**.
+ Replace the background of the stage with a background from Indoors, **spotlight-stage**.
+ Select a main character for the game. If you really don't want a ballerina then choose something else. It doesn't have to be a person, but it needs to be able to show different colours.
+ Create 4 costumes for you sprite and edit the main colour of them using the *Fill tool* to be different.
+ Rename your character to something memorable E.g. **Simone**
+ In Variables, make a list `For this sprite only` {.blockgrey} and call it `sequence` {.blockorange}.

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

# Step 2: Add buttons to input the sequence guess { .activity }

Now we need to add some coloured drums so you can enter in your guess at the sequence.

## Activity Checklist { .check }

+ Import a new sprite **Things/drum2**
+ Make the sprite a bit smaller by clicking on the `Shrink sprite` {.blockgrey} icon and then on the drum several times.
+ Rename the sprite *BlueDrum*
+ Using the `Fill tool` {.blockgrey} again, edit the costume so that the top of the drum is blue.
+ Add the following code to send a message to Ballerina

```blocks
when this sprite clicked
broadcast [BlueClicked v]
```

+ Duplicate the drum sprite 3 times
+ Edit the colour of each drum
+ Rename each one after it's colour
+ Create a new broadcast message for each one

## Save your project { .save }

# Step 3: Check if the guess is correct { .activity }

Now we need to return to the *Ballerina* sprite, and add some code to receive the messages and check our guesses.

```blocks
when I receive [BlueClicked v]
if <(item (1 v) of [sequence v])=[1]>
    delete (1 v) of [sequence v]
else
    say [Wrong!] for (1) secs
```

You will need 4 copies of this script, one for each colour message. The numbers to use to compare with the list item can be seen by looking at the `Costumes`, and seeing the numbers you have for each colour.

![screenshot](costume_numbers.png)
![screenshot](receiver_code.png)

## Test Your Project { .flag }

Click the green flag.

+ Can you get the sequence right?
+ Do all the buttons work as expected?
+ When you make an incorrect guess, does the ballerina say Wrong?

## Things to try { .try }

+ It is slightly too easy to remember the last colour in the sequence as the ballerina remains in that colour dress. Can you make the ballerina change to a white dress when she has finished the sequence?
+ When you make a correct guess, it sometimes feels like nothing is happening. Can you play a sound when you click on a drum? or maybe a different sound for each drum?

## Save your project { .save }

# Step 4: Let's celebrate success { .activity }

If you get the sequence correct, it would be nice if the game did something exciting! Let's add the following script to the **Stage**

```blocks
when I receive [Won v]
play sound [Eggs v]
repeat (90)
    change [color v] effect by (25)
    wait (0.1) secs
end
clear graphic effects
```

You can see what it does by double clicking on it. Disco!

When you get tired of that excitment, let's move on. We need to create a way to detect if we've completed the sequence and broadcast the *Won* message. Add the following code to 

```blocks
when I receive [CorrectGuess v]
delete (1 v) of [sequence v]
if <(length of [sequence v])=[0]>
    broadcast [Won v]
```

And we need to edit each of the 4 receiver codes to broadcast CorrectGuess rather than delete an item from *sequence*.

```blocks
when I receive [BlueClicked v]
if <(item (1 v) of [sequence v])=[1]>
    broadcast [CorrectGuess v]
else
    say [Wrong!] for (1) secs
```

## Save your project { .save}

## Things to try { .try}

+ __Make the game start again after you win__
+ __Make the sequence get longer each time__
+ __Can you make the game end if you make an incorrect guess, and display a final score?__
+ __Well done you’ve finished the basic game. There are more things you can do to your game though. Have a go at these challenges!__

---
title: Scratch Table Football
level: Level 3
language: en-GB
stylesheet: scratch
embeds: "*.png"
materials: ["Resources/*.png", "Resources/whistle.mp3", "Resources/pitch.jpg"]
...

# Introduction { .intro }

It’s the Football World Cup! So to celebrate, let’s make a world cup football game in Scratch!

![screenshot](scratch_table_football_screenshot.png)

# Step 1: Get the pitch ready for a game { .activity }

## Activity Checklist { .check }

+ Start a new project in Scratch.
+ Click on the **stage** next to the sprite and switch to the `Backdrops` tab, then click the `Upload backdrop from file` button and choose the **resources/pitch.jpg** file.
+ Delete the original blank backdrop, and the cat sprite.
+ Our goals need nets! Create a sprite using the `Upload sprite from file` button and select **resources/net.png**. Move the net into the middle of the goal on the left. Rename it **blue goal**.
+ Right-click on the net sprite and click `duplicate`, then move this new sprite to the goal on the right and rename it **red goal**.

## Save your project { .save }

# Step 2: Add a goalie { .activity }

Okay – our pitch is looking good! Now let’s add some players and get them moving about.

## Activity Checklist { .check }

+ Click on `Upload sprite from file` and choose **resources/goalie_blue.png**. Rename the sprite **blue goalie**, and drag it near to the left goal.
+ Click on the `grow sprite` button, and click on the **blue goalie** sprite 10 times to scale up the sprite.
+ Click on the `Scripts` tab, and add:
```blocks
    when FLAG clicked
    go to x: (-190) y: (0)
    forever
        if <<key [q v] pressed?> and <(y position) < [80]>>
            change y by (5)
        end
        if <<key [a v] pressed?> and <(y position) > [-80]>>
            change y by (-5)
        end
    end
```
  Let’s look at the code.  We position the goalie, then we loop forever listening for key presses from the player. **Q** moves the goalie up, **A** moves it down. We check the `y position` { .blockblue } of the goalie to stop it moving off the screen.

## Test your project { .flag }

Click the green flag.

+ Can you control the goalie by pressing Q and A?
+ What happens when it gets to the edges of the pitch?

## Save your project { .save }

# Step 3: Add some more players { .activity }

We can’t play a game of football with just one player! We need to add some more.

## Activity Checklist { .check }

+ Create another sprite using the `Upload sprite from file` button and selecting **resources/goalie_red.png**.
+ Change the name of the sprite to **red goalie**.
+ Drag the sprite on the stage to the right-hand side just in front of the goal.
+ Like before, grow the sprite 10 times so it is as big as the other goalie.
+ Select the **blue goalie** sprite and drag the script to **red goalie** to duplicate it.
+ Select **red goalie**, and modify the script so it looks like this:
```blocks
    when FLAG clicked
    go to x: (190) y: (0)
    forever
        if <<key [p v] pressed?> and <(y position) < [80]>>
            change y by (5)
        end
        if <<key [l v] pressed?> and <(y position) > [-80]>>
            change y by (-5)
        end
    end
```
  You should only have to change three things: the `x position` { .blockblue }, and which keys are pressed.

## Test your project { .flag }

Click the green flag.

+ Can you control the red goalie by pressing P and L?
+ Do the controls for the blue goalie still work?

## Save your project { .save }

# Step 4: Add some attacking players { .activity }

## Activity Checklist { .check }

+ Create another sprite using the `Upload sprite from file` button and selecting **resources/attack_blue.png**. Rename the sprite **blue attack**.
+ As before, grow the sprite 10 times, so the players are as big as the goalies.
+ Move the sprite into the right-hand side of the pitch, so they are attacking the red team’s goal.
+ Drag the script from **blue goalie** to **blue attack**, and modify it to match this:
```blocks
    when FLAG clicked
    go to x: (70) y: (0)
    forever
        if <<key [w v] pressed?> and <(y position) < [80]>>
            change y by (5)
        end
        if <<key [s v] pressed?> and <(y position) > [-80]>>
            change y by (-5)
        end
    end
```
  You should only have to change three things: the `x position` { .blockblue }, and which keys are pressed.
+ Create one more sprite using the `Upload sprite from file` button and selecting **resources/attack_red.png**. Rename sprite to **red attack**.
+ As before, grow the sprite 10 times, so all the players on the pitch are the same size.
+ Move the sprite into the left-hand side of the pitch, so they are attacking the blue team’s goal.
+ Drag the script from **blue attack** to **red attack**, and modify it to match this:
```blocks
    when FLAG clicked
    go to x: (-70) y: (0)
    forever
        if <<key [o v] pressed?> and <(y position) < [80]>>
            change y by (5)
        end
        if <<key [k v] pressed?> and <(y position) > [-80]>>
            change y by (-5)
        end
    end
```
  You should only have to change three things: the `x position` { .blockblue }, and which keys are pressed.

## Test your project { .flag }

Click the green flag.

+ Do you have two teams of working players now? Try pressing Q, A, W and S to control the blue team, and P, L, O and K to control the red team.

## Save your project { .save }

# Step 5: Add a bouncing ball { .activity }

Our game of _football_ has **feet**, but no **ball!** Let’s fix that.

## Activity Checklist { .check }

+ Click `Upload sprite from file`
+ Select **resources/ball.png**, and rename the sprite **ball**.
+ In the `Scripts` tab for the ball, add the following:
```blocks
    when FLAG clicked // bounce about
    broadcast [resetball v]
    forever
        move (10) steps
        if on edge, bounce
    end
```
+ Right-click on this script and click `add comment`. Add the comment **“bounce about”**.
+ Add another script to the ball:
```blocks
    when I receive [resetball v] // prepare for kick-off
    go to x: (0) y: (0)
    point in direction <pick random (1) to (360)>
```
  This tells the ball to move to the middle of the pitch for kick-off, and then point in a random direction. Why do we use `resetball` { .blockorange }?
+ Don’t forget to add the **“prepare for kick-off”** comment, so we remember what this script does!

## Test your project { .flag }

Click the green flag.

+ Does the ball move?
+ What happens when it hits the edges?
+ Are you happy with the ball speed? Try changing the `move` { .blockblue } block to have a smaller or larger number until you’re happy with it.
+ What happens when the ball hits your players?

## Save your project { .save }

# Step 6: Kicking the ball { .activity }

We need the ball to bounce off the players on the pitch.

+ Modify the last code block you created (**“bounce about”**) to look like this:
```blocks
    when FLAG clicked // bounce about
    forever
        move (10) steps
        if on edge, bounce
        if <<touching color [#0A9AF7]?> or <touching color [#FF0D01]?>>
            turn cw (pick random (140) to (220)) degrees
        end
    end
```
  You should select the colours by clicking on the football players. This change makes the ball sense it is touching a player, and then bounce off them by turning (with a bit of randomness).

## Test your project { .flag }

Press the green flag.

+ What happens now when the ball hits your players? Is it working for both red and blue players?

## Save your project { .save }

# Step 7: GOOOOOOAAAAAALLLLLLLLL!!!!!!!! { .activity }

## Activity Checklist { .check }

+ Select **red goal** and add the following script:
```blocks
    when FLAG clicked // goal line technology
    forever
        if <touching [ball v]>
            broadcast [goal v]
        end
    end
```
  This is like goal line technology - it runs all the time, checking whether the ball is touching the goal, and broadcasting a message when it is.
+ Drag the script to **blue goal** to copy it there as well.
+ Now we need to do something when **goal** is broadcast. Click `Upload sprite from file`.
+ Select **resources/goal_text.png**, and rename the sprite **goal text**.
+ Add this script to **goal text**:
```blocks
    when I receive [goal v] // goal scored
    show
    wait (1) secs
    hide
```
+ Finally, add one more script to **goal text**:
```blocks
    when FLAG clicked
    hide
```
  …to ensure the **goal text** begins the game hidden.

## Save your project { .save }

## Test your project { .flag }

You’re ready to play a game! Press the green flag.

+ What happens when the ball goes in?
+ Try challenging a partner to a game!

## Challenge 1: Keep score { .challenge }

Can you add variables that will keep track of scores for the red and blue teams?

## Challenge 2: Tip the table { .challenge }

You might notice sometimes the ball gets stuck bouncing where the players can’t reach. Can you add a script to the ball to fix this by “tipping the table” when the spacebar is pressed?

## Challenge 3: Referee’s whistle { .challenge }

Can you add the sound effect **resources/whistle.mp3** so that the whistle sounds whenever a kick-off takes place?

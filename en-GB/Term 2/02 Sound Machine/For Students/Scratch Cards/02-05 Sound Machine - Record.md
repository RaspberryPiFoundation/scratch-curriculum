---
title: Frantic Felix - Record
level: Level 6
language: en-GB
stylesheet: scratch
embeds: "*.png"
...

## Activity Checklist { .check}

1.  Get ready

    Press Make a list to make a new list.

    ![](variable.png)


2.  Try this code
 
    Empty the list when you start.

    ```scratch
    when flag clicked
    delete (all v) of [notes v]
    ```

3.  Every time something happens, add it to the list.

    ```scratch
    when this sprite clicked
    play note (pitch) for (0.5) beats
    add (pitch) to [notes v]

    ```

4.  If you want to record several things, use one list for each.

    ```scratch
    when [space v] key pressed
    move (10) steps
    add (x position) to [xs v]
    add (y position) to [ys v]

    ```

6. See the “Play back a sequence” card for how to replay what you’ve recorded.

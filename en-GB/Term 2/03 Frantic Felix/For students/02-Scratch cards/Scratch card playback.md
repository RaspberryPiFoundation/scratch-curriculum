---
title: Frantic Felix - Playback
level: Level 6
language: en-GB
stylesheet: scratch
embeds: "*.png"
...

## Activity Checklist { .check}

1.  Get ready
    
    Press Make a variable to make an index variable
    
    ![](variable.png)


2.  Try this code
    
    Make the sprite follow the path it recorded.

    ```scratch 
    when I receive [replay v]
    set [index v] to [1]
    repeat (length of [xs v])
        set x to (item (index) of [xs v])
        set y to (item (index) of [ys v])
        change [index v] by (1)
        wait (0.1) secs
    
    ```

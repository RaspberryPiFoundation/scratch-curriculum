---
title: Scratch Card - Recorder
level: Level 5
language: en-GB
stylesheet: scratch
embeds: "*.png"
materials: "*.sb2"
...

## Activity Checklist { .check}

+ Create two new lists (for all sprites). Call one of them `instrument`{.blockred} and the other `timing`{.blockred}.
+ Create a new variable (for all sprites) called `recording`{.blockorange}
+ For each of your instruments (drum, piano, each sound sample etc.), you will need to add the following items to the `when I receive`{.blockbrown} block.
```blocks
    if <(recording) = (1)>
        add (timer) to [timing v]
        add (cat) to [instrument v]
```

+ Change the word “cat” in `add [cat] to [instrument v]`{.blockred} to match the name of the message used to play this sound.
```blocks
    when I receive [drum v]
        play drum (48 v) for (0.2) beats
        if <(recording) = (1)>
            add (timer) to [timing v]
            add (cat) to [instrument v]
        end
        set size to (110) %
        wait (0.1) secs
        set size to (100) %
```

+ Draw a new sprite and give it a red circle costume. Name this sprite “Record”. ![record costume](record-costume.png)
+ Create a script that sets `recording`{.blockorange} to 1 and deletes all of `instrument`{.blockred} and `timing`{.blockred} when clicked.

## Test your project {.flag}

Try clicking the record button. What happens when you play instruments?

+ Create another sprite and give it a costume in the shape of a green arrow.  Call this “Play”. ![play costume](play-costume.png)
+ Create a new variable called `index`{.blockorange} for Play only.
+ Now we need to make the playback actually do something. Add this script to "Play"
```blocks
    when Play clicked
        set [recording v] to (0)
        set [index v] to (1)
        reset timer
        forever
            if <(item (index) of [timing v]) < (timer)>
                broadcast (item (index) of [instrument v])
                change [index v] by (1)
                if <(index) > (length of [timing v])>
                    stop script
                end
            end
        end
```

## Test your project {.flag}

Press the green play button. what happens?

Now click the red record button and play some instruments. When you're done, press the green play button again. What happens?

Play some more instruments without pressing record. Then play the green play button again. What happens?

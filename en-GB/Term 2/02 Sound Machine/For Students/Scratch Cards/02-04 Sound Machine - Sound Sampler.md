---
title: Scratch Card - Sound Sample
level: Level 5
language: en-GB
stylesheet: scratch
embeds: "*.png"
materials: "*.sb2"
...

## Activity Checklist { .check}

+ Create a new sprite and make it resemble the sound you will be making.
+ In the `sounds`{.blocklightgrey} tab, create a new recording or import a sound.
![cat sound sample](sound-sample.png)
+ When the sprite is clicked, `broadcast`{.blockbrown} the same name as your sprite.
```blocks
    when Cat clicked
        broadcast [cat v]
```

+ Now we need to play the `sound`{.blockpurple} when it receives the `broadcast`{.blockbrown}.
```blocks
    when I receive [cat v]
        play sound [cat v]
```

+ Finally, make the sprite change in appearance when the `sound`.{blockpurple} is played.
```blocks
    when I receive [cat v]
        play sound [cat v]
        set size to (110) %
        wait (0.1) secs
        set size to (100) %
```

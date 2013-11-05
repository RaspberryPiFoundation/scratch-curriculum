#NOTES FOR CLUB LEADERS
##(Paint Box)

###Introduction

The project creates a basic drawing tool. It draws a line as you move your mouse over the screen. You can change the colour of the line and clear the screen.

###Skills

This project covers

* Moving sprites
* Drawing with the pen
* Broadcasting and listening for events
* Changing costumes
* Setting constraints
* Constructing and using Boolean expressions

###Resources

This project uses resources found in this project folder. Make sure this folder is on the desktop of each computer your children are using so they can access it.

##Basic exercises

Step 1: Drag and draw

Step 2: Clearing up

Step 3: Changing colour

Step 4: Only drawing inside the border Step 5: Eraser

Step 6: Stamps

##Challenges

1. Rainbow pencil
2. Keyboard shortcuts 3. Big and small

##Some things to be aware of

Some people have reported that they had an issue with getting the pen to draw a consistent line. This is because when the stage is not full screen, the act of clicking on a sprite and dragging is captured by the Scratch environment because it assumes you are trying to move the sprite, so the events are not handled by your code correctly. (If this is the problem you were seeing, you'll find that running the paintbox in full screen makes the problem go away).
The solution? When you edit the pencil sprite and 'Set costume center' in step 1, make sure you set the center to be a transparent pixel (i.e. a point just left and down from the tip of the pencil). By doing this, when your code moves the sprite to the cursor's position, the mouse drag won't get captured by the Scratch environment.



---
layout: post
comments: false
title:  "04-Setting up the player area"
date:   2016-04-09 01:40:47
tags: [unity3d]
excerpt_separator: <!--more-->
---
<iframe width="560" height="315" src="https://www.youtube.com/embed/dahT0wRVO1Q" frameborder="0" allowfullscreen></iframe>

So let's set up our play field.

The play field for our game will be very simple.

We will place walls around the edges
to keep our player game object from falling off
and we will create and place a set of collectable
objects for our player to pick up.
<!--more-->
First let's create a new game object
and rename it Walls.

This will be an organising parent game object
for our Wall objects.

Reset this game object to origin.

Now we will build our walls.

Let's start by creating a new cube
to be our first wall.

Rename this West Wall.

Reset this game object to origin.

Now parent West Wall to our Walls game object.

Let's focus our Scene view camera
to our Wall object.

We can do this by typing the F key
while the cursor is over the Scene view
or by selecting Edit - Frame Selected.

We need to change the size of the cube to fit
one side of our play area.

Change the cube's transform scale of X, Y and Z to
.
5 for thin, 2 for tall and 20.
5 for long.

Now we can simply push the wall in to place
using the Translate tool
or we could enter a value in to the transform component.

In this case we can set the transform's
position X value to -10.

This places the wall neatly to the edge of our play area.

To create the next wall we could
start with another new cube,
but then we'd have to rescale this
new cube before we placed it.

Our current West Wall is already the perfect size.

So let's duplicate the West Wall game object.

Let's rename it East Wall.

To place the wall simply remove the negative sign
and it pops in to place on the east side of our game area.

Now let's duplicate the east wall
and call it North Wall.

Reset the X position so the north wall
is in the centre of the play area.

We now have two choices.

We can rotate the wall by 90 degrees,
or, as this is a cuboid,
we can rescale the wall to 20.
5 in the X and 0.
5 in the Z.

Now it's scaled correctly for it's orientation
as the north wall.

We can drag the wall in to place,
or we can simply use the value of 10
in the transform's position Z field to place it.

Duplicate North Wall and call it South Wall,
and -10 in the Z axis pops it in to place.

Enter play mode and test.

Fantastic, the walls work fine.

Remember to test early and test often,
don't wait to test.

Let's exit play mode.

Let's highlight the Player game object
and set the editor to Local mode,
and try again.

Note how in Local mode we can see the transform rotate.

Let's exit play mode.

In the next episode we will be creating
our collectable pickup object.

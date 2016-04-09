---
layout: post
comments: false
title:  "03-Moving the camera"
date:   2016-04-09 01:40:46
tags: [unity3d]
excerpt_separator: <!--more-->
---
<iframe width="560" height="315" src="https://www.youtube.com/embed/Xcm5H2J95iI" frameborder="0" allowfullscreen></iframe>

The camera doesn't move and from it's current position
cannot see very much.

We need to tie the camera to the player game object.

First let's set the position of the camera.
<!--more-->
Let's lift it up by 10 units and tilt it
down by about 45 degrees.

Next let's make the camera a child of the
player game object.

This is a typical third-person setup,
with the camera as a child of the player.

When we move the player's position
the camera moves with it.

When the player rotates the camera rotates as well.

Let's look at this from a position where we
can see both the player and the camera game object.

Move the player,
rotate the player,
the child camera moves with it.

Now let's reset the player and test.

We enter play move, hold down the up arrow to move,
Whoa what's happening here?
Okay, well as the camera is a child of the player's sphere,
even thought the camera is not moving at all
relative to the player's game object,
the player game object is rotating like crazy
so the camera's point of view rotates with it.

Let's exit play mode.

Unlike a normal third-person game
our player game object is rotating on all 3 axis
not just 1.

In a typical third-person setup
the camera as a child of the player game object
will always be in a position relative
to it's immediate parent,
and this position will be the parent's
position in the game, modified or offset by
any values in the child's transform.

We can't have the camera as a child of
the player, so let's detach it.

Our offset value will be the difference
between the player game object and the camera.

Now we need to associate the camera with
the player game object, not as a child
but with a script.

Using the Add Component button choose New Script.

We are writing in C#
and name the script CameraController
and then click on Create and Add
or simply hit the return or enter key
to confirm our selection.

We should note, this way of creating a script
will create that script asset on
the root or top level of our project view.

File CameraController in the Scripts folder
and open it for editing.

We need 2 variables here.

A public GameObject reference to the player
and a private vector3 to hold our offset value.

Offset is private because we can
set that value here in the script.

For our offset value we will take the
current transform position.

and subtract the transform position of the player
to find the difference between the two.

So in start we can make offset equal to our
transform position minus the player's transform position.

And then every frame we set our
transform position to our player's transform position
plus the offset.

This means as we move our player
with the controls on the keyboard
that each frame before displaying what the camera can see
the camera is moved in to a new position
aligned with the Player object.

Just as if it were a child of that object
if it were not rolling around the game board.

However, update is not the best place for this code.

It is true that update runs every frame
and in update each frame we can track
the position of the player's game object
and set the position of the camera.

However, for follow cameras, procedural animation,
and gathering last known states
it's best to use LateUpdate.

LateUpdate runs every frame, just like update.

But it is guaranteed to run after all items
have been processed in update.

So when we set the position of the camera
we know absolutely that the player has moved for that frame.

So let's test this.
 Let's save our script
and return to Unity.

First we need to create a reference to the
player game object by dragging the player
game object in to the Player slot
in the camera controller's component.

Enter play mode
and now we get the behaviour we want.

The camera follows the rolling ball
without rotating
even as the ball goes over the edge.

In the next assignment we will setup the basic
play area and create and place our
special pick-up objects.

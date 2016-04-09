---
layout: post
comments: false
title:  "05-Creating collectable objects"
date:   2016-04-09 01:40:50
tags: [unity3d]
excerpt_separator: <!--more-->
---
<a href="http://www.youtube.com/watch?feature=player_embedded&v=RFlh8pTf4DU
" target="_blank"><img src="http://img.youtube.com/vi/RFlh8pTf4DU/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="502" height="300" border="10" /></a>

Next let's create our collectable objects.

Create a new cube
and rename it PickUp.

Reset the Pickup's transform to origin.

Focus the scene view camera on the Pickup object.
<!--more-->
The Player game object is in the way.

Let's select the Player game object
and deselect the checkbox in front of the Name field.

This is the game object's Active checkbox.

Deselecting it will deactivate the game object in the scene.

This will give us a clear working space
for our new Pickup object.

The cube is buried in the plane, just like our player
sphere was when we started this project.

The cube is also a regular shape, 1 by 1 by 1.

So let's lift it up by half a unit
and we know it's resting on the plane.

This cube will be our Pickup object.

To be effective it must attract the attention of the Player.

So let's make the cube more attractive.

We will start by making it smaller.

This will also give it the effect of floating in above the play area.

Both will help identify this object as special.

Not enough however.

Let's tilt it over.

45, 45, 45 in each of the axis
of the transform's rotation.

Better, but not sexy enough.

One thing I feel certainly attracts the attention of a player,
and that is movement.

So let's rotate the cube.

To do this we need a script.

With the Pickup object selected
use the Add Component button in the Inspector.

Create a new script called Rotator.

Click Create and Add to confirm.

Organise the script by placing it in the Scripts folder,
and open it for editing.

We want the cube to spin,
and we want to do it with this script.

Let's remove the sample code we don't need.

We will not be using forces, so we can use
update rather than fixed update.

We have already set the transform rotation
in the transform component to 45, 45, 45
for the X, Y and Z axis.

But these values don't change by themselves.

We want to change these values every frame.

To make the cube spin we don't want to
set the transform rotation,
but we want to rotate the transform.

Next type Transform inside update.

Select it and hold down the control key on the PC
or the command key on the Mac
and type single quote.

Again, this brings up the page with a search term Transform.

Select Transform.

This brings up the Transform page in the documentation.

There are two main ways to effect the transform.

These are Translate and Rotate.

Translate moves the game object by it's transform.

Rotate rotates the game object by it's transform.

We will use Rotate.

So let's click on the link,
and this brings up the page for Transform Rotate.

Note again the two signatures
and the two possible overrides.

One using a vector3 and the other using
three float values for X, Y and Z.

Both overrides have the optional parameter Space.

Which we will leave at Default for this lesson.

Again we will choose the most simple
form that only uses the vector3 for direction.

Let's return to our code.

After transform, and make sure transform is written
to begin with a lowercase T,
write Rotate (new Vector3 (15, 30, 45)
Now this action also needs to be smooth
and frame rate independent.

So we need to multiply the vector3 value
by Time.
deltaTime.

Save this script and return to Unity.

Test by entering play mode, and our Pickup object rotates.

Let's exit play mode.

Okay, we have the start of a working Pickup object.

Next we want to place these around the game area.

But before we do this we need to do one important step.

We need to make our Pickup object in to a prefab.

So remember, a prefab is an asset that contains a template,
or blueprint of a game object or game object family.

We create a prefab from an existing game object
or game object family, and once created,
we can use this prefab in any scene in our current project.

With a prefab of our Pickup object
we will be able to make changes to a single
instance in our scene,
or to the prefab asset itself,
and all of the Pickup objects in our game
will be updated with those changes.

So first let's create a folder to hold our prefabs.

We want this folder on our root, or top level of our project.

So select the project view
and make sure that no other item or directory is highlighted.

And then choose Create - Folder
Rename this folder Prefabs.

Now drag the Pickup game object from our hierarchy
and place it in to our Prefabs folder.

When we drag an item from our hierarchy
in to our project view we create a new prefab asset
containing a template, or blueprint
of our game object or game object family.

Before we spread our collectables around the game area
we should create a new game object
to hold our Pickups and to help organise our hierarchy.

Let's create a new game object
and call it Pickups.

Check to make sure this parent game object is at origin
and drag our Pickup game object in to it.

Now we want to spread a number of these Pickup
objects around the play area.

First, make sure we have the Pickup game object
selected, not the parent.

Now let's move in to a top-down view
by clicking on the gizmo in to upper-right of our scene view.

Let's back out a little so we can see the entire game area.

Grab the Pickup game object,
and it doesn't move in the scene the way we want it to.

Note how the cube is moving in relation to
it's gizmo, which is tilted over.

What we are seeing is the game object moving in local mode.

We really want to move the Pickup game object
aligned with the ground.

Change the editor to Global mode.

Now see how the orientation of the gizmo changes?
And now we can drag our game object around
relative to the world's global axis.

So let's lay down a few of these in the game area.

Take our first Pickup object
and place it in to the game area, some place convenient.

I'm going to place mine at the top.

With the game object selected, duplicate it.

This can be done either by selecting Edit - Duplicate
or by using the hot key combination, this is command-D on the Mac
or control-D on the PC.

Now we place the second instance of the prefab.

Using the hot keys we will create a few more,
placing them around the play area.

Note that I'm moving parallel to the ground or the X/Z plane
by selecting the X/Z plane at the centre of the gizmo.

Okay, that's 12.

Let's hit play and test.

Excellent.

These Pickup prefabs are working great.

The only thing that I want them to do now
is stand out more against the background
walls and Player game object.

Let's change their colour/
To do this we need another material.

To make things easy we can simply
select our existing material and duplicate it.

Let's rename this new material Pickup.

With the material selected in the project view
let's change the albido colour property to yellow.

Now we can change the colour of the prefab
by changing the prefab's material.

We can do this in two ways.

We can change the material on just
one instantiated prefab
If we do this we must remember to
use the Apply button to apply
those changes to the prefab asset.

Otherwise we will only change the material
on this single instance.

The other way, which is perhaps more simple
is to simply change the material on the
prefab asset directly.

Let's hit play and test.

There, that looks better.

In the next assignment we will learn how to
pick them up and count them.

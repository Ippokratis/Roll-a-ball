---
layout: post
comments: false
title:  "01-Setting up the game"
date:   2016-04-08 14:40:46
tags: [unity3d]
excerpt_separator: <!--more-->
---


Let's begin by creating a new project.

We can create a new project from File - New Project.
This will bring up the home screen.

![Create new project]({{site.baseurl}}/images/posts/01/01-create-new-project.gif){: cssStuff}

I'm going to call the new project Roll a Ball.
<!--more-->
The next thing we need to do is set the destination,
or path to our new project.
I'm going to put this new project on my desktop.
At this point it's worth noting that we can
have our new project use default settings
for either a 2D project or a 3D project.
We will choose 3D.
And then I will click on Create Project
to make a new project.
We now have our new project with a new empty scene.

![New project setup]({{site.baseurl}}/images/posts/01/02-new-project-setup.gif)

Before creating anything in the new scene
we need to save our scene.
We can save our scene by going to File - Save Scene
or by using the keyboard shortcut (Ctrl-S for Windows, Option-S for Mac).

![Save scene]({{site.baseurl}}/images/posts/01/03-save-scene.gif)

I'm going to save this scene in the Assets directory
in a new folder called _scenes.
The underscore is optional, I use it to sort this
folder to the top of my project window.
Now I'm going to call the scene MiniGame.

![Save scene dialog]({{site.baseurl}}/images/posts/01/04-save-scene-dialog.gif)

We can now see in our Scenes folder
the scene called MiniGame.

![Save scene result]({{site.baseurl}}/images/posts/01/05-save-scene-result.gif)

Let's create our game board, or play field.

To do this we will use a stock Unity plane.
We can create this plane from either
Game Object - 3D Object - Plane,
![Create plane from the menu]({{site.baseurl}}/images/posts/01/06-create-plane-menu.gif)
 
or from inside the Hierarchy view using the Create menu.

![Create plane from the Hierarchy]({{site.baseurl}}/images/posts/01/07-create-plane-hierarchy.gif)

Rename this game object Ground.
We can do this by either selecting the game object
and using the enter or return keys
to allow editing, or by clicking on the
game object twice, slowly.
Type in the new name or hit enter or return
to confirm this change.

![Rename plane]({{site.baseurl}}/images/posts/01/08-rename-plane.gif)

Reset the transform component using the context
sensitive gear menu in the upper right.
This will place the game object at the location of
(0, 0, 0) in our scene.
This point is known as the origin point
of the world and this is where all of the
coordinates in the scene are calculated from.

![Resetplane]({{site.baseurl}}/images/posts/01/09-reset-plane.gif)

Now with the game object selected and the
cursor over the Scene view type the F key, or choose
Frame Selected from the Edit menu
to see the entire game object in the Scene view.

![Frame selected]({{site.baseurl}}/images/posts/01/10-frame-selected-menu.gif)

Looking at our current scene,
we can see grid lines indicating the plane at origin.
For the purposes of this project
we will turn them off.
Select the Gizmos menu in the Scene view
and deselect Show Grid.

![Hide grid]({{site.baseurl}}/images/posts/01/11-hide-grid.gif)

We need to change the scale of the ground plane.
We can do this in a number of ways.
We can use the Scale tool,
simply grab the axis handle you want to change
and drag the handle rescaling the plane.
We can click and drag on the title of
the fields we want to change.

![Resize plane in scene view]({{site.baseurl}}/images/posts/01/12-resize-plane-in-scene.gif)

Or we can type a number directly in to the
field we want to change.
You can tab between fields and hit enter or return
to confirm your choice.

![Resize plane in the inspector]({{site.baseurl}}/images/posts/01/13-resize-plane-in-inspector.gif)

Now remember a plane has no volume
and scale does not work on the Y axis.
There will be no change unless you go in to negative numbers.
In this case the plane, which is a single
sided object will simply face the other direction.
If you place a plane in the scene and you can't see it
check your orientation between the plane and camera
and make sure that you have the correct values
for the Y axis of scale.
This is usually the value of 1.

Let's create our player object.

In this assignment our player object
will be a Unity sphere.
From the Hierarchy - Create menu select Sphere.
Rename the sphere Player.

![Create and name the player]({{site.baseurl}}/images/posts/01/14-create-player-object.gif)

Reset the transform to make sure it's a origin.
Select Edit - Frame Selected
or use the F key while the cursor is
over the Scene view to focus our Scene view
camera on our game object.
See how the sphere is buried in the plane?
This is because both game objects
are in the exact same location in the scene,
the origin point, or (0, 0, 0)
on the X, Y and Z axis.
We need to move the player's sphere up
until it rests on the plane.

All Unity primitive objects, cubes, spheres, capsules,
have a standard size, they are either
1 by 1 by 1 or 1 by 2 by 1 Unity units.
As such we simply lift the player object up
by half a unit in the Y axis
and we know it is laying perfectly on top of plane.

![Place the player on the plane ]({{site.baseurl}}/images/posts/01/15-place-sphere-on-plane.gif)

If we look in the Game view we can that the
player game object is lit and it
casts a shadow on the plane.
All new Unity scenes come with the
default sky box and a directional light
to represent the sun, so we don't need to worry
about setting up any default lighting.
What could be improved however is the
white player sphere on the white background.

Let's add some colour to our background
so there is some contrast between the player and the play field.

To add colour or texture to a model
we need to use a material.
We won't go in to the details of materials now,
and we won't be using any textures.
We will simply use a standard material
to add colour to the objects in our scene.
First let's create a new folder in our
project to hold our materials.
We can do this by using the project's
Create menu and selecting Folder.
Rename this folder Material.

![Create a folder ]({{site.baseurl}}/images/posts/01/16-create-folder.gif)

With the Materials folder selected
use the project's Create menu again
and this time select Material.
Note how the material was created in the Materials folder.
This is because we had the folder selected
when we chose to create our new material.
Rename this material Background.

![Create a material]({{site.baseurl}}/images/posts/01/17-create-material.gif)

Select the material and under Main Maps
the first property is Albedo.
Click on the Albedo's colour field
to open a colour picker.
Change the colour to a nice dark shade of blue.
In our case I will use the RGB values of 0, 32, 64.
For a preview of the material make sure
that the preview window is open.

![Change albedo color to blue]({{site.baseurl}}/images/posts/01/18-change-albedo-to-blue.gif)

To apply the texture to the plane,
simply select the material in the project view
and drag it on to the plane in the scene view.
Now the player stands out on the dark blue background.

![Apply the material to the plane]({{site.baseurl}}/images/posts/01/19-apply-the-material.gif)

I want to make one additional change that
will help us later in this project.
I want to rotate the main directional light
so that we have better lighting on our player.

Select the directional light and in the transform component
change the Transform Rotation on the Y axis to 60.
This will give better shape to our player sphere.
Now we have a player game object and a background play field.

![Rotate the directional light]({{site.baseurl}}/images/posts/01/20-rotate-dir-light.gif)

You can watch all of the above steps in the following video tutorial:

<div align = "center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/W_fAidYRGzs" frameborder="0" allowfullscreen></iframe>
</div>

 In the [next tutorial]({{ site.baseurl }}{% post_url  2016-04-09-02-Moving the player %}) we will make the player move.
 

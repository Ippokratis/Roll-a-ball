---
layout: post
comments: false
title:  "08-Building the game"
date:   2016-04-09 01:40:56
tags: [unity3d]
excerpt_separator: <!--more-->
---
<iframe width="560" height="315" src="https://www.youtube.com/embed/hSg3e1M3hKY" frameborder="0" allowfullscreen></iframe>

Now that we've finished our game we need to
present it to our players.

One of the greatest things about Unity is that
once we have created our game we can deploy
it to many of the current platforms.
<!--more-->
For more detailed information on building and
build targets please see the lesson linked below.

Before we build our game we should
save our scene.

To build our game we must first open
the Build Settings window.

We can do this by selecting File - Build Settings
or by using the key combination of
shift plus command or control plus B.

This brings up the Build Settings window.

Our current build target is indicated by the Unity logo.

The blue highlight indicates our focus and
shows us on the right hand side the build
options for the currently selected platform.

We want to build a standalone application.

This is our current build target.

PC, Mac and Linux Standalone.

We do not need to change our build target.

If we did want to change our build target
we can select the desired platform from the list
and click the Switch Platforms button at the bottom of the window.

Let's now return our build target to the standalone player.

Once we have selected our new build target
we need to add the scenes we want to build
to the Build Settings window.

We can add the current scene by clicking the
Add Current button.

Or we can drag and drop any scene from our
project view in to the field at the top of
the Build Settings window.

It's worth noting that we don't need to
include every scene in our project.

We only need to include the scenes we
we want in our game.

It is also possible to perform a build
with no scenes in the build Settings window.

If we do this, Unity will simply build our game
using the current scene we have open for editing.

Now we are ready to build our game.

Let's return to the Build Settings window
and click the Build button.

This will bring up a dialogue box asking us
to choose a build location.

I like to associate my build location with
my project, so I will create a new folder
inside my project called Builds.

This folder must be placed only on the
root of our project alongside the
assets and library folders.

With the build folder selected let's name the build
and then click save.

Unity will now build the application
and save it to our Builds folder
When building for the Mac Unity builds a .
app bundle,
which contains all of the relevant data and files.

When building for Windows
Unity builds a .
exe file
and a data folder which contains all of the necessary resources.

To run the game, simply run the executable application.

And now we are running our game.

And, we win!
So in these assignments we have learned how to
create new game objects, how to position them in the scene,
add new components to them, write our own custom behaviours
for them using simple scripting.

We've seen how to use lights, cameras,
colliders, triggers, rigid bodies.

We can collect and count objects.

Though this is a very simple example,
it covers a large set of basic
subjects important to understanding how to use Unity.

For continued learning about Unity check the Learn site
for more lessons, assignments and projects.

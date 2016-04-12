---
layout: post
comments: false
title:  "02-Moving the player"
date:   2016-04-09 01:40:45
tags: [unity3d]
excerpt_separator: <!--more-->
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/7C7WWxUxPZE" frameborder="0" allowfullscreen></iframe>

Now we are going to move the player game object.

First let's think through how we want this player
game object to behave.
<!--more-->
We want to have the sphere roll around on the
game area, bump in to walls, stay on the ground
and not fly off in to space.

We want to be able to collide with our collectible
game objects and pick them up when we do.

This requires physics.

To use physics the game object needs
a rigidbody component attached.

To attach a new component we must first
select the game object we want to attach
the component to, in this case we will select
our player game object.

Then we can either choose the Component menu
and select Physics - Rigid Body
which would attach this component to the game object
we have selected.

Or use the Add Component button in the Inspector
choosing Physics - Rigid Body.

Either way this attached the rigidbody
component to the selected game object.

If we choose to we can rearrange the
order of the components on the game object
using the context sensitive gear menu
in the upper right of the component.

Doing this has no effect on the performance of our game.

However, having a consistent order to the components
on our game object may help us speed up our development
by keeping or maintaining an organised
project and hierarchy.

Don't forget, you can collapse or expand
the Component view by clicking on the component's title bar.

We should note that whenever we do this
this will also toggle the relevant
gizmos for that component in the Scene view.

Now we need to get the player object moving
under our control.

To do this we need to get input from our player
through the keyboard and we need to apply
that input to the player game object as forces
to move the sphere in the scene.

We will do this by using a script that
we attach to the player game object.

First let's create a folder in our project view
to hold our script assets.

In the Project view click on the Create menu
and choose Create Folder.

Rename this folder Scripts.

Next let's create a new C# script.

To create a new script we have some choices.

We can choose Assets - Create
to create our new C# script.

Or we can use the Create menu in the project view.

But what might be more efficient in this case
would be to select the player game object
and use the Add Component button in the Inspector.

The Add Component menu contains the selection
New Script.

This allows us to both create and attach
a script in one step.

First let's name this script PlayerController.

We can choose the language of the script, which will be C#,
and then click on Create and Add.

Or simply hit the return or enter key to
confirm our selection.

Unity will create, compile and attach this script
to our selected game object.

We should note, this way of creating a script
will create that script asset on the root
or top level of our Project view.

We will need to move the asset in to the Scripts directory
in order to maintain an organised Project view.

If we select the script in our Project view
we see a preview of the script asset in the Inspector,
but this text is not editable.

Let's open the script.

We can do this a number of ways.

When we are inspecting a game object using the script
we can use the context sensitive gear menu.

We can double click on the script asset in the Project view
or we can use the Open button in the Inspector
when we have the script selected in our Project view.

This will open our script in our preferred script editor.

First let's remove the sample code provided
in the base script.

Next let's think,
what do we want to do with this script?
We want to check every frame for player input
and then we want to apply that input to the
player game object every frame as movement.

Where will we check for and apply this input?
We have two choices.

Update and Fixed Update.

Update is called before rendering a frame
and this is where most of our game code will go.

Fixed Update on the other hand is called just
before performing any physics calculations
and this is where our physics code will go.

We will be moving our ball by applying forces
to the rigidbody, this is physics.

So we will put our code in Fixed Update.

What code to we need to write?
We know we need input,
but how do we find out more?
There is a shortcut in Monodevelop
that searches the Unity API.

On the mac it's command plus single quote,
and on the pc it's control plus single quote.

Select the item you want to research,
in our case input,
and hold down the command or control key and
type the single quote button.

This search brings up every reference
in our documentation related to input.

Select Input at the top,
interface in to the input system.

This brings up the page on Input.

This is the page on the input class.

We use this class to read the axis setup in the
input manager and to access multitouch
touch and accelerometer data
on mobile devices.

We read the text on the top of the page to
understand how to use the class.

In our case, to get input from the player
on all platforms, including mobile devices.

Under the description is a list of class
variables and class functions.

The class variables hold information
like the number of touches in touchCount
or a reference to the default gyroscope with gyro.

The class functions do something for us.

In our code we will be using Input.
GetAxis.

When we find the item we want we click on the link
to bring up a page on the function or the variable.

Let's look at Input.
GetAxis.

This page includes the signature of the function,
a description of the function
and code snippets showing how to use it
in Unity's Javascript and C#.

We will be using C#.

For more information on the input manager
and Input.
GetAxis see the lessons linked below.

We will be using Input.
GetAxis in a
very similar way to the code snippet.

Let's return to our script and write our code.

float moveHorizontal = Input.
GetAxis ("horizontal")
float moveVertical = Input.
GetAxis ("vertical")
This grabs the input from our player through the keyboard.

The float variables moveHorizontal and moveVertical
record the input from the horizontal
and vertical axis, which are controlled by the keys on a keyboard.

Our player game object uses a rigidbody
and interacts with a physics engine.

We will use this input to add forces to the rigidbody
and move the player game object in the scene.

To know more about how to apply forces to
the rigidbody let's check the documentation.

Type Rigidbody in to our script.

Now select rigidbody and hold down
the command key on the mac
or the control key on the pc
and type single quote.

Again, this brings a page with a search term "rigidbody".

We want to click on Rigidbody.

This brings up the rigidbody page.

If we want to apply force to our player game object
we need to do something.

So let's look at the functions available
to the rigidbody class.

We read the descriptions until we find
the one we want, in this case
let's choose AddForce.

This adds a force to the rigidbody
as a result the rigidbody will start moving.

Click the link and we go to the page on AddForce.

We can see the signature of the function
at the top of the page.

This signature tells us we need a vector3
and an optional ForceMode to add
force to our rigidbody.

What is a vector3?
For more detailed information on vector3
Please see the information linked below.

But in simple terms the vector3
holds 3 decimal values in one container.

This makes it easy for us to move around
and use values for things like a force in 3D space,
which requires a value for force on
each of the X, Y and Z axis.

Or to describe a rotation which would also require
a value for each of the X, Y and Z axis.

All of our documentation pages are linked together.

If we were to click on Vector3, we would be taken to the
documentation page for vector3.

The same is true for ForceMode, MonoBehaviour and RigidBody.

Below the description are snippets
that show us how this function could be used.

Note the second signature for AddForce below the first.

The descriptions are the same.

But in this case we can use AddForce with either a vector3
or 3 float values for X, Y and Z.

The next concept that we need to cover is
how to get a hold of, or how to reference
different components on our game object.

We are writing a script called PlayerController.

Which is attached as a script component
to our Player game object.

From this script we need to AddForce
using the rigidbody component.

We want to access that component from this script.

There are several ways that we can do this.

But in our case we will cover only one of the main ways
of accessing another component on the same game object.

We will create a variable to hold this reference in our script
and we will set this reference in the Start function.

We see this here in the code snippet.

public Rigidbody rb creates a public variable
with the type of rigidbody called rb
to hold the reference to the rigidbody we want to access.

In Start the reference is set by using the code
GetComponent
This will find and return a reference to the attached rigidbody,
if there is one.

All of the code in the start function is
called on the first frame that the script is active.

This is often the very first frame of the game.

Finally in FixedUpdate the attached rigidbody component
is accessed through the variable named rb
with rb.
AddForce.

So in our script we need to write
private Rigidbody rb to create the variable to hold the reference.

And in a new start function we need to write
rb=GetComponent
In FixedUpdate
let's use the simplest version of Rigidbody.
AddForce.

One that simply uses a vector3
and we will leave the ForceMode at default
by omitting it from our code.

So in our script we need to type
rb.
AddForce and then some vector3 value.

No how do we get our two float values
in to a vector3 value?
Let's create a new vector3 variable called Movement.

This will be equal to a new vector3
that is made up of an X, a Y and a Z.

The X, Y, Z values will determine the direction of the force
we will add to our ball.

What is our X value?
That would be moveHorizontal.

With this our left and right keys will add force
moving the ball to the left or right.

What is our Y? 0.

We don't want to move up at all.

What is our Z value? That would be moveVertical.

Now we use Movement, a vector3 value,
in rb.
AddForce
as rb.
AddForce(movement).

Let's save this script and return to Unity.

We check for errors in our footer or the console
and there are none.
 Good.

Let's test what we've written.

Hit Play, and by using the keys setup on the input manager
the ball moves in the scene.

But it's very slow.

This is too slow to be playable, but the basic concept
works 100%.

To stop testing leave play mode.

Let's return to our code and create a tool
that will give us control over the speed of the ball.

We need to multiply our movement by some value.

We could simply enter that value here on our script
but if we ever needed to make any tweaks or changes
we would have to return to our scripting editor
and change the value in the script and then recompile.

This takes time.

The solution is to create a public variable in our script.

Let's create a public float
called Speed.

By creating a public variable in our script
this variable will show up in the Inspector
as an editable property.

When we use a public variable we can make
all of our changes in the editor.

We then multiply Movement by Speed.

We now have control over our movement value
from inside the editor.

Let's save these changes and return to Unity.

When we return to the editor we can see our
PlayerController script now has a speed property.

Let's set this property to 1000.

Now enter play mode.

Whoa! Way too fast!
But changes are fast too.
Exit play mode and change the value to 500.

Hit Play.

That's a little better.

Congratulations, we can now move our character.

In the next assignment we'll talk about how to move the camera.

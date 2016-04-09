---
layout: post
comments: false
title:  "07-Displaying the score and the text"
date:   2016-04-09 01:40:55
tags: [unity3d]
excerpt_separator: <!--more-->
---
<a href="http://www.youtube.com/watch?feature=player_embedded&v=RFlh8pTf4DU
" target="_blank"><img src="http://img.youtube.com/vi/RFlh8pTf4DU/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="502" height="300" border="10" /></a>
Counting, displaying text and ending the game.

We need a tool to store the value
of our counted collectables.

And another tool to add to that value
as we collect and count them.

Let's add this tool to our PlayerController script.
<!--more-->
Select the Player game object and open the
PlayerController script for editing.

Let's add a private variable to hold our count.

This will be an int, as our count will be
a whole number, we won't be collecting partial objects,
and let's call it Count.

So in our game we will first start
with a count of 0.

Then we will need to increment our count value
by 1 when we pick up a new object.

First we need to set our count value to 0.

As this variable is private we don't have
any access to it in the Inspector.

This variable is only available for use within this script
and as such we will need to set it's starting value
here in the script.

There are several ways we can set the starting value
of Count, but in this assignment we will
do it in the Start function.

In Start set our Count to be equal to 0.

Next we need to add to Count when we pick up
our collectable game objects.

We will pick up our objects in OnTriggerEnter
if the Other game object has the tag Pickup.

So this is where we add our counting code.

After setting the other game objects
active state to False we add our new value of Count
is equal to our old value of Count plus 1.

There are other ways to add, count up or increment
the value when coding for Unity,
but this one is very easy to understand and
this is the one that we're going to use in this assignment.

Save this script and return to Unity.

Now we can store and increment our count
but we have no way of displaying it.

It would also be good to display a message
when the game is over.

To display text in this assignment we will
be using Unity's UI Toolset
to display our text and values.

First let's create a new UI text element
from the hierarchy's Create menu.

Let's look at what we've added to the hierarchy.

We seem to have gotten more than we bargained for.

We don't just have a UI text element,
but we've also created a parent
canvas element and an event systems game object.

These are all required by the UI toolset.

The single most important thing to know about
these additional items is that all UI elements must
be the child of a canvas to behave correctly.

For more information on the UI tools,
including the canvas and the events system
please see the information linked below.

Rename the text element CountText.

So let's customise this element a bit.

The default text is a bit dark.

Let's make the text colour white,
so it's easier to see.

The size and alignment are good.

And let's add some placeholder text
Count Text.

We want our text to display in the upper left
of the screen when the game is playing.

We can see that the UI text is currently
displaying in the centre of the screen in the game view.

This is because the text element is anchored
to the centre of it's parent,
which is, in this case, the canvas.

It is worth noting that the transform component on UI elements
is different from the other game objects in Unity.

For UI elements the standard transform has been replaced
with the rect transform,
which takes in to account many specialised features
necessary for a versatile UI system,
including anchoring and positioning.

For more information on the rect transform
please see the information linked below.

One of the easiest ways to move the
count text element in to the upper left
is to anchor it to the upper left corner of
the canvas, rather than to it's centre.

To do this open the Anchors and Presets menu
by clicking on the button displaying the current anchor preset.

When we re-anchor this text element
we also want to set the pivot
and the position based on the new anchor.

So we will hold down both the Shift and the Alt keys
and the select the upper left corner button.

That's done it, it's up in the corner.

But now it looks budged up against the
corner of the game view.

Let's give it some space between the text
and the edges of the screen.

As we are anchored to the upper left corner of the canvas
and we have set our pivot to the upper left corner as well
the easiest way to give the text a little breathing room
is to change the rect transform's
Pos X and Pos Y values.

10 and -10 seems about right,
with some room around it, yet it's still up and out of the way.

So let's wire up the UI text element
to display our count value.

Start by opening the PlayerController script for editing.

Before we can code anything related to any UI elements
we need to tell our script more about them.

The details about the UI toolset
are held in what's called a namespace.

We need to use this namespace
just as we are using UnityEngine and System.
Collections.

So to do this, at the top of our script write
using UnityEngine.
UI.

With this in place we can now write our code.

First create a new public text variable
called countText
to hold a reference to the UI text
component on our UI
text game object.

We need to set the starting value of the
UI text's Text property.

We can do this in Start as well.

Write countText.
Text = "Count: "
+ count.
ToString, and we need the parenthesis.

Now this line of code must be written
after the line setting our count value.

Count must have some value for us to set a text with.

Now we also need to update this text property
every time we pick up a new collectable
so in OnTriggerEnter after we increment our count
value let's write again
countText.
Text = 'Count: ' + count.
ToString();
Hmm, we've now written the same line of code
twice in the same script.

This is generally bad form.

One way to make this a little more elegant
is to create a function that does the work in one place
and we simply call this function every time we need it.

Let's create a new function with void SetCountText
and then an empty set of parenthesis and brackets.

Now let's move one instance of this line of code
in to the function by cutting and pasting it.

And in it's place let's put a line of code
simply calling the function.

Finally let's replace the other line with
the function call as well.

Excellent.
 Save and swap back to Unity.

Now we see our PlayerController script has
a new text property.

We can associate a reference to our Count text
simply by dragging and dropping the
CountText game object on to the slot.

Unity will find the text component
on the game object and correctly associate the reference.

Now let's save, enter play mode and test.

Ah-ha! Not only do we collect
these objects but we count them now.

Let's exit play mode.

We need to display a message when we have
collected all of the cubes.

To do this we will need another UI text object.

Again, using the hierarchy's Create menu
make a new UI text game object.

Rename it Win Text.

Note how the new UI text element
is automatically added to our canvas.

Again, as before, let's customise the values on the component.

Let's colour the text white so it is easier to see.

Let's make the text a little larger,
let's try about 24.

Lastly, let's adjust the alignment to centre and middle.

And again let's add placeholder text
Win Text.

We want this text to display in the centre of the game screen
but up a little so it doesn't cover the player game object.

To do this simply adjust the rect transform's
Pos Y value as by default this UI text element
is anchored to the centre of the canvas.

A value of about 75 feels good.

Save the scene and swap back to our scripting editor.

We need to add a reference for this UI text element.

Create a new public text variable
and call it winText.

Now let's set the starting value for the
UI text's text property.

This is set to an empty string or two
double quote marks with no content.

This text property will start empty.

Then in the SetCountText function let's write
if Count is greater than or equal to 12,
which is the total number of objects we have in the
game to collect, then our winText.
Text equals You Win.

Save this script and return to Unity.

Again on our player,
our PlayerController has a new UI text property.

We can associate the component
again by dragging the WinText game object in to the slot.

Save the scene and play.

So we're picking up our game objects,
we're counting our collectables,
and
we win!
And as we can see when we have collected 12 objects
we display the 'You Win' text.

In the next and last assignment of this series
we will build the game and deploy it using a standalone player.

.. _how-to-pick-frame:

How to define a good pick frame
===============================

When using Pickit :ref:`teach` the pick frame is the location where the Tool Center Point(TCP) of the robot will be guided to.
A good location of the pick frame will make programming the robot easier. 
So the focus of this article is on how to define a good pick frame for your application.

From the two examples below you'll see that it is important to define the pick frame according the gripper you are using for the application.

Orientation of the pick frame
-----------------------------

As a first example we want pick parts with a two-finger gripper. 
In the image below both gripper and part are shown. 
From this image it is clear that this would not be a good setup. 
The gripper would bump into the part.

.. image:: /assets/images/faq/pick-frame-two-finger-bad.png

The way the gripper approaches the part can be changed by changing the orientation of the pick frame in Pickit.
For the image below the orientation of the pick frame is changed for 90 degrees around the z-axis.
Like this the fingers of the gripper will go into the holes and it is sufficient to close the gripper to pick the part.

.. image:: /assets/images/faq/pick-frame-two-finger-good.png

Location of the pick frame
--------------------------

Next example is the same part but now we want to pick it with a vacuum gripper. 
If the pick frame of the previous example is used here, the vacuum gripper will be guided to the middle of the part.
But at this location there is no surface for the vacuum to attach itself. 

.. image:: /assets/images/faq/pick-frame-vacuum-bad.png

A better location for the vacuum gripper would be the surfaces at the side of the part.
For the image below the position of the pick frame is moved to this location. 
Also the orientation of the pick frame is changed so the gripper will approach perpendicular to the surface.

.. image:: /assets/images/faq/pick-frame-vacuum-good.png
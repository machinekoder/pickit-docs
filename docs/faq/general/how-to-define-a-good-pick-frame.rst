.. _how-to-pick-frame:

How to define a good pick frame
===============================

When using Pickit :ref:`teach`, the pick frame is the location where the Tool Center Point (TCP) of the robot will be guided to.
A well-specified pick frame makes programming the robot easier, as you don't need to specify part-specific offsets. 
This article focuses on how to define a good pick frame for your application.

A good pick frame is an application-level choice, as it not only depends on the part to pick, but also on the type of gripper that will be used.
The use cases below illustrate how the same part requires different pick frames when picked with different grippers.

Use case 1: picking a power socket with a two-finger gripper
------------------------------------------------------------

As a first example we want to pick parts with a two-finger gripper. 
In the image below both gripper and part are shown. 
From this image it is clear that this would not be a good setup. 
The gripper would bump into the part.

.. image:: /assets/images/faq/pick-frame-two-finger-bad.png

The way the gripper approaches the part can be changed by altering the orientation of the pick frame in Pickit.
In the image below, the pick frame is rotated by 90 degrees around the z-axis.
This way, the fingers of the gripper will go into the holes of the part, such that when the gripper closes, it will pick the part.

.. image:: /assets/images/faq/pick-frame-two-finger-good.png

Use case 2: picking a power socket with a vacuum gripper
--------------------------------------------------------

The next example shows the same part, but now we want to pick it with a vacuum gripper. 
If the pick frame of the previous example is used here, the vacuum gripper will be guided to the middle of the part.
But at this location there is no surface for the vacuum gripper to grasp. 

.. image:: /assets/images/faq/pick-frame-vacuum-bad.png

A better pick location for the vacuum gripper would be the surfaces at the side of the part.
In the image below the position of the pick frame is moved to this location. 
Also, the orientation of the pick frame is changed, such that the gripper will approach perpendicular to the surface.

.. image:: /assets/images/faq/pick-frame-vacuum-good.png
.. _example-case-washers:

Pickit example case: Picking of washers
=======================================

This article covers an extensive overview of an actual Pickit application, picking washers out of a bin.
Once picked the washers are dropped on top of each other, for this high accuracy is necessary.
In this article the basics as well as the robot program used in this application are covered.

Motivation
----------

For this application high accuracy is necessary to drop off the washers.
When picking them straight from the bin it is not always easy to have this high accuracy.
One of the reasons for this is that in a random bin all parts can be partially covered by each other.
Also specific for this application a magnetic gripper is used to pick the parts, and typically the parts tend to realign a bit when they are grasped.

To solve this a robot program with two steps is introduced.
In the first step the focus is to pick one part with the gripper from the bin.
Once the part is picked it is shown again to the Pickit camera to determine the exact position of the part in the gripper.
This information is then used to compensate while dropping the part.

See video below for the results of this approach.

Robot program
-------------

.. image:: /assets/images/examples/ur-program-in-hand-check.png

This example program can be downloaded 
`here <https://drive.google.com/uc?export=download&id=15nEGHvmjkcJnSTu-Xy0ca3SKgGPdM8cG>`__.
.. _example-case-washers:

Pickit example case: Picking of washers
=======================================

This article covers an extensive overview of an actual Pickit application, picking washers out of a bin.
Once picked the washers are dropped on top of each other, for this high accuracy is necessary.
In this article the basics as well as the robot program used in this application are covered.

Motivation
----------

For this application high accuracy is necessary to drop off the washers.
When picking them straight from the bin it is not always easy or even possible to have this high accuracy.
One of the reasons for this is that in a random bin all parts can be partially covered by each other.
Also, specific for this application a magnetic gripper is used to pick the parts.
When picking parts with a magnetic gripper they tend to realign a bit when they are grasped.

To solve this a robot program with two steps is introduced.
In the first step the focus is to pick one part from the bin.
Once the part is picked it is shown again to the Pickit camera to determine the exact position of the part.
This information is then used to compensate while dropping the part.

See video below for the results of this approach. 
Here you can clearly see that the robot compensates when dropping of the part so that all parts are all nicely stacked on top of each other.

.. raw:: html

  <div style="position: relative; padding-bottom: 5%; height: 0; overflow: hidden; max-width: 100%; height: auto;">
    <iframe src="https://drive.google.com/file/d/1uwuIwv8K6r884uZ1oQ9yn6nlXUCPYlxO/preview" width="640" height="480"></iframe>
  </div>

Robot program
-------------

To set up this application the in hand check template is being used.
The idea of this template is to first pick a part from the bin.
Then in a second step the part is presented again to the camera.
Now a second in hand detection is triggered to determine the exact position of the part in the gripper.
If this detection is succesful the part is dropped off neately on the stack.
If the detection is not succesful the part is dropped back in the bin.
For this application accuracy is important, so when we are not entirely sure of how the part is presented it is better to drop the parts back in the bin and try again with a different part.

Below the image all variables that needs to be filled in the template are explained.
This example program can be downloaded 
`here <https://drive.google.com/uc?export=download&id=1oXJ0EtJxgWAZcB56fw66XmzmfrEaoj0e>`__.

.. image:: /assets/images/examples/ur-program-in-hand-check.png

.. _drop-off-pose:

Drop_off_pose
~~~~~~~~~~~~~

The waypoint **drop_off_pose** is defined where the part needs to be dropped off.
In this template the robot will never move to this waypoint but it is used to calculate the waypoints **corr_drop** and **corr_pre_drop**.

For this application the **drop_off_pose** is defined by bringing the TCP of the robot just above the center of the stack.
This position will then be approached by the calculated pick frame of the in hand check.
This means if the calculated pick frame is in the center of the washer the washer will be dropped over the middle, shown in the top part of the image below.
If the calculated pick frame is somewhere at the sides of the washer the washer will be dropped with an offset, shown in the bottom part of the image below.

.. image:: /assets/images/examples/pick-frame-tcp-drop-off.png

.. note::
  It is important that the **drop_off_pose** waypoint is correctly defined.
  That is why a popup message is implemented in the template.

Fixed waypoints
~~~~~~~~~~~~~~~

**Home_pose** is the starting position of the robot program.
**Present_pose** is a waypoint where the part is presented for the in hand check.
**Detect_pose** is a waypoint where the robot does not block the field of view of the Pickit camera to look into the bin.
**Drop_off_bin** is a waypoint to drop back parts into the bin.

Bin picking setup/product file
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

For this application a simple :ref:`setup` file with a ROI box with similar dimensions as the actual bin is created.

In the product file the :ref:`teach` detection engine is used to find the washers.
Here half a model of the washers is taught and the pick frame is positioned at the sides.

These files need to be filled in twice in the robot program.
Once at the beginning and once after the second step, somewhere at the middle.

In hand check setup/product file
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This :ref:`setup` file containes a ROI box that isolates the washer in the hand of the robot.

The product file is again a :ref:`teach` detection.
But now a full model of the washer is taught and the pick frame is positioned in the center.

.. note::
  Here the position of the pick frame is important, as discussed in the section :ref:`drop-off-pose`.
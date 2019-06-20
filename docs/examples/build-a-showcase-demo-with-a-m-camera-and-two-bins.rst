Build a showcase demo with a M-camera and two bins
==================================================

This article will guide you in setting up a simple showcase demo with Pickit and a UR robot.
For this demo a Pickit M camera is used to detect bottles in a bin.
The parts are picked from the bin with a UR5 robot and a vacuum cup.
A video of the end result can be seen below.

.. raw:: html

  <iframe src="https://drive.google.com/file/d/1E4oO89VM-VIaAffyaiCnZt0mBtuPVEGJ/preview" frameborder="0" allowfullscreen width="640" height="480"> </iframe>
  <br>

.. contents::
    :backlinks: top
    :local:
    :depth: 1

Requirements
------------

The list below shows the different hardware that has been used to set up this demo.

-  Pickit system with M camera
-  Mounting plate to mount camera on to the robot
-  UR5e robot
-  Stand to mount the robot on
-  Schmalz Vacuum gripper ECBPi 12 24V-DC M12-8, 15 cm extended with vacuum cup SPB4f 40
-  Two bins with size 400 x 300 x 120 mm
-  Bottles of ø65 mm and length 200 mm

Mounting instructions
---------------------

-  The robot is mounted on the stand.
-  The camera is mounted on the robot flange of the robot with the help of a mounting plate.
-  The vacuum gripper is mounted on the robot flange beneath the camera. The distance between the end effector of the vacuum and the mounted camera should be bigger than the depth of the bin.
   In the example the bin is 120 mm deep and the distance between the end effector and camera is 150 mm.
-  Both bins are placed at a distance of 550 mm (center of robot base to center of bin) next to each other.

.. image:: /assets/images/examples/demo_2_bins_setup.png

Setting up the Pickit files
----------------------------

`Here <https://drive.google.com/uc?export=download&id=1B1BqZYRuM9Ny5DLZPQ5Lx3l6DZm7lrBs>`__ you can download a snapshot of the demo.
In the snapshot you can see that the bottles are detected by using the Teach detection engine with a single model.

Setup file
~~~~~~~~~~

For this demo two :ref:`setup` files are defined, one for each bin.
For both files the :ref:`region-of-interest` (ROI) has similar dimensions as the real bin.
The height is set to be higher than the real bin, so if the parts are stacked they can still be detected.
A separate :ref:`bin-box <bin-box>` height is defined to still be able to check for collisions.
Also a :ref:`empty ROI box <detecting-an-empty-roi>` value is defined, so we are able to determin if a bin is empty.
Last, the ROI boxes are attached to the Robot base frame. No other settings are used for this demo.

Need help with these settings? See the :ref:`setup` article for more information.

Product file
~~~~~~~~~~~~

For this demo one product file is defined with one model.
The model that is being used is the shape from the side.
The **pick frame** of this model is located in the center of the cylinder.
Here it is important that the X-axis of the pick frame is in the center and is pointing in the length direction of the bottle.
This allows for pick frame alignment (see further).
The **matching score** and **tolerance** is set to 80% and 2.4 mm.
No **fusion** or **downsampling** is applied and the **detection speed** is set to Normal.

.. image:: /assets/images/examples/demo_2_bins_pick_frame.png

Need help with these settings? See the :ref:`Teach` article for more information.

In the **Picking** page the :ref:`pick frames are enforced <enforce-alignment-of-pick-frame-orientation>` to Y ⊥ Z alignment.
This setting gives Pickit the freedom to rotate around the X-axis of the pick frame.
If a bottle is found in the middle of the bin the pick frame will point as much as possible upwards.
Since we are also using **box avoidance**, if a bottle is close to the side of the bin, the pick frame will not be pointing upwards but will be slightly tilted away from the side of the bin.

Also :ref:`check-collisions-with` is used. A simple cylinder shaped tool is used here.
Note that since the pick frame is in the center an pick offset in tool is used to compensate for this.

Need help with these settings? See the :ref:`Picking` article for more information.

Calibration
-----------

Next step is the robot-camera calibration. This process teaches Pickit
where the robot base is located w.r.t. to the camera. This information
is used to transform the object pick-frames into robot coordinates. A
detailed description in robot-camera calibration can be found in the article :ref:`robot-camera-calibration`. 

Setting up the robot program
----------------------------

`Here <https://drive.google.com/uc?export=download&id=1BT2TlxE-7Wqv8ZgmaNPdOIzdqtvJ5u6f>`__ you can download the UR robot program.
The idea of the program is to pick bottles from one bin and drop them in the other bin.
The robot will change bin if the bin is empty or if no valid objects are found for a few times in a row.

.. image:: /assets/images/examples/ur-2-bin-demo.png

The following still needs to be defined in this robot program:

-  Pickit **select** command, the correct setup and product file need to be filled in.
   First the setup file for the first bin is selected.
-  The **home_pose** is a start position of the robot.
-  For the picking sequence if an object in bin 1 is found following needs to be added. 
   A **grasping logic** to pick the part.
   **Detect_pose_1** is a waypoint 650 mm above bin 1.
   **Pre_drop_1** and **drop_1** are waypoints to drop off the parts in the other bin.
   A **release logic** to drop off the parts.
-  Similar settings need to be defined for the picking sequence if an object is found in bin 2.
-  In the Else clause for object found the **select** commands for Pickit need to be filled in correctly.
   If bin 1 is active the setup file is changed to bin 2 and vice versa.

In the robot program a script file function is defined and used. 
The idea here is to not rotate around the 6-th axis of the robot when picking objects.
This is done to make cable managment easier for the camera that is mounted on the head of the robot.

::

    def final_joint_correction():

    pickit_pre_joint = get_inverse_kin(pickit_pre_pose)
    actual_joint = get_actual_joint_positions()
    joint_cor = actual_joint[5] - pickit_pre_joint[5]
    pickit_pose = pose_trans(pickit_pose, p[0,0,0,0,0,joint_cor])
    pickit_pre_pose = pose_trans(pickit_pre_pose,p[0,0,0,0,0,joint_cor])

    end

To get rid of movement around the 6-th joint. 
The current joint position is compared with the calculated waypoints by Pickit.
Then the variable waypoints are altered to have the same joint position for the 6-th axis as the current one.
This function is executed before the program moves to these positions.

Interaction with the running demo
---------------------------------

This demo is robust and will keep on working continuously.
Interaction with the scene is possible.
Parts can be placed under angles, taken away and so on.

.. note::
   It is adviced to only alter the bin where the robot is not picking from.
Robot-camera calibration
========================

In this step we do a robot-camera calibration. In the previous chapter
we saw that the Pickit system is able to detect parts in its field of
view. Now Pickit needs to know where the robot is based so that it can
tell the robot where it needs to move to when an object is detected.
**If you skip this step, the robot will move to a wrong location.**

Follow the steps below to do a robot-camera calibration:

-  Mount the robot-to-camera calibration plate to the flange of the
   robot. Make sure it is well fixed.
-  Click on the :guilabel:`Calibration` button on top of the user interface. A popup
   showing the first step of the calibration process appears. Select a
   **stationary** camera mount and **Multi Poses Calibration**
   for the calibration method. For the robot type, select **6 D.O.F.** or **4 D.O.F.**
   depending on the number of degrees-of-freedom of your robot. If your robot has
   only 4 degrees-of-freedom, fill in the distance between calibration plate and
   robot flange in the field **Flange Z-axis**. Press :guilabel:`Start calibration process`.
-  On your robot open the example multi-poses calibration program supplied
   by Pickit. Edit the program, defining different waypoints such that the
   robot shows the calibration plate to the camera at different angles.

.. image:: /assets/images/First-steps/Robot-camera-calibration.jpg

-  Press :guilabel:`Next` in the Pickit user interface, going to the second step. Confirm
   that the plate is visible for the first waypoint, by looking at the 2D
   view in the calibration wizzard. Press :guilabel:`Next`.
-  Run the multi-poses calibration program on the robot. The calibration
   wizzard shows a progress bar, indicating the number of collected robot
   poses. Once all five poses are collected, press :guilabel:`Finish`.
-  Open the 3D view in the calibration wizzard, and check if the position and
   orientation of the robot model match the actual robot. If that is the case,
   press :guilabel:`Close popup`.
-  The robot-camera calibration process is finished and the calibration plate
   can be dismounted from the robot.

.. tip:: More details about robot-camera calibration can be found in
   the :ref:`robot-camera-calibration` article.

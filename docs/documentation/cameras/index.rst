.. _cameras:

Camera(s)
=========

In this article the different settings of the Camera(s) tab are discussed.

Camera configuration
--------------------

One Pickit processor can be connected to two different Pickit cameras at the same time. 
This can be two M-cameras, two L-cameras or a M and L-camera combined.

Here you select which camera to use in the setup file. Each setup file should have exactly one active camera.

Robot camera calibration
------------------------

Robot camera calibration is the process where the camera and the robot learn their relative position
with respect to each other. If done correctly, the camera can guide the robot to correct positions in
the physical environment. Calibration can be performed once the camera and robot have been mounted in
the work cell. This process only needs to be repeated if the camera is moved relative to the robot base,
or vice-versa.

Related articles:

.. toctree::
    :maxdepth: 1

    robot-camera-calibration
    multi-poses-calibration
    single-pose-calibration
    checking-robot-camera-calibration
    how-to-execute-robot-camera-calibration-with-an-abb-yumi-robot

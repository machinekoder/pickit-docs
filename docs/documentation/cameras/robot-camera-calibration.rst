.. _robot-camera-calibration:

Robot camera calibration
========================

After detecting objects, Pickit sends the pick frames to the robot. For the frames to make
sense, Pickit first needs to know the exact location of the robot base with respect to the
camera. This is achieved by **robot camera calibration**, making it a crucial step in any
picking application.

The basic procedure of robot camera calibration consists of having the robot showing the calibration
plate to Pickit and communicating its pose. This information is enough for Pickit to find out
where the robot base is relatively to the camera.

.. warning::
  Wrong or old calibration parameters can lead to unexpected motions. Safe motions of the robot
  must always be checked by the operator of the robot itself and can never be guaranteed by Pickit.

There are two possible ways to perform robot camera calibration: the multi poses and the single pose
method. Both options are briefly described below.

Multi poses calibration
~~~~~~~~~~~~~~~~~~~~~~~

The multi poses method consists of having the robot showing the calibration plate to Pickit five
times. This option is recommended, as it imposes no restrictions on the camera mount, or on how
the calibration plate is fixed to the robot flange.

.. note::
  Go to the :ref:`multi-poses-calibration` article for a step-by-step tutorial.

Single pose calibration
~~~~~~~~~~~~~~~~~~~~~~~

As the name suggests, the single pose method requires having the robot showing the plate to the
camera only once. However, this option can only be executed if the following restrictions are met:

#. The Pickit camera must be fixed at a stationary location, and cannot be mounted on the robot flange.
#. The robot must have a supported type of flange:
       - ISO 9409-1-50-4-M6 (50 mm width)
       - ISO 9409-1-31.5-4-M5 (31 mm width)
#. The calibration plate must be mounted on the robot flange exactly as described in
   :ref:`installing-calibration-plate`.

.. note::
  Go to the :ref:`single-pose-calibration` article for detailed instructions.

.. warning::
  If after calibration the Pickit camera has been relocated or rotated relatively to the robot base,
  a new robot camera calibration is required before picking, even if the motion was small.

.. important::
  After finishing robot camera calibration, don't forget to check the calibration result. Go to
  :ref:`checking-robot-camera-calibration` to know how.

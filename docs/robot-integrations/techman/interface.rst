.. _techman-interface:

The Pickit Omron TM interface
=============================

Pickit integrates seamlessly with **Omron’s TM** cobots by means of a set of **TM components**.
These components expose a set of Pickit specific command blocks that make the creation of vision-guided programs simple and easy.
This article documents the interface of the Pickit TM Components.
For installation instructions please refer to the Omron TM :ref:`techman-installation` article.

Components
----------

This section presents the available Pickit components.
It describes their usage and the meaning of the input parameters and output gateway states.

Some general considerations that apply to all components:

-  The complete component names are prepended by **perception_pickit_pickit_V01_**
-  The g_perception_pickit_user_msg global variable holds human-readable status updates from all commands.
   For instance, when a component exists with an error state, the value of this variable can be shown in a **Display** node to get an insight on the failure reason.
   Refer to the picking example article [TODO: Add link] for the recommended usage.

init
~~~~

Initializes the connection with a Pickit system and handles communications with it.
It should be the first Pickit component to appear in a robot program.

**Parameters**

**Pickit system IP address**, which can be modified by editing the **perception_pickit_pickit_V01_init1_pickit** device of the internal **send** node:

.. image:: /assets/images/robot-integrations/techman/tm-init-1.png
   :scale: 45 %

.. image:: /assets/images/robot-integrations/techman/tm-init-2.png
   :scale: 45 %

**Output**

Whether robot mode has been enabled.
Robot mode is enabled in the Pickit web interface, and is a requisite for performing picking operations, but not robot-camera calibration.

.. image:: /assets/images/robot-integrations/techman/tm-init-3.png
   :scale: 45 %

configure
~~~~~~~~~

Loads a specified setup and product configuration.
This specifies the behavior of Pickit detections, i.e. where and what to look for.

**Parameters**

**Setup and product ID**, valid values correspond to any of the configurations currently available in the connected Pickit system.
Available configurations are listed in the Pickit web interface.

By default, the IDs correspond to invalid values, so it is required to edit these parameters.

.. image:: /assets/images/robot-integrations/techman/tm-configure-1.png
   :scale: 45 %

**Output**

OK if the requested configuration was successfully loaded, FAIL otherwise.
The most typical failure reason is specifying non-existent IDs.

.. image:: /assets/images/robot-integrations/techman/tm-configure-2.png
   :scale: 45 %

findObjects
~~~~~~~~~~~

Trigger a Pickit object detection using the currently active setup and product configuration.

The next Pickit command after **findObjects** should always be **getResult**, which waits until a response for the detection request is ready.

.. tip:: It’s valid (and sometimes encouraged) to perform robot motions or other non Pickit actions between calls to **findObjects** and **getResult**.
  For instance refer to the :ref:`techman-pick-and-place-program` for such an application.

**Parameters**

This component has no input parameters.

**Output**

OK if the object detection was successfully triggered, FAIL otherwise.

.. image:: /assets/images/robot-integrations/techman/tm-findobjects-1.png
   :scale: 45 %

nextObject
~~~~~~~~~~

Request the next detected object.

A single call to **findObjects** might yield the detection of multiple objects.
**nextObject** allows to request the next available object, if any, without the need of triggering a new detection and the time overhead it entails.

The next Pickit command after **nextObject** should always be **getResult**, which waits until a response for the request is ready.

.. tip:: It’s recommended to use this command only when objects in the detection region have not moved (significantly) since calling **findObjects**.
  A good example of when to use **nextObject** is when a detection is unreachable by the robot.

**Parameters**

This component has no input parameters.

**Output**

OK if there is a next detected object, FAIL if the set of detected objects has been exhausted.

.. image:: /assets/images/robot-integrations/techman/tm-nextobject-1.png
   :scale: 45 %

getResult
~~~~~~~~~

Wait for Pickit reply with detection results.
**getResult** should always be the next Pickit command after a **findObjects** or **getNextObject** request.
It blocks the robot until a reply from Pickit is received.
When an object has been found, the following global variables are populated:

-  percepton_pickit_pose Object pick pose.
-  percepton_pickit_dim Object dimensions.
-  percepton_pickit_type Object type.
-  percepton_pickit_remaining_obj Number of remaining object detections from the last call to **findObjects**.
   After first calling **getResult**, this function returns the total number of object detections minus one.
   This value is also equal to the number of times **getNextObject** can be called.
   As such, the returned value decreases with each call to **getNextObject**.

**Parameters**

This component has no input parameters.

**Output**

-  Pickit can discriminate the following scenarios, for which the robot program can take action upon.
-  OBJECT_FOUND: A valid object has been found.
-  NO_OBJECT_FOUND: There are no pickable objects, yet the Region Of Interest (ROI) is not empty.
-  EMPTY_ROI: There are no pickable objects because the ROI is empty.
-  NO_IMAGE_CAPTURED: Image capture failed, most probably due to a disconnected camera.
-  FAIL: The call to **getResult** failed, for instance because it was called at the wrong place (not the next Pickit command after a **findObjects** or **getNextObject** request).

.. image:: /assets/images/robot-integrations/techman/tm-getresult-1.png

.. note:: There is currently no way to programmatically check if a pose is reachable by the robot before it gets executed.
  This means that program execution might stop if an unreachable object is detected by Pickit.

saveSnapshot
~~~~~~~~~~~~

Save a snapshot with the latest detection results.
The saved snapshot can then be loaded or downloaded by going to the :ref:`_Snapshots` page on the Pickit web interface and searching for a file whose name contains the capture timestamp.

**Parameters**

This component has no input parameters.

**Output**

OK if the snapshot was successfully saved, FAIL otherwise.

.. image:: /assets/images/robot-integrations/techman/tm-savesnapshot-1.png
   :scale: 45 %

findCalibrationPlate
~~~~~~~~~~~~~~~~~~~~

Trigger detection of the robot-camera calibration plate.
This command requires the Pickit web interface to be in the :ref:`robot-camera-calibration` page, hence robot mode should be disabled.
When Pickit is not in the :ref:`robot-camera-calibration` page, a pop-up is shown.

This component is meant to be used only in robot-camera calibration programs such as this example [TODO: Add link].
It is not meant to be used in picking programs.

**Parameters**

This component has no input parameters.

**Output**

OK if the calibration plate was found, FAIL otherwise.

.. image:: /assets/images/robot-integrations/techman/tm-findcalibrationplate-1.png
   :scale: 45 %
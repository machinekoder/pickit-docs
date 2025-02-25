.. _web-interface:

Web interface
=============

Interaction with Pickit is done through its web interface.
Its simple and intuitive user experience lets you configure the system and
monitor detections interactively.
This article presents an overview of the Pickit web interface.

.. _connecting-to-the-web-interface:

Connecting to the web interface
-------------------------------

Follow :ref:`these instructions <connect-computer>` on how to connect an
external computer to your Pickit system.
When successfully connected to the Pickit web interface, you should expect to
see something similar to the below image:

.. image:: /assets/images/Documentation/pickit-webinterface-21.png

If you cannot manage to successfully visualize the Pickit web interface, contact
us at `support@pickit3d.com <mailto:mailto:support@pickit3d.com>`__.


Components
----------

The interface consists of three main components:

.. contents::
    :backlinks: top
    :local:
    :depth: 1

.. _web-interface-top-bar:

Top bar
~~~~~~~

The top bar of the Pickit web interface contains relevant status information and
buttons that remain visible at all times.

The left part of the bar displays the following contents:

.. image:: /assets/images/Documentation/pickit-webinterface-top-bar-left.png
   :scale: 70%

- The Pickit logo.
- The Pickit version. By clicking on it, you can access the changelog of what's
  new in each Pickit release.
- The currently active **Setup** and **Product** files. By clicking on either
  file name, a separate window will pop up that allows you to change the active
  file or manage available files. See the :ref:`Configuration` article for more
  details.

The right part of the bar displays the following contents:

.. image:: /assets/images/Documentation/pickit-webinterface-top-bar-right.png
   :scale: 70%

- The status of the Pickit connection with the robot.
  An active robot communication is indicated by **✓**, otherwise **∅**.
- The :guilabel:`Settings` button, which opens a page with user :ref:`Settings`.
- The :guilabel:`Snapshots` button, which opens a page for
  :ref:`snapshot management <Snapshots>`.
- The :guilabel:`Calibration` button, which opens the page for performing
  :ref:`robot camera calibration <robot-camera-calibration>`.
- The :guilabel:`Enable Robot Mode` button. When enabled, Pickit starts
  listening for incoming robot commands and prevents the user from modifying
  the Pickit configuration.

Right panel
~~~~~~~~~~~

This part of the web interface is where you specify your object detection
configuration. There are different pages where you can define:

- :ref:`Setup: <setup>` Where to look for objects.
- :ref:`Detection: <detection>` What type of object to look for.
- :ref:`Picking: <Picking>` How to pick the detected objects.

.. image:: /assets/images/Documentation/pickit-webinterface-right-side.png

Left panel
~~~~~~~~~~

This part of the web interface displays the results of an object detection
run both graphically (:ref:`viewer <Viewer>`, top) and numerically
(:ref:`detection grid <detection-grid>`, bottom).
These allow you to have both qualitative and quantitative feedback on the
performance of object detection, and are powerful tools for inspecting and
optimizing your application.

.. image:: /assets/images/Documentation/pickit-webinterface-left-side.png

.. toctree::
    :maxdepth: 1
    :hidden:

    viewer
    detection-grid

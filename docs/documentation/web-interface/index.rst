.. _web-interface:

Web interface
=============

When a Pickit system is connected to an external computer and a
:ref:`supported web browser <supported-browsers>` is pointed to 
`http://192.168.66.1 <http://192.168.66.1/>`__, the web interface of
Pickit is shown. The web interface looks like the image below. In this
article a general overview of what you can see in this interface is
discussed. The interface is divided into 3 part: top bar, left side and right
side.

.. image:: /assets/images/Documentation/pickit-webinterface-21.png

.. contents::
    :backlinks: top
    :local:
    :depth: 1

.. _web-interface-top-bar:

Top bar
-------

Starting from left to right. First the logo of Pickit shown.
Next to the logo the current software version of your system is shown.

Next to the current software version the current **Setup** and **Product** file are shown.
More information on these can be found in
the :ref:`Configuration` article.

Next is the Pickit connection status with the robot.
An active robot communication is indicated by **✓**, otherwise **∅**.

Then the :guilabel:`Settings` button is shown. Here amongst other the Network and user settings
can be defined. More information about these settings can be found in
the article :ref:`Settings`.

Next the :guilabel:`Snapshots` button is shown. More information about this can be found in the :ref:`Snapshots` article.

Then the :guilabel:`Calibration` button is shown. More information about this can be found in the :ref:`robot-camera-calibration` article.

At last the :guilabel:`Robot` mode button is shown. Here you can change from
**Robot mode** to **Idle**. 

.. note:: Only when Pickit is in **Idle** mode parameters can be changed and
   saved.

Left side
---------

Here the Pickit viewer and detection grid
are shown. See the corresponding articles to have an in depth
explanation.

.. toctree::
    :maxdepth: 1

    viewer
    detection-grid

Right side
----------

Here the parameters of the Pickit system can be changed and saved. All
settings and parameters are divided over several tabs. See article of
each tab to have an extensive overview:

-  :ref:`setup`
-  :ref:`Teach`
-  :ref:`Flex`
-  :ref:`Pattern`
-  :ref:`Picking`

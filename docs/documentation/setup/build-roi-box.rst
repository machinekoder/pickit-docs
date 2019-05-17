.. _build-roi-box:

Build ROI box
-------------

There are three methods in Pickit for defining the ROI box:

.. contents::
    :backlinks: top
    :local:
    :depth: 1

When a ROI box is defined, it specifies the **Pickit reference frame**.
The axes of this frame are aligned with the box, and box bounds are
reported with respect to this frame, as mentioned in the :ref:`fine-tune-roi-box`. Furthermore, the
position of the detected objects displayed in the :ref:`detection-grid`
is with respect to the Pickit reference frame.

.. note:: The object positions are reported with respect to the Pickit
   reference frame in the web interface for convenience; but they are sent to the robot with respect to
   the robot base frame.

.. _Use-markers:

Around QR markers
~~~~~~~~~~~~~~~~~

This is the most common way of defining the ROI box. The ROI box is
defined based on three markers laid out in the field of view of the
camera. The Pickit text of all markers should be oriented in the same
direction and the arrows of the same color should be pointing to each other.
The markers are not interchangeable.

.. image:: /assets/images/Documentation/Roi-markers.jpg

#. Open the **2D** view in the Pickit viewer.
#. Place the three markers as shown in the image above in the field of
   view of the camera.
#. Press :guilabel:`Around QR markers` (this button is on clickable when all three markers
   are in the field of view of the camera).
#. If required, manually adjust the ROI box size as described in
   the :ref:`fine-tune-roi-box` section.

.. note:: When defining the ROI box, the **Pickit reference
   frame** is defined in the left bottom corner of the ROI box.

Automatically
~~~~~~~~~~~~~

With this strategy, the ROI box is located on top of the most dominant
plane in the field of view of the camera.

#. Press :guilabel:`Automatically`.
#. Input length and width of the desired ROI box.
#. If required, manually adjust the ROI box size as described in
   the :ref:`fine-tune-roi-box` section.

.. note:: When defining the ROI box, the **Pickit reference
   frame** is defined in the middle of the bottom of the ROI box.

From camera
~~~~~~~~~~~

In this way the ROI box is defined based of the camera frame.

#. Press :guilabel:`From camera`.
#. Input length and width of the desired ROI box.
#. If required, manually adjust the ROI box size as described in
   the :ref:`fine-tune-roi-box` section.

.. note:: This method simply defines the camera frame as the **Pickit
   reference frame**.
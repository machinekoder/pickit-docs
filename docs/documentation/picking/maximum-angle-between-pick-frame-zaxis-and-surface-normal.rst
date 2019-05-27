Maximum angle between pick frame Z-axis and surface normal
----------------------------------------------------------

This setting becomes visible whenever an alignment is enforced (see article :ref:`enforce-alignment-of-pick-frame-orientation`). With this setting, you can specify the maximum angular difference
between the Z axis of your adapted pick frame and the original pick
frame. As seen in the image below, if the new frame is tilted more than
the maximum specified angle, the object will be labeled as unpickable
and not sent to the robot. In the Pickit web interface, unpickable
objects are displayed orange in the :ref:`Objects view <objects-view>` and the :ref:`detection-grid`.

.. image:: /assets/images/Documentation/Max-angle-normal.png

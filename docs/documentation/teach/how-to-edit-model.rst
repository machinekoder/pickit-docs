How to edit an existing Pickit Teach model
------------------------------------------

After teaching a model, it is possible to change it, without the need to add
or delete models. This article explains how you can edit an existing model.

.. contents::
    :backlinks: top
    :local:
    :depth: 1

Defining the Pick frame
~~~~~~~~~~~~~~~~~~~~~~~

Each model has a Pick frame, which indicates where and with which orientation
the part will be picked by the robot. Upon teaching a model, the Pick frame is
automatically set to the centroid of the model point cloud. The user can change
the position and orientation of the Pick frame to the most suitable spot to pick.

**Left: Default Pick frame after teaching the model. Right: Custom Pick frame set by the user.**

.. image:: /assets/images/Documentation/Teach-model-pick-frame.png

Re-teaching the model cloud
~~~~~~~~~~~~~~~~~~~~~~~~~~~

If you wish to change the model cloud from scratch, you can re-teach it. Similarly as for the
:guilabel:`Add model` button, when you press :guilabel:`Re-teach`, the model cloud is replaced
by the content of your :ref:`region-of-interest`.

.. warning::
  When re-teaching a specific model, the point-cloud data from the previous model
  is overwritten. This action cannot be undone.

A common example is when you realize that the model cloud quality could be improved. For
instance, a model taught with the camera at a far distance might be missing important
details. In that case, you may want to :guilabel:`Re-teach` it from a closer distance.

**Left: model taught at a long distance to the camera. Right: model re-taught at a short distance to the camera.**

.. image:: /assets/images/Documentation/Teach-model-taught-far-close.png

Cropping and expanding a model cloud
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When clicking :guilabel:`Add a model` or :guilabel:`Re-teach`, the resulting model
corresponds to the content of the current :ref:`region-of-interest`. The
model point cloud can be cropped or expanded afterwards, using the arrows in the
**Model** view.

On the top left corner of the **Model** view, there is a **Auto-snap crop box**
checkbox. If this option is enabled, the green model box automatically adjusts to
the limits of the model points. This is useful for the user to check if the model
contains undesired points that are difficult to spot.

**If there are no undesired points in the model, the auto-snapped model box bounds the model points cleanly.**

.. image:: /assets/images/Documentation/Teach-model-autosnap-on-clean.png

**If the model contains undesired points that are difficult to see, the auto-snapped model box seems larger than the actual model.**

.. image:: /assets/images/Documentation/Teach-model-autosnap-on-ghostpoints.png

If the auto-snap option is disabled, the green model box is set to whatever the
user defines using the model arrows.

.. image:: /assets/images/Documentation/Teach-model-autosnap-off.png

.. note::
  Cropping and expanding operations do not replace the model with the content of the
  current region-of-interest. Instead, they work on the point cloud that was captured
  at the moment of teaching. When expanding the model box (making it larger), it is
  possible to include points that were initially outside the region-of-interest at
  the time of teaching.

Re-teaching the model cloud
~~~~~~~~~~~~~~~~~~~~~~~~~~~

If you wish to change the model cloud in a way that cropping or expanding it caanot help,
you can re-teach it. Similarly as for the :guilabel:`Add model` button, when you press
:guilabel:`Re-teach`, the model cloud is replaced by the content of your :ref:`region-of-interest`.

.. warning::
  When re-teaching a specific model, the point-cloud data from the previous model
  is overwritten. This action cannot be undone.

A common example is when you realize that the model cloud quality could be improved. For
instance, a model taught with the camera at a far distance might be missing important
details. In that case, you may want to :guilabel:`Re-teach` it from a closer distance.

**Left: model taught at a long distance to the camera. Right: model re-taught at a short distance to the camera.**

.. image:: /assets/images/Documentation/Teach-model-taught-far-close.png

How to use Pickit Teach
-----------------------

This article describes how to get started with the Pickit Teach engine.
Pickit Teach is a detection engine in Pickit which can search for
objects based on a previously shown example object. It is primarily used
to find irregularly shaped objects that don't fit in one of the basic
shape categories, like cylinders, spheres, squares, rectangles, circles,
and ellipses.

.. contents::
    :backlinks: top
    :local:
    :depth: 1

Teach a model based on your product
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Teaching a model of an object is the most important step when setting up
the Pickit Teach engine to detect your object. The model is the only
thing that is used by Pickit Teach to search for your objects in a
scene, so a better quality model results in better detections. A
high-quality model has the following characteristics:

#. It contains as many details of the object as possible,
#. It contains only points that
   belong to the object itself and
#. It exactly matches the side of the object
   that you want to detect.

Continue reading to learn how to build a high-quality model.

Placing the object under the camera
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Place your object under the camera and try to put it as close as
possible to the camera to capture the most details while making sure
that the object is lying fully in the field of view of the camera. It's
useful to keep the 2D view open so you see what the camera sees.

.. image:: /assets/images/Documentation/Teach-object-under-camera.png

Make sure that the object is inside the :ref:`region-of-interest`, and that
it is not occluded by other elements in the scene.

Adding a model
^^^^^^^^^^^^^^

In this step, the actual model will be taught and saved. Go to the
Detection tab and select the Pickit Teach engine. Open the ‘Define your
model(s)’ section. Here you will see a widget that allows adding models.

To add a new model, click the :guilabel:`Add a model`. Before clicking
this button, make sure that the previous steps are completed so that a correct side of the object is oriented to the
camera. When a new model is
successfully defined, the viewer will open the **Model
tab** automatically and a **Model row** will be added to the models'
widget.

The **Model tab** shows a 3D visual representation of your model, a green
model bounding box and the Pick frame. Note the
number in round brackets in the Model view tab name, this is the model
ID.

Previous steps can be repeated to Teach different models to Pickit Teach.
In one product file up to 8 different models can be taught.
This means that Pickit Teach is capable of looking for 8 different shapes in one detection.
See :ref:`Using-the-model-id-in-a-robot-program` on how you can use the model id in a robot program.

Editing a model
^^^^^^^^^^^^^^^

**Choosing the Pick frame**

Each model has a Pick frame, which indicates where and with which orientation
the part will be picked by the robot. Upon teaching a model, the Pick frame is
automatically set to the centroid of the model point cloud. The user can change
the position and orientation of the Pick frame to the most suitable spot to pick.

**Left: Default Pick frame after teaching the model. Right: Custom Pick frame set by the user.**
.. image:: /assets/images/Documentation/Teach-model-pick-frame.png

**Cropping and expanding the model**

When clicking :guilabel:`Add a model`, the resulting model corresponds to
the content of the current :ref:`region-of-interest`. However, the model
point cloud can be cropped or expanded afterwards, using the arrows in the
**Model** view.

On the top left corner of the **Model** view, there is a **Auto-snap crop box**
checkbox. If this option is enabled, the green model box automatically bounds
the model points. This is useful for the user to check if the model contains
undesired points that are difficult to spot.

**If there are no undesired points in the model, the auto-snapped model box bounds the model points cleanly.**
.. image:: /assets/images/Documentation/Teach-model-autosnap-on-ghostpoints.png

**If the model contains undesired points that are difficult to see, the auto-snapped model box seems larger than the actual model.**
.. image:: /assets/images/Documentation/Teach-model-autosnap-on-clean.png

If the auto-snap option is disabled, the green model box is whatever the user
defines using the model arrows.

.. image:: /assets/images/Documentation/Teach-model-autosnap-off.png

Notice that cropping or expanding the model does not replace the model with
the content of the region-of-interest, but only changes the point cloud that
was previously taught.

Detecting object(s)
~~~~~~~~~~~~~~~~~~~

Now that you've added your models, it's time to detect objects. 

Place your objects inside the region of interest box and press the
Detect button. On a successful detection, you will see in the 2D view
that a frame appears on the detected objects and yellow lines indicate
the bounding box. (For the yellow lines enable the "Show model box" in
the Viewer options.)

.. image:: /assets/images/Documentation/Teach-detecting-objects.png

In the Objects view, the point cloud models are visualized as a colored
cloud on top of the detected objects. When a detection failed because
for example a threshold parameter was exceeded, the model cloud will be
colored in red.

In the Objects table, you can see the detected object dimensions,
matching score and the Model ID that was found. Take a look at this
article to learn how to interpret the :ref:`detection-grid`.

.. image:: /assets/images/Documentation/Teach-detection-grid.png

If you want to optimize your detections, the article :ref:`Explaining-the-teach-detection-parameters`
goes more in depth on the different parameters of Pickit Teach. We
advice you to experiment with different settings and multiple objects in
different settings(tilted, on top of each other,..)

.. note:: There is a hard limit on the Teach matching time of 5 seconds.
   Before applying any optimization, this limit could be reached.
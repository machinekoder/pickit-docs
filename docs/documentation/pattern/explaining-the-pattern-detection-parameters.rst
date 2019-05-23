.. _Explaining-the-pattern-detection-parameters:

Explaining the Pattern detection parameters
-------------------------------------------

The process of detecting objects with the Pattern detection engine is all
about step-by-step testing and fine-tuning parameters until you get a
good result. The parameters for Pattern are split into six catagories.

.. contents::
    :backlinks: top
    :local:
    :depth: 1

M-HD preset (M-HD camera only)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The M-HD preset settings are explained in :ref:`M-HD-preset`.

Group points into clusters
~~~~~~~~~~~~~~~~~~~~~~~~~~

Go to :ref:`Group-points-into-clusters` to learn about clustering options.

Reject clusters
~~~~~~~~~~~~~~~

Cluster rejection is explained in :ref:`Reject-clusters`.

Fit objects to clusters
~~~~~~~~~~~~~~~~~~~~~~~

The parameters in the **Fit objects to clusters** section are similar as the ones for Pickit Flex. The main difference is that Pattern supports only flat shapes:

-  **Square** and **rectangle**: cardboard packaging, plastic bags,    industrial objects.
-  **Circle** and **ellipse**: industrial rings, pipe ends, top of soda
   cans.

Refer to :ref:`Fit-objects-to-clusters` for a detailed explanation on the remaining parameters in this section.

Define dimensions and orientation of objects
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

These parameters determine the dimensions and the orientation of
objects you want to find. 

The key difference between the Flex and Pattern detection engines lies in this section. While in Flex you specify a range of sizes (minimum and maximum length, width, diameter, etc.), in Pattern you specify a fixed size. Furthermore, you also specify the rough orientation of the parts, if they are aligned.

.. Note ::
  This additional piece of information (orientation and exact dimmensions) allows Pickit to detect objects even if different parts belong to the same cluster (for instance, aligned boxes touching each other). Flex, on the other hand, requires that different parts are grouped into separate clusters.

The effect of modifying the objects shape and orientation can be visualized in the **Objects** view. 

- For circles, you can define the diameter, for the other geometrical models you can define length and width.
- If the parts are aligned, the **expected orientation** indicates whether the long side of the objects (X-axis) is aligned with the reference (Region of Interest) X- or Y-axis. If the parts do not follow any particular alignment, choose an unknown orientation.
- With the **Remove contour points on ROI boundary** and the **Threshold**, you can remove contour points that are within the
threshold distance of the Region of Interest. 

Filter objects
~~~~~~~~~~~~~~

These parameters specify filters for rejecting detected
objects. Rejected objects are shown in the :ref:`detection-grid` as invalid.

Pattern objects can be rejected by setting minimum and maximum values for their **size in number of points**. Additionally,
objects can be rejected depending on the value of the :ref:`Contour-score` and :ref:`Surface-score`.

Optimize detections
~~~~~~~~~~~~~~~~~~~

Refer to :ref:`Optimize-detections` to learn how you can make detections faster.

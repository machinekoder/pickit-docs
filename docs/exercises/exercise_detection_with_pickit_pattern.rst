.. _exercise_detection_pattern:

Exercise detection with Pickit Pattern
=======================================

This exercise involves using the Pickit flex detection engine.
Different objects needs to be detected using fixed sized shapes.

+--------------+------------------+
| **Level**    | Basic            |
+--------------+------------------+
| **Duration** | < 15 min         |
+--------------+------------------+

.. image:: /assets/images/getting-started/detection-pattern.png

Requirements
------------

Before starting on this exercise we advise you to read the following articles:

-  :ref:`Region of Interest <region-of-interest>`
-  :ref:`Detection: Pickit Pattern <Pattern>`

Task
----

This exercise consist of three different parts. To get feedback on all
different parts of the exercise in total three different snapshots need
to be created.

-  Detect the cardboard boxes with dimensions 114 mm x 64 mm.
-  Detect the coils with outer diameter 55 mm.
-  Detect the coils with inner diameter 23 mm.

**Hint:** When using Pickit Pattern, it is important that the contours
of the clusters are well defined. This means that the clustering method,
contour method and downsampling influence the performance.

How to get started
------------------

Follow the next steps to complete the exercise.

#. Download the snapshot file
   `here <https://drive.google.com/uc?export=download&id=1In5l7xo8DNSEFPpwvqtQj7LtCUlUJw9p>`__
   to your computer.
#. Connect your computer to the Pickit :ref:`web-interface`.
#. In the user interface of Pickit, go to the :guilabel:`Snapshots` page. 
#. Press :guilabel:`Upload snapshot` and select the file.
#. The file can now be found under ``snapshots/uploads``.
#. Finish the exercise.
#. :ref:`Save a snapshot <Saving-a-snapshot>` with your current detection results.
#. Name your snapshot ``Solution_Pattern_boxes/coilsinner/coilsouter_1_CompanyName``.
#. :guilabel:`Download` the file from the ``snapshots`` folder.
#. Send your solution to support@pickit3d.com to receive feedback.

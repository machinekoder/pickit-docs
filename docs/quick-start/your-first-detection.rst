Your first detection
====================

Now that all connections are tested we can start our first detection.
For this we'll use a soda can. Note that this is the final step of this
quick start guide that can be completed without having a robot.
Follow the steps below to do your first detection with Pickit:

-  Make sure that the Pickit camera is mounted 700 mm above a flat work
   space. The work space is now seen in the 2D viewer on the Pickit
   user interface.
-  In the Pickit user interface press Disable Robot Mode.
-  Create a new setup: in the Setup tab, on top, click + New and name
   the new setup file 'Test\_Pickit'. Press Continue.
-  Place the three workspace markers, according the indicated arrows,
   inside the field of view of the camera.
-  Go to the Build ROI box section and press Around QR markers. This button
   is only enabled if all three region-of-interest amrkers are visible.
   Wait until the blue box is updated. 
-  In section Fine-tune ROI box, set Z min to 10 mm and Z max to 150 mm.
-  Press the Save button on top of the Setup tab.

.. image:: /assets/images/First-steps/Empty-roi.png

-  Create a new product: in the Product tab, on top, click + New and name
   the new product file 'Test\_Pickit'. Press continue. 
-  Make sure that Pickit Teach is selected.
-  Now place a soda can on its side in the middle of the marks.
-  Under section Define your models press Add a model. Now the model view is
   opened and a point cloud of the soda can is shown.
-  Press the Save button on top of the Detection tab.

.. image:: /assets/images/First-steps/Model-soda-can.png

-  Go back to the 2D view and press Detect, a Pick Frame (red-green-blue
   arrows) appears above the soda can.
-  Place the soda can somewhere else in between the markers and press
   Detect again.
-  Congratulations for your first detection!

.. image:: /assets/images/First-steps/First-detection.png

.. tip:: More information about the possibilities of the Pickit system can be
   found in the :ref:`region-of-interest` or the :ref:`teach` section.

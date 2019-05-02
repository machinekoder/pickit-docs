.. _bin-box:

Defining the Bin box 
---------------------

The Bin box specifies the box that is used to check for collisions with the bin, as described in :ref:`check-collisions-with`.

In most cases, the ideal ROI box is a good representation of the bin (:ref:`How-can-i-get-a-better-bin-picking-experience`). Therefore, by default Pickit uses the ROI box as Bin box. However, in some applications, it might be interesting to specify a Bin box different than the ROI box. For example, when the objects to pick are sticking out of the bin as shown below.


.. image:: /assets/images/Documentation/Bin-vs-Roi.png

To do so, go to `Define bin box` and select the Bin to be different than the ROI box. Then you can specify a different height for your bin. The Bin box will appear in Green in the 3D views next to the Blue ROI box.  

.. image:: /assets/images/Documentation/Bin-vs-Roi-view.png
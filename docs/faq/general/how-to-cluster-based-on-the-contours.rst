.. _how-to-cluster-contours:

How to cluster based on the contours
====================================

Contour clustering is an option mostly used when detecting 2D shapes with Pickit :ref:`Flex`. 
This option is used when the standard :ref:`Group-points-into-clusters` methods are not sufficient.
This additional clustering method is based on the contour points. 
In this article multiple examples are shown where this option is used.

Touching boxes
--------------

The first example is of 2 boxes that are touching in one corner. 
Because the surfaces of the boxes are on the same level, it is not possible to cluster the 2 boxes apart from each other.
In this case Pickit tries to fit one big rectangle on both rectangles at the same time. This leads to a strange and bad fit.

.. image:: /assets/images/faq/touching-rectangles-bad.png

Now if we look closely at the contour points of the cluster we can distinguish 7 convex angles and 2 concave angles.
If we are looking for a rectangular shape only convex angles make sense. 
So the concave angles in this case can be used to split up this cluster in 2 smaller clusters, this is done by cluster contours.
In the image below you can see that the contour points are now shown in 2 different colours. 
Now for every contour cluster a rectangle is calculated and good results are obtained.

.. image:: /assets/images/faq/touching-rectangles-good.png

Not perfectly aligned boxes
---------------------------

A similar example is when 2 boxes are aligned but not perfectly aligned, like in the image below.
Again the surfaces are on the same level, so they can't be clustered apart.
And also the result of fitting one rectangle on this cluster will not give a good result.

.. image:: /assets/images/faq/aligned-rectangles-bad.png

Also here there are 2 concave angles that can help us split up the contour points in 2 smaller clusters.
In the image below you can see that the contour points are now shown in 2 different colours. 
Now for every contour cluster a rectangle is calculated and good results are obtained.

.. image:: /assets/images/faq/aligned-rectangles-good.png


Touching circles
----------------

An other example is when 2 circular object are touching, shown in the image below.
Also here the surfaces are on the same level, so they can't be clustered apart.
Fitting one circle on the whole cluster doesn't make sense and leads to bad results.

.. image:: /assets/images/faq/circles-bad.png

If cluster contours is applied on this case, actually 4 smaller clusters are obtained. 
The contours of the 2 holes are clustered apart. 
And also the outer contours are clustered apart by using the concave angles present in this contour. 
In the image below 2 circles are calculated on the 2 outer contours. 
Note that similar results can be obtained by fitting circles on the holes.
In this case they are filtered out by using the filtering settings of Pickit Flex.

.. image:: /assets/images/faq/circles-good.png
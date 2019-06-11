.. _how-to-multiple-thread:

How to make a robot program with multiple threads
=================================================

When programming a robot with Pickit, a separate thread can be devoted to purely communicate with the Pickit system. 
The benefits for using a separate thread to communicate with the Pickit system are the following:

-  Robot program becomes cleaner, as all Pickit commands are in a separate thread
-  If the Pickit camera is mounted stationary more than one detection can be triggered while the robot is busy, for instance dropping off a part. 
   This saves cycle when Pickit needs more than one attempt to find a valid detection. 

In this article an example program with multiple threads is shown and elaborated. 
The example program is for Universal Robots, similar logic can be implemented for other robot brands.

Example program Universal Robots
--------------------------------

The logic behind this example program is similar as :ref:`universal-robots-urcap-example`. 
Pickit looks for a part, when a part is found the robot picks the part and while dropping off Pickit looks again for a new part.

In this robot program two threads are run simultaneously by the robot. 
One thread that controls all robot movements and the other thread controls all Pickit commands.
A variable **detecting** is introduced to synchronize both threads.

When the variable **detecting** is **True** the Pickit system is allowed to trigger detections. 
The robot is still allowed to perform actions, but it can't block the field of view of the camera.
After a part is detected successfully this variable is set to **False**. 
Now the robot is allowed to enter field of view of the camera and pick the part. 
After picking the part and the robot it outside the field of view again the value of **detecting** is set to **True**.

.. image:: /assets/images/faq/ur-multiple-thread.png

This example program can be downloaded 
`here <https://drive.google.com/uc?export=download&id=1nHyHMabCKk3wPl5eXQY4l1y9muLUUOQi>`__.



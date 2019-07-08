.. _how-to-in-hand-check:

How to make a robot program with in hand check
==============================================

When programming a robot with Pickit a second detection sometimes can be necessary to determine how the object is grasped by the robot.
This second, in  hand, detection will lead to a higher accuracy when dropping of the part.

The robot program will be divided into two parts.
In the first part Pickit will find a part in the bin and the robot will pick it.
Then in the second part the robot will present the part again to the Pickit camera and now the exact position of the part in the gripper will be determined.

The benefit of this approach is that the parts can be picked from the bin with an unknown offset.
This offset can be caused by different things:

-  When picking the part the gripper touch it and push it away.
-  When picking parts with a magnetic gripper the magnet tends to realign the parts.
-  When it is hard/impossible to determine the exact position of the part straight out of the bin.

In this article, an example program with in hand check is shown and elaborated. 
The example program is for Universal Robots, similar logic can be implemented for other robot brands.

Example program Universal Robots
--------------------------------
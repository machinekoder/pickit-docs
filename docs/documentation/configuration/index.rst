.. _Configuration:

Configuration
=============

The communication between a robot and the Pickit system is based on question and answer. 
The robot asks a question to the Pickit system and then the Pickit system answers this question.
The **setup** and **product** files are used to define the question that is asked to Pickit.

-  **Setup** file: defines where Pickit needs to look. It contains all the parameters set in the setup tab.
-  **Product** file: defines what Pickit needs to look for. It contains all the parameters set in the detection and picking tab.

The current loaded setup and product file are always shown in the top
bar as shown in the screenshot below.

.. image:: /assets/images/Documentation/active-files-21.png

Loading a setup or product file
-------------------------------

To load a new setup or product file press :guilabel:`Open`. A separate view will show all setup or product files on this system. 
From this list you can select the file that you want to open.

Setup and product files can also be loaded from within your robot
program using the correct Pickit command.

You can rename, download or delete a specific setup or product by pressing :guilabel:`Rename` 
:guilabel:`Download` or :guilabel:`Delete` once the setup or product files are
selected. Note that a setup or product file cannot be renamed or deleted while
being active.

.. image:: /assets/images/Documentation/product-files-window.png

.. warning::
  Deleted setup and product files cannot be recovered.

Creating a new setup or product file
------------------------------------

To create a new setup or product file, first press :guilabel:`New`, name the new file and press :guilabel:`Continue`. Pickit will make a new file with all settings set to the basic default settings.
After creation, the new setup or product file will automatically be
loaded.

.. image:: /assets/images/Documentation/create-new-product-file.png

Saving a setup or product file
------------------------------

Once settings are changed in Pickit they can be saved in the correct file. 
The :guilabel:`Save` button can be found at the top of the page. 

Pressing :guilabel:`Save` updates the active file with the new data. 
The :guilabel:`Save as` button saves the data to a new file. 
Pressing :guilabel:`Reset` restores the last saved settings.

.. image:: /assets/images/Documentation/save-saveas-reset.png

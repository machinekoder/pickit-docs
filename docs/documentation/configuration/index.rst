.. _Configuration:

Configuration
=============

The communication between a robot and the Pickit system is based on question and answer.
The robot asks a question to the Pickit system and then the Pickit system answers this question.
The **setup** and **product** files are used to define the question that is asked to Pickit.

-  **Setup** file: defines where Pickit needs to look. It contains all the parameters set in the **Setup** page.
-  **Product** file: defines what Pickit needs to look for. It contains all the parameters set in the **Detection** and **Picking** pages.

The current loaded setup and product file are always shown in the top
bar as shown in the screenshot below.

.. image:: /assets/images/Documentation/active-files-header.png

The name of the currently loaded setup file is also indicated on top of the **Setup** page, and the product file on top of the **Detection** and **Picking** pages.

.. image:: /assets/images/Documentation/active-file-name.png
   :scale: 70%

Loading a setup or product file
-------------------------------

To load a new configuration file press the :guilabel:`Open` button on top of the **Setup** page, to load a setup file, or on top of the **Detection** or **Picking** pages, to load a product file. You can also load a file by clicking on the file name at the top status bar instead. A separate view will show all setup or product files on this system.
From this list you can select the file that you want to open.

Setup and product files can also be loaded from within your robot
program using the correct Pickit command.

You can :guilabel:`Rename`, :guilabel:`Download` or :guilabel:`Delete` selected setup or product files. Active files cannot be renamed or deleted.

.. image:: /assets/images/Documentation/product-files-window.png

.. warning::
  Deleted setup and product files cannot be recovered.

Creating a new setup or product file
------------------------------------

To create a new setup or product file, first press :guilabel:`New`, name the file and press :guilabel:`Continue`. The new file will contain default settings.
After creation, the new file will automatically be loaded and set to active.

.. image:: /assets/images/Documentation/create-new-product-file.png
   :scale: 80%

Saving a setup or product file
------------------------------

Pressing :guilabel:`Save` updates the active file with the new data.
The :guilabel:`Save as` button saves the data to a file with a different name.
Pressing :guilabel:`Reset` restores the last saved settings, and all unsaved data is lost.

.. image:: /assets/images/Documentation/save-saveas-reset.png

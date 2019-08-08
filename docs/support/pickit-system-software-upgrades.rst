.. _Pickit-system-software-upgrade:

Pickit system software upgrades
================================

Upgrading the Pickit software can be done by the user, without Pickit
support engineers’ intervention. This feature is available starting from
software version 1.10. This guide will take you through the upgrade
procedure.

Overview
--------

.. warning:: We noticed that in some cases the web interface can show the error
   message **ERROR: Something went wrong during upgrading** although the upgrade
   process is still running fine. We are working hard on resolving this confusion.
   **DO NOT REBOOT THE PICKIT SYSTEM YOURSELF AND WAIT FOR IT TO REBOOT
   AUTOMATICALLY.** Once the Pickit system rebooted, the web interface will also
   automatically refresh and show the newest version. In the exceptional case that
   the Pickit system does not reboot itself within 15 minutes after starting the
   upgrade, please contact support@pickit3d.com if you can't confirm that the
   upgrade succeeded.

To upgrade your system follow these steps:

.. note:: User of version 2.1.2 or above should go in :ref:`upgrade-since-2-1-2`.

-  Press the **Settings** button in the top bar of Pickit's web
   interface.

   .. image:: /assets/images/Documentation/settings-button-21.png

-  Under the **Upgrade Pickit version** drawer in the **Network
   settings** section of the screen, you should see the following
   content depending on whether you're connected to the internet.

   -  If you are connected on the internet on the laptop/computer
      through which you are accessing the Pickit web interface), the
      content will look like the screenshot below. To upgrade your
      system, proceed with the steps
      described in :ref:`software-upgrade-with-internet`.

      .. image:: /assets/images/Documentation/Upgrade-pickit-version-internet.png

   -  If you don’t have internet on your computer, the settings will
      look like the screenshot below. To upgrade your system, follow the
      steps described in :ref:`software-upgrade-without-internet`.

      .. image:: /assets/images/Documentation/Upgrade-pickit-version-no-internet.png

.. note:: Before proceeding with the automatic upgrade, make sure your
   setup and product files are saved.

.. _software-upgrade-with-internet:

Software upgrade with internet connection
-----------------------------------------

If you are connected to the internet, you can just press the **Download
and Install Upgrades** button and the rest will be automatically taken
care of. When the upgrading is in progress you should see the following:

.. image:: /assets/images/Documentation/pickit-upgrading.png

.. _software-upgrade-without-internet:

Software upgrade without internet connection
--------------------------------------------

If the PC through which you access the Pickit web interface does not
have access to the internet, you should download the upgrade file from
the link shown on one of the previous screenshots above. 

After you download the file, you can use a USB flash drive to transfer
it on the computer on which the Pickit web interface is open, and under
the same section for version upgrades, press the **Upload and Install
Upgrades** to upload it and proceed with the same procedure as described
above.

.. _upgrade-since-2-1-2:

Upgrade Pickit since 2.1.2
--------------------------

Since this version, we disabled the direct upgrade.

- Download the latest version of Pickit here_.
- Press the **Settings** button in the top bar of Pickit's web interface.

     .. image:: /assets/images/Documentation/settings-button-21.png

- Under the **Upgrade Pickit version** drawer in the **Network
  settings** section of the screen, you should see the following
  content :

    .. image:: /assets/images/Documentation/upgrade_pickit_2.1.2.png

- Press the **Upload and Install Upgrades** to upload and select the downloaded
  file.

- When the upgrading is in progress you should see the following:

   .. image:: /assets/images/Documentation/pickit-upgrading.png

.. _here: https://client.pickit3d.com/upgrade/v2/

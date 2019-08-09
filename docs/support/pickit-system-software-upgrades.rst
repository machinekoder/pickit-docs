.. _Pickit-system-software-upgrade:

Pickit system software upgrades
================================

Upgrading the Pickit software can be done by the user, without Pickit
support engineers’ intervention. This feature is available starting from
software version 1.10. This guide will take you through the upgrade
procedure.

Overview
--------

To upgrade your system follow these steps:

.. note:: Before proceeding with the upgrade, make sure your
   setup and product files are saved.

- Download the latest version of Pickit here_.
- Press the **Settings** button in the top bar of Pickit's web interface.

     .. image:: /assets/images/Documentation/settings-button-21.png

- Under the **Upgrade Pickit version** drawer in the **Network
  settings** section of the screen, check the case **I prefer downloading and
  uploading the new version myself** if any and then press the **Upload and
  Install Upgrades** button to upload and select the downloaded
  file.

- When the upgrading is in progress you should see the following:

   .. image:: /assets/images/Documentation/pickit-upgrading.png

.. _here: https://client.pickit3d.com/upgrade/v2/

.. warning:: We noticed that in some cases the web interface can show the error
   message **ERROR: Something went wrong during upgrading** although the upgrade
   process is still running fine. We are working hard on resolving this confusion.
   **DO NOT REBOOT THE PICKIT SYSTEM YOURSELF AND WAIT FOR IT TO REBOOT
   AUTOMATICALLY.** Once the Pickit system rebooted, the web interface will also
   automatically refresh and show the newest version. In the exceptional case that
   the Pickit system does not reboot itself within 15 minutes after starting the
   upgrade, please contact support@pickit3d.com if you can't confirm that the
   upgrade succeeded.

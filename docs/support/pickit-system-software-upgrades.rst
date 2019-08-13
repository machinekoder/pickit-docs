.. _Pickit-system-software-upgrade:

Pickit system software upgrades
================================

Upgrading the Pickit software can be done by the user, without Pickit
support engineers’ intervention. This guide will take you through the upgrade
procedure.

Overview
--------

To upgrade your system follow these steps:

- Before proceeding with the upgrade, make sure your setup and product files are saved.

- Download the latest version of Pickit here_.
- Press the **Settings** button in the top bar of Pickit's web interface.

     .. image:: /assets/images/Documentation/settings-button-21.png

- Under the **Upgrade Pickit version** drawer in the **Network settings** section of the screen,
  press the **Upload and
  Install Upgrades** button to upload and select the downloaded
  file.

  .. note:: **For version < 2.1.2** :

    You first need to check the case **I prefer downloading and
    uploading the new version myself** before pressing the **Upload and
    Install Upgrades** button to upload and select the downloaded
    file.

- When the upgrade is in progress you should see the following:

   .. image:: /assets/images/Documentation/pickit-upgrading.png

.. _here: https://client.pickit3d.com/upgrade/v2/

.. warning:: Note that for Pickit versions < 2.1.2, the web interface can show
  the error message **ERROR: Something went wrong during upgrading** although the
  upgrade process is still running fine.

  If you see this message, **DO NOT REBOOT THE PICKIT SYSTEM YOURSELF AND WAIT
  FOR IT TO REBOOT AUTOMATICALLY**. Once the Pickit system rebooted, the web
  interface will also automatically refresh and show the newest version.

  In the exceptional case that the Pickit system does not reboot itself within
  15 minutes after starting the upgrade, please contact support@pickit3d.com

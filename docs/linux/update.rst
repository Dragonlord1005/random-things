=============
Update Linux
=============
This is how to setup ubuntu to update automatically

.. code-block:: sh
   :caption: This is manually update just in case

    apt update && apt upgrade -y

This will update your system.

The next step is enabling automatic updates, you will need sudo permissions to do this.

.. code-block:: sh

    sudo apt install unattended-upgrades
    sudo dpkg-reconfigure --priority=low unattended-upgrades

This will allow your system to automattically update your system
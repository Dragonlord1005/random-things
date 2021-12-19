====
SSH
====

This is about how to setup ssh on linux and windows


----------------------------------------------------------------
Setup
----------------------------------------------------------------
.. code-block:: sh
    :caption: This will be run on the linux server
    
        mkdir ~/.ssh && chmod 700 ~/.ssh

This will do the stuff for the setup

.. code-block:: bash
    :caption: this is run on windows

        ssh-keygen -b 8192

This will generate a key, it can take a minute so don't worry

You don't really need a pashprase so just press enter

.. code-block:: bash
    :caption: this is run on windows only

        scp $env:USERPROFILE/.ssh/id_rsa.pub username@ip:~/.ssh/authorized_keys

After you run this it will ask for your password and your done!


----------------------------------------------------------------
Lockdown
----------------------------------------------------------------
This is going to lock it down pretty much, making it hard to hack

.. code-block:: sh
    
    sudo nano /etc/ssh/sshd_config
    Change the port to something different like 777 for example
    Change permit root login to no
    turn password authentication to no

Exit nano then run this

.. code-block:: sh

    sudo systemctl restart sshd

DO NOT LOGOUT YET

You could have messed something up, so open a new terminal window and login to ssh normally but add -p whatever you set the port too, if it works your all good!


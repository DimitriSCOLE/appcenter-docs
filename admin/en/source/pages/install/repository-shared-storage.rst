.. Copyright 2017 FUJITSU LIMITED

.. _repository-shared-storage:

UForge Repository on Shared Storage
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When using shared storage NFS is used to share the information between the various UForge nodes.  To setup the NAS or SAN for the UForge Repository you must create two shared directories, one for the operating system data and the other for all the user data (``My Software`` and images generated).

To setup the shared storage:

	1. Log in to the machine where the NFS server is running

	2. Create the operating system directory, for example: /volume1/DISTROS

		The following NFS options are required::

			*(rw,async,no_wdelay,no_root_squash,insecure_locks,anonuid=0,anongid=0)

	3. Create the user data directory, for example: /volume1/USER_DATA

		The following NFS options are required::

			*(rw,async,no_wdelay,no_root_squash,insecure_locks,anonuid=0,anongid=0)

	4. Check the mount points: 

		.. code-block:: shell

			mount 192.20.777.205:/volume1/USER_DATA/ /mnt 
			su - tomcat 
			cd /mnt

	5. Execute the command:

		.. code-block:: shell

			touch test 

	6. If it returns:

		.. code-block:: text

			touch: cannot touch `test': Permission denied 

	Then execute the following commands (as ``root``) 

		.. code-block:: shell

			cd /mnt 
			chown -R tomcat:tomcat . 

	7. Confirm you can create a file on /mnt as user ``tomcat``. Then perform the following:

		.. code-block:: shell

			cd ~ 
			umount /mnt 




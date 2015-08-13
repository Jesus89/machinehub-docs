============
Installation
============

System dependencies
===================

`Install FreeCAD <http://www.freecadweb.org/wiki/index.php?title=Install_on_Unix>`_.
------------------------------------------------------------------------------------



.. code-block:: bash

	# Install FreeCAD
	sudo add-apt-repository ppa:freecad-maintainers/freecad-stable
	sudo apt-get update
	sudo apt-get upgrade
	sudo apt-get install freecad freecad-doc

`Install Docker <https://docs.docker.com/installation/ubuntulinux/>`_.
----------------------------------------------------------------------

.. code-block:: bash

	# Install Docker
	sudo apt-get install wget
	wget -qO- https://get.docker.com/ | sh


`Create a Docker group <https://docs.docker.com/installation/ubuntulinux/#create-a-docker-group>`_.
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. warning::

	Warning: The docker group is equivalent to the root user.

.. code-block:: bash

	# Create a Docker group
	sudo usermod -aG docker YOUR_USER_NAME


Python requirements
-------------------

.. code-block:: bash

	cd machinehub
	sudo -H pip install -r requirements.txt


Execute machinehub
==================

Build the machinehub docker image to use as base to the machine images.

.. code-block:: bash

	cd machinehub/machinehub/docker/
	docker build -t machinehub .

Launch the webapp.

.. code-block:: bash

	cd machinehub
	python launcher.py

Configure machinehub
====================

If you want to change the address or the admin info, edit `~/.machinehub/machinehub.conf` yo chage the address, port, or the admin info.

.. code-block:: text

	[server]
	host: 127.0.0.1
	port: 5000
	[users]
	admin: admin #user: password

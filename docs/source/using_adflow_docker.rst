Using ADflow Docker
===================

For installing docker for ADflow, please visit: https://mdolab-mach-aero.readthedocs-hosted.com/en/latest/installInstructions/dockerInstructions.html

Initialize a container
----------------------
Navigate to the directory containing the case you would like to run and initialize the Docker image you downloaded into a container, running interactively:

.. code-block:: bash

   docker run -it --name <NAME> --mount "type=bind,src=<HOST_DIR>,target=<MOUNT_DIR>" <IMAGE> /bin/bash

Replace ``<NAME>`` with the name you would like to give the container, set ``<HOST_DIR>`` to the absolute path to your case directory (call it ``<name>``), and set ``<MOUNT_DIR>`` to ``/home/mdolabuser/mount/``. Then provide the image tag as ``<IMAGE>``, matching the one downloaded previously: ``mdolab/public:<TAG>``.

Download helper scripts
-----------------------
Download the ``dockerUsageExample`` folder from the UniFoil GitHub repository into your ``<name>`` directory using this link: https://github.com/rohitroxkp7/UniFoil/tree/main/dockerUsageExample. This folder contains:

- ``run_adflow.py``
- ``aero_run.py``
- ``wing_vol.cgns``

Run the case
------------
From your host machine, start the container and run the helper script.

.. code-block:: bash

   sudo docker start adock

Add your user to the docker group (one time) so you can run Docker without sudo, then log out and back in. If that does not work, then restart the computer post command execution:

.. code-block:: bash

   sudo usermod -aG docker $USER

Now run the case from the host in the ``dockerUsage`` folder:

.. code-block:: bash

   cd <name>/dockerUsage
   python run_adflow.py --start

Useful options:

- ``--np 16`` to control MPI processes
- ``--container <NAME>`` if your container name is not ``adock``
- ``--script aero_run.py`` to select a different script
- ``--workdir /home/mdolabuser/mount`` if you changed the mount path

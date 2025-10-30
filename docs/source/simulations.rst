Simulations
============

.. autosummary::
   :toctree: generated

UniFoil used ADFlow and the MACH-Aero library to simulate the data.
In the event that the data provided in our lab is insufficent for your needs, we have also included scripts to help generate more samples.
You can customise the generation arguments to gather simulations with specific properties.
It is important to note that ADFlow and its dependances are optimized for CPU work and not GPUs.
It is recommended to use a high power CPU Cluster if available to speed up processing.


.. note::
   This docuentation only covers the basic usage of ADFlow for airfoil simulations. Please visit the 'ADFlow GitHub <https://github.com/mdolab/adflow>' or the 'ADFlow Documentation <https://mdolab-adflow.readthedocs-hosted.com/en/latest/> for usage.'

Building MACH-Aero
----------------
MACH-Aero is the library utilized to generate airfoil simulations.
In order to get started in using this library, visit the 'MACH-Aero GitHub Repo <https://github.com/mdolab/MACH-Aero>', or the 'MACH-Aero Documentation <https://mdolab-mach-aero.readthedocs-hosted.com/en/latest/>' and follow the installation instructions.

As a general requirement, using MACH-Aero and ADFlow is only officially supported on Ubuntu LTS 20.04 or 22.04, however testing shows that it is funcional in the most recent Ubuntu LTS 24.04.
Those familiar with Docker and containerization can use the official 'Docker Image <https://hub.docker.com/r/mdolab/public/tags>'.

Grid Generation
---------------
The first part of simulating airfoils through ADFlow is generating the airfoil grid.
Our grids were generated from a series of coefficents to allow for easier encoding of geometry data.
Each airfoil type has a different quantity of coefficents.

PLACEHOLDER!

+-----------------+----------------------+
| Airfoil Class   | Geometry Coefficents |
+=================+======================+
| NLF             | 16                   |
+-----------------+----------------------+
| FT              | 14                   |
+-----------------+----------------------+

Mesh Generation
---------------
After generating the airfoil grid, the points must be converted into a Volume .CGNS.
This file is what is fed into ADFlow to run the simulation.

Geometry
========

To begin using UniFoil, import the package:

.. code-block:: python

   import unifoil

The **Geometry** section provides commands to generate airfoil geometries and extract coordinate data from the UniFoil dataset.  
Follow the commands below in order.

.. code-block:: python

   # Generate Fully Turbulent (FT) airfoil geometries
   unifoil.gen_ft()

.. code-block:: python

   # Generate Natural Laminar Flow (NLF) airfoil geometries
   unifoil.gen_nlf()

.. code-block:: python

   # Initialize the data extraction interface
   from unifoil.extract_data import ExtractData
   ed = ExtractData()

.. code-block:: python

   # Extract airfoil coordinates from the turbulent dataset
   x, y = ed.extract_airfoil_coords(airfoil_number=3, source="turb", plot_flag=True)

.. code-block:: python

   # Extract airfoil coordinates from the transitional-laminar dataset
   x, y = ed.extract_airfoil_coords(airfoil_number=3, source="translam", plot_flag=True)

Geometry
========

The **Geometry** module of UniFoil provides tools to generate and access airfoil geometries from the curated UniFoil dataset.  
This includes creating both *Fully Turbulent (FT)* and *Natural Laminar Flow (NLF)* geometry libraries, as well as extracting airfoil coordinates from different datasets.

The following sequence demonstrates the typical workflow for geometry generation and extraction.

.. code-block:: python

   import unifoil

   # Step 1: Generate Fully Turbulent airfoils
   unifoil.gen_ft()

   # Step 2: Generate Natural Laminar Flow airfoils
   unifoil.gen_nlf()

   # Step 3: Initialize the data extraction interface
   from unifoil.extract_data import ExtractData
   ed = ExtractData()

   # Step 4: Extract airfoil coordinates from the turbulent dataset
   x, y = ed.extract_airfoil_coords(airfoil_number=3, source="turb", plot_flag=True)

   # Step 5: Extract airfoil coordinates from the transitional-laminar dataset
   x, y = ed.extract_airfoil_coords(airfoil_number=3, source="translam", plot_flag=True)


Functions and Classes
---------------------

.. autosummary::
   :toctree: generated


.. py:function:: unifoil.gen_ft()

   Generates and stores the **Fully Turbulent (FT)** airfoil geometries in the local UniFoil directory.  
   These geometries are used in simulations assuming fully turbulent flow.

   :return: None
   :rtype: NoneType

   **Example:**

   .. code-block:: python

      import unifoil
      unifoil.gen_ft()


.. py:function:: unifoil.gen_nlf()

   Generates and stores the **Natural Laminar Flow (NLF)** airfoil geometries in the local UniFoil directory.  
   These geometries are used for cases involving laminar–turbulent transition.

   :return: None
   :rtype: NoneType

   **Example:**

   .. code-block:: python

      import unifoil
      unifoil.gen_nlf()


.. py:class:: unifoil.extract_data.ExtractData()

   Initializes the **ExtractData** interface, providing methods to read, process, and visualize airfoil data from the UniFoil dataset.

   **Example:**

   .. code-block:: python

      from unifoil.extract_data import ExtractData
      ed = ExtractData()


.. py:method:: ExtractData.extract_airfoil_coords(airfoil_number, source="turb", plot_flag=False)

   Extracts the surface coordinates *(x, y)* of a specific airfoil from the selected dataset.

   :param airfoil_number: The ID number of the airfoil to extract.
   :type airfoil_number: int
   :param source: The dataset source, e.g., ``"turb"`` or ``"translam"``.
   :type source: str, optional
   :param plot_flag: If ``True``, plots the extracted airfoil geometry.
   :type plot_flag: bool, optional
   :return: Tuple of arrays ``(x, y)`` representing the airfoil coordinates.
   :rtype: tuple of np.ndarray

   **Examples:**

   - Extract from the **turbulent dataset**:

     .. code-block:: python

        x, y = ed.extract_airfoil_coords(airfoil_number=3, source="turb", plot_flag=True)

   - Extract from the **transitional-laminar dataset**:

     .. code-block:: python

        x, y = ed.extract_airfoil_coords(airfoil_number=3, source="translam", plot_flag=True)

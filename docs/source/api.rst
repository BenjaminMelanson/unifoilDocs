API
===

Welcome to the **UniFoil API Documentation**!  
Below is a list of the core functions and classes needed to utilize the UniFoil dataset and geometry generation tools.

Geometry
--------

.. autosummary::
   :toctree: generated

.. py:function:: unifoil.gen_ft()

   Generates and saves the **Fully Turbulent (FT)** airfoil geometries.  
   These geometries are used to initialize simulations that assume fully turbulent flow conditions.

   :return: None
   :rtype: NoneType

   **Example:**

   .. code-block:: python

      import unifoil
      unifoil.gen_ft()

.. py:function:: unifoil.gen_nlf()

   Generates and saves the **Natural Laminar Flow (NLF)** airfoil geometries.  
   These geometries are used to initialize simulations with laminar-turbulent transition regions.

   :return: None
   :rtype: NoneType

   **Example:**

   .. code-block:: python

      import unifoil
      unifoil.gen_nlf()


Data Extraction
---------------

.. autosummary::
   :toctree: generated

.. py:class:: unifoil.extract_data.ExtractData()

   Provides methods for reading and extracting airfoil coordinate data and other simulation results from the UniFoil dataset.

   **Example:**

   .. code-block:: python

      from unifoil.extract_data import ExtractData
      ed = ExtractData()

.. py:method:: ExtractData.extract_airfoil_coords(airfoil_number, source="turb", plot_flag=False)

   Extracts the airfoil surface coordinates *(x, y)* for the specified airfoil number and dataset source.

   :param airfoil_number: The ID number of the airfoil to extract.
   :type airfoil_number: int
   :param source: The dataset source, e.g., ``"turb"`` or ``"translam"``.
   :type source: str, optional
   :param plot_flag: If ``True``, plots the extracted airfoil geometry.
   :type plot_flag: bool, optional
   :return: Tuple of arrays ``(x, y)`` representing the airfoil coordinates.
   :rtype: tuple of np.ndarray

   **Example:**

   .. code-block:: python

      from unifoil.extract_data import ExtractData
      ed = ExtractData()

      # Extract from the turbulent dataset
      x, y = ed.extract_airfoil_coords(airfoil_number=3, source="turb", plot_flag=True)

      # Extract from the transitional-laminar dataset
      x, y = ed.extract_airfoil_coords(airfoil_number=3, source="translam", plot_flag=True)

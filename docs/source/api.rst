API
===

Welcome to the **UniFoil API Documentation**!  
Below is a list of the core functions and classes needed to utilize the UniFoil dataset and geometry generation tools.
Place your Python script for the interface inside **Unifoil root** with any filename of choice.
Next, at the script header, insert the following:

   .. code-block:: python

      import unifoil
      from unifoil.extract_data import ExtractData
      ed = ExtractData()

Geometry
--------

.. autosummary::
   :toctree: generated

.. py:function:: unifoil.gen_ft()

   Generates and saves the **Fully Turbulent (FT)** airfoil geometries inside a locally created folder named **airfoil_ft_geom**. 

   :return: None
   :rtype: NoneType

.. py:function:: unifoil.gen_nlf()

   Generates and saves the **Natural Laminar Flow (NLF)** airfoil geometries inside a locally created folder named **airfoil_nlf_geom**.  

   :return: None
   :rtype: NoneType

.. py:method:: ed.extract_airfoil_coords(airfoil_number, source="turb", plot_flag=False)

   Extracts the airfoil surface coordinates *(x, y)* for the specified airfoil number and dataset source.

   :param airfoil_number: The ID number of the airfoil to extract.
   :type airfoil_number: int
   :param source: The dataset source, e.g., ``"turb"`` or ``"translam"``. ``"turb"`` produces the **FT** geometries and ``"translam"`` produces the **NLF** geometries.
   :type source: str, optional
   :param plot_flag: If ``True``, plots the extracted airfoil geometry.
   :type plot_flag: bool, optional
   :return: Tuple of arrays ``(x, y)`` representing the airfoil coordinates.
   :rtype: tuple of np.ndarray

FT Geometries — Turbulent Simulation Data
-----------------------------------------

This section provides access to **surface flow-field quantities** obtained from the **Fully Turbulent (FT)** simulations within the UniFoil dataset.  
All operations under this section are handled through the method :py:meth:`ExtractData.surf_turb`.

.. autosummary::
   :toctree: generated


.. py:method:: ed.surf_turb(airfoil_number, case_number=None, field_name=None, action=None, block_index=None, xlim=None, ylim=None, levels=200, cmap="viridis", overlay_airfoil=True, vel_component=None, Mach=None, AoA=None, Re=None, save_path=None)

   Accesses and visualizes turbulent surface data for a given airfoil and case from the UniFoil dataset.

   :param airfoil_number: Target airfoil number.
   :type airfoil_number: int
   :param case_number: Case number to analyze. If ``None``, the function automatically selects the nearest available case based on ``Mach``, ``AoA``, and ``Re``.
   :type case_number: int, optional
   :param field_name: Flow variable to extract or visualize.  
                      Supported values include ``"CoefPressure"``, ``"Mach"``, and ``"Velocity"``.
   :type field_name: str, optional
   :param vel_component: Component of velocity to visualize (used only when ``field_name="Velocity"``):  
                         ``'a'`` = |u| (magnitude),  
                         ``'b'`` = uₓ (x-component),  
                         ``'c'`` = u_y (y-component).
   :type vel_component: str, optional
   :param action: The operation to perform.  
                  Supported options are:
                  
                  - ``"display_structure"`` — print the CGNS file hierarchy.  
                  - ``"plot_field"`` — visualize a specified field variable.  
                  - ``"extract_xy_quantity"`` — extract and save surface field data to file.
   :type action: str
   :param block_index: CGNS block index to target (for mid-plane or surface selection).
   :type block_index: int, optional
   :param Mach: Freestream Mach number (used for nearest-case search if ``case_number=None``).
   :type Mach: float, optional
   :param AoA: Freestream angle of attack in degrees (used for nearest-case search).
   :type AoA: float, optional
   :param Re: Reynolds number (used for nearest-case search).
   :type Re: float, optional
   :param xlim: Tuple defining x-axis limits for plots.
   :type xlim: tuple of float, optional
   :param ylim: Tuple defining y-axis limits for plots.
   :type ylim: tuple of float, optional
   :param levels: Number of contour levels for plots. Default is ``200``.
   :type levels: int, optional
   :param cmap: Colormap used for visualization. Default is ``"viridis"``.
   :type cmap: str, optional
   :param overlay_airfoil: If ``True``, overlays the airfoil geometry outline on plots.
   :type overlay_airfoil: bool, optional
   :param save_path: File path to save extracted data when using ``action="extract_xy_quantity"``.
   :type save_path: str, optional
   :return: Depending on the action — either ``None`` (for visualization) or ``(x, y, q)`` arrays containing the extracted field data.
   :rtype: None or tuple of np.ndarray

   **Description of Common Use-Cases:**

   - **Display CGNS structure:**  
     Shows the file hierarchy for the selected airfoil and case.

   - **Plot scalar fields:**  
     Visualize ``CoefPressure`` (Cp), ``Mach``, or ``Velocity`` components at a given block index.

   - **Extract numerical data:**  
     Retrieve ``(x, y, q)`` arrays for any scalar field and save them as ``.npz`` or ``.csv``.

   - **Automatic case selection:**  
     When ``case_number=None``, the routine finds and uses the case closest to the requested ``Mach``, ``AoA``, and ``Re`` values.


.. py:method:: ed.get_aero_coeffs_turb(airfoil_number, case_number)

   Returns the aerodynamic coefficients for the specified **Fully Turbulent (FT)** airfoil case.

   :param airfoil_number: Target airfoil number.
   :type airfoil_number: int
   :param case_number: Case index corresponding to the simulation condition.
   :type case_number: int
   :return: Tuple ``(Cl, Cd)`` representing lift and drag coefficients.
   :rtype: tuple of float

   **Description:**  
   Retrieves precomputed aerodynamic coefficients from the turbulent simulation database for the specified airfoil and case.


.. py:method:: ed.load_convergence_data_turb(airfoil_number, case_number, print_flag=False)

   Loads and parses the convergence history file for a **Fully Turbulent (FT)** simulation case.

   :param airfoil_number: Target airfoil number.
   :type airfoil_number: int
   :param case_number: Case index corresponding to the simulation condition.
   :type case_number: int
   :param print_flag: If ``True``, prints a summary of available convergence fields.
   :type print_flag: bool, optional
   :return: Dictionary containing convergence quantities (e.g., ``CFL``, ``Residual``, ``CL``, ``CD``) keyed by field names.
   :rtype: dict

   **Description:**  
   Provides access to solver convergence histories for monitoring simulation stability and performance.


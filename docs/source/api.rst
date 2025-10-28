API
===

.. autosummary::
   :toctree: generated

.. py:function:: unifoil.random_airfoil(returnType = "Mach")

   Returns the parameters of a random airfoil from the target UniFoil dataset.

   :param returnType: The target data to pull from a random airfoil
   :type returnType: str
   :return: Returns an array of values in the format specified. 
   :rtype: np.array

.. py:function:: unifoil.get_airfoil_path(airfoilIndex = 0)

   Return a list of random ingredients as strings.

   :param airfoilIndex: The index of the target airfoil from the Airfoil List.
   :type airfoilIndex: int
   :return: Returns the file path of the airfoil.
   :rtype: str

Machine Learning
================

.. autosummary::
   :toctree: generated

To test the UniFoil Dataset, a set of scripts were used to access the dataset and use the information for training a Machine Learning Algorithm.
This algorithm was trained in TensorFlow on the Turbulent Airfoil Data.
This section will include the documentation for this work and should serve as a starting point for ML Research.

Dataset Compilation
-------------------
The tools in Dataset Compilation are a set of functions used to generate a native TensorFlow dataset.
Unlike the other functions referenced in this project, these manually build a dataset from the raw .CGNS Files.
You may find this approach to be more flexible.

`DataGenerationLauncher.py <https://github.com/rohitroxkp7/UniFoil/blob/main/ml/dataset_compilation/DataGenerationLauncher.py>`__ can be used to create a dataset using this method.
It recursivly calls `DataGenerationUtility.py <https://github.com/rohitroxkp7/UniFoil/blob/main/ml/dataset_compilation/DataGenerationUtility.py>`__, the script which extracts and saves the .CGNS Files in a more useful format.

The Model
---------
A series of scripts exist in the `UniFoil GitHub <https://github.com/rohitroxkp7/UniFoil/tree/main/ml>`__ which are used to create and train a Convolutional Neural Network.


Performance Sampling
--------------------
`Sampling <https://github.com/rohitroxkp7/UniFoil/tree/main/ml/sampling>`__ contains a set of scripts to help examine the accuracy of the previous Convolutional Neural Network.

Installation
============

Section 1: Installation
-----------------------

The users can install the **UniFoil interface** by cloning the repository from the following link:  
`<Insert Repository Link Here>`_

Once inside the cloned repository, run the following command in your terminal:

.. code-block:: console

   pip install .

This command will install the **UniFoil interface** along with all of its dependencies.

.. warning::

   This installation process will also install all dependencies such as
   ``numpy`` and ``niceplots``. These packages may upgrade versions of existing
   libraries you already have installed locally.  
   If this could cause conflicts, it is strongly recommended to create a
   `Python virtual environment <https://docs.python.org/3/tutorial/venv.html>`_
   before installing **UniFoil**.

Section 2: Data Curation
------------------------

Upon successful completion of **Section 1**, we need to download and perform a few simple data organization steps before using **UniFoil**.

1. **Create a local folder for UniFoil usage.**  
   This folder will serve as the workspace for your datasets and scripts.  
   All UniFoil operations must be executed from within a Python script located inside this folder.  
   We will refer to this folder as the **UniFoil Root** throughout this documentation.

2. **Download the dataset from the Harvard Dataverse.**  
   The complete dataset can be downloaded from the  
   `Harvard Dataverse <https://doi.org/10.7910/DVN/VQGWC4>`_.

3. **Open the UniFoil repository**  
   Visit the `UniFoil GitHub repository <https://github.com/YourRepoLinkHere>`_  
   and download the folders **a**, **b**, and **c**.

4. **Organize and extract the data.**  
   Place all downloaded files and folders inside the **UniFoil Root**.  
   Unzip all the `.zip` and `.tar.gz` files. Once extracted, please delete the compressed files.  
   Refer to the table below for the unzip process:

   +-----------------------------------------------+---------------------------------------------+
   | **Compressed File**                           | **Extracted Folder Name**                   |
   +===============================================+=============================================+
   | ``airfoil_data_from_simulations.tar.gz``      | ``airfoil_data_from_simulations/``          |
   +-----------------------------------------------+---------------------------------------------+
   | ``unifoil_additional_data.zip``               | ``unifoil_additional_data/``                |
   +-----------------------------------------------+---------------------------------------------+
   | *(Add more rows here as needed)*              |                                             |
   +-----------------------------------------------+---------------------------------------------+

5. **Verify your folder structure.**  
   After completing steps 1–4, your **UniFoil Root** directory should look as follows:

   .. code-block:: text

      UniFoil_root/
      ├── airfoil_data_from_simulations/
      │   ├── airfoil_001_G2_A/
      │   ├── airfoil_002_G2_A/
      │   └── ...
      ├── unifoil_additional_data/
      │   ├── transition_data/
      │   ├── laminar_data/
      │   └── ...
      ├── a/
      ├── b/
      ├── c/
      └── your_script.py

We are now ready to use **UniFoil**.

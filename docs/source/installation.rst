Installation
============

Step 1: Installation
-----------------------

The users can install the **UniFoil interface** by cloning our `repository <https://github.com/rohitroxkp7/UniFoil>`_.

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
   before installing **UniFoil** and using the interface inside this virtual environment.

Step 2: Data Curation
------------------------

Upon successful completion of **Step 1**, we need to download and perform a few simple data organization steps before using **UniFoil**.

1. **Create a local folder for UniFoil usage:**  
   This folder will serve as the workspace for your datasets and scripts.  
   All UniFoil operations must be executed from within a Python script located inside this folder.  
   We will refer to this folder as the **UniFoil Root** throughout this documentation.

2. **Download the dataset from the Harvard Dataverse:**  
   The complete dataset can be downloaded from the  
   `Harvard Dataverse <https://doi.org/10.7910/DVN/VQGWC4>`_.

3. **Open the UniFoil repository:**  
   Visit the `UniFoil GitHub repository folder <https://github.com/rohitroxkp7/UniFoil/tree/main/unifoil_interface>`_  
   and download the folders **input_nlf**, **input_ft**, and the file **matched_files.csv**.
   Also download the `test scripts <https://github.com/rohitroxkp7/UniFoil/tree/main/unifoil_interface/examples>`_ **test<0-8>.py** to be run in the next step. 
   These are basically helper files and folders to help 
   with the dataset interface usage. Once downloaded, place them as is inside the **UniFoil Root**.

4. **Extract and organize the data:**  
   Place all downloaded files and folders from the  inside the **UniFoil Root**.  
   Unzip all the `.zip` and `.tar.gz` files. Once extracted, please delete the compressed files.  
   Refer to the table below for the unzip process (for folders only):

+-----------------------------------------------+-----------------------------------------------+
| **Compressed File**                           | **Extracted / Renamed Folder Name**           |
+===============================================+===============================================+
|``airfoil_data_from_simulations_transi.tar.gz``| ``airfoil_data_from_simulations_transi/``     |
+-----------------------------------------------+-----------------------------------------------+
| ``airfoil_dat_from_sim_lam.tar.gz``           | ``airfoil_data_from_simulations_lam/``        |
+-----------------------------------------------+-----------------------------------------------+
| ``airfoil_dat_from_sim_turb1.tar.gz``         | ``airfoil_data_from_simulations_turb_set1/``  |
+-----------------------------------------------+-----------------------------------------------+
| ``airfoil_dat_from_sim_turb2.tar.gz``         | ``airfoil_data_from_simulations_turb_set2/``  |
+-----------------------------------------------+-----------------------------------------------+
| ``NLF_Airfoils_Fully_Turbulent.zip``          | ``NLF_Airfoils_Fully_Turbulent/``             |
+-----------------------------------------------+-----------------------------------------------+
| ``Transi_Cutout_<1-4>.zip``                   | ``Transi_Cutout_<1-4>/``                      |
+-----------------------------------------------+-----------------------------------------------+
| ``Transi_sup_data_Cutout_<1-2>.zip``          | ``Transi_sup_data_Cutout_<1-2>/``             |
+-----------------------------------------------+-----------------------------------------------+
| ``Turb_Cutout_<1-6>.zip``                     | ``Turb_Cutout_<1-6>/``                        |
+-----------------------------------------------+-----------------------------------------------+
Note that the convention ``folder_<a-b>`` represents the series of cutout folders from folder a to folder b.

5. **Verify your folder structure.**  
   After completing steps 1–4, your **UniFoil Root** directory should look like as follows:

   .. code-block:: text

      UniFoil_root/
      ├── airfoil_data_from_simulations_transi/
      ├── airfoil_data_from_simulations_lam/
      ├── airfoil_data_from_simulations_turb_set1/
      ├── airfoil_data_from_simulations_turb_set2/
      ├── NLF_Airfoils_Fully_Turbulent/
      ├── Transi_Cutout_<1-4>/
      ├── Transi_sup_data_Cutout_<1-2>/
      ├── Turb_Cutout_<1-6>/
      ├── input_nlf/
      ├── input_ft/
      ├── matched_files.csv
      ├── test<0-8>.py
      └── your_script.py


Step 3: Dataset Check
------------------------
Once **Step 2** is complete, please run the follo


We are now ready to use **UniFoil**.

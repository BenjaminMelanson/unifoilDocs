Installation
============

Step 1: Installation
--------------------

The users can install the **UniFoil interface** by the following command:

.. code-block:: console

   pip install unifoil

This command will install the **UniFoil interface** along with all of its dependencies.

.. warning::

   This installation process will also install all dependencies such as
   ``numpy`` and ``niceplots``. These packages may upgrade versions of existing
   libraries you already have installed locally.  
   If this could cause conflicts, it is strongly recommended to create a
   `Python virtual environment <https://docs.python.org/3/tutorial/venv.html>`_
   before installing **UniFoil** and using the interface inside this virtual environment.

Step 2: Data Curation
---------------------

Upon successful completion of **Step 1**, download **UniFoil** using the command below. If flag is set to the string **"sample"**, it downloads a small working subset of the  dataset to help users quickly get around the interface and test different components and functionality. By setting the flag to string **"full"** downloads the entire dataset.

.. code-block:: python

   from unifoil.getdata import GetData
   GetData().getdata(flag="sample")

NOTICE: We are currently facing challenges with the **full** string option. We are working on setting this up. To access the full dataset, please download it manually for the timebeing.
We apologize for this inconvenience and are working on getting this option to work to enable seamless dataset download and access.
Ensure that the folder structure is as described below. Please run the command above with **sample** option to download the mandatory tools.

**Verify your folder structure.**  
After completing steps 1–2, your **UniFoil Root** directory should look like as follows:

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
   └── test<0-8>.py

Note that the convention ``folder_<a-b>`` represents the series of cutout folders from folder a to folder b.

Step 3: Dataset Check
---------------------
Once **Step 2** is complete, please run the python test scripts **test<0-8>.py** in the order: test0.py , test1.py ,..., and test8.py.
It is imperative that these tests run successfully.


We are now ready to use **UniFoil** !
Click on the **Next** button below to move to the API manual to use the **UniFoil interface**.

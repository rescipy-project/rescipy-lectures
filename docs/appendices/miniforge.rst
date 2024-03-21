======================
Miniforge installation
======================

Download and installation
=========================

The Miniforge distribution can be downloaded `here <https://github.com/conda-forge/miniforge#miniforge3>`_.
The installation is typically done by typing in a terminal:

.. code-block:: bash

    $ bash /PATH/TO/MINIFORGE_INSTALLER.sh

The basic differences of Miniconda with respect to the Anaconda distribution are:
 * Miniconda comes with conda-forge channel already added
 * the ``conda`` command is now replaced by the ``mamba`` command


Create an environment
=====================

After installation, Miniforge comes with a very minimun set of packages. The best way to install new packages is using `environments <https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#managing-environments>`_. To create and activate an environment, here named ``jlab``, simply type:

.. code-block:: bash

    mamba create -n jlab
    mamba activate jlab

Within this environment you can now install new packages. Here follows a list of commands to create a quite complete environment for data analysis. For more information on these packages have a look :doc:`here </appendices/useful_packages>`.

.. code-block:: bash

    mamba install jupyterlab

    mamba install holoviews hvplot param panel

    $(which python) -m ipykernel install --user

    mamba install h5py nodejs scikit-image
    mamba install xarray lmfit nexusformat nexpy
    mamba install -c mantid mantid mantidworkbench

    pip install nxarray

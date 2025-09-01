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

    mamba create -n jlab python=3.11
    mamba activate jlab

Within this environment you can now install new packages. Here follows a list of commands to create a quite complete environment for data analysis. For more information on these packages have a look `here </appendices/useful_packages>`_.

.. code-block:: bash

    mamba install jupyterlab hvplot scikit-image nexusformat xarray-lmfit
    pip install nxarray lmfitxps

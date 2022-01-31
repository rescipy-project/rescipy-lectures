=====================
Packages installation
=====================

via Anaconda Navigator
======================

To install a package from Anaconda Navigator, select the ``Environment`` section on the left pane. The default environment should be ``base (root)`` (in case select a different environment).
Check that the filter is set to ``All`` and not only to ``Installed``. Search for the package you want to install, select it and hit ``Apply`` on the lower right corner. The package will be installed with all the related dependencies.

If you know the package is available only in a certain channel, press the ``Channels`` button, select ``Add`` and insert the name of the channel you want to add. Indeed, many packages and dependencies are available through the ``conda-forge`` channel. It is recommended that you add it to your environment.

If you cannot find the package in any channel, then the package is not available through conda and you need to install it with pip. See the next section.

..
    Example with nxarray
    --------------------

    Let's see, as an example, how to install the ``nxarray`` package from the ``rescipy`` channel.

    Select the ``Environment`` section on the left pane. Check that the filter is set to ``All`` and not only to ``Installed``. Press the ``Channels`` button. Add the ``conda-forge`` and ``rescipy`` channels with the ``Add`` button, then press ``Update channels``. When updating has finished, search ``nxarray``, select it and hit ``Apply`` on the lower right corner. The ``nxarray`` package will be installed together with the ``nexusformat`` and ``xarray`` dependencies.


via Anaconda Prompt
===================

You can install a package launching your terminal (or Anaconda Prompt as Administrator if you are on Windows) and typing:

.. code-block:: bash

    $ conda install [packagename]

In case you need to add a channel, just type:

.. code-block:: bash

    $ conda config --add channels [channelname]

In case the package is not available through conda, you can install it with pip:

.. code-block:: bash

    $ pip install [packagename]

..
    Example with nxarray
    --------------------

    To install nxarray through your terminal (or Anaconda Prompt as Administrator on Windows) just type:

    .. code-block:: bash

        $ conda config --add channels conda-forge rescipy
        $ conda install nxarray

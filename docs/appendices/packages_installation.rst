========================
A. Packages installation
========================

Anaconda Navigator
==================

To install a package from Anaconda Navigator, select the ``Environment`` section on the left pane. The default environment should be ``base (root)`` (in case select a different environment).
Check that the filter is set to ``All`` and not only to ``Installed``. Search for the package you want to install, select it and hit ``Apply`` on the lower right corner. The package will be installed with all the related dependencies.

If you cannot find the package, or you know the package is available only in a certain channel, press the ``Channels`` button, select ``Add`` and insert the name of the channel you want to add.


Example with nxarray
--------------------

Let's see, as an example, how to install the ``nxarray`` package from the ``rescipy`` channel.

Select the ``Environment`` section on the left pane. Check that the filter is set to ``All`` and not only to ``Installed``. Press the ``Channels`` button, select ``Add`` and write ``rescipy`` and then ``Update channels``. When updating has finished, search ``nxarray``, select it and hit ``Apply`` on the lower right corner. The ``nxarray`` package will be installed together with the ``nexusformat`` and ``xarray`` dependencies.

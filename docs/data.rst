================
2. Data handling
================

2.1 Introduction
================

Standard Python containers, such as lists and dictionaries, are not designed for numerical computation. In order to efficiently perform scientific calculations, the **NumPy** package provides powerful multi-dimensional array objects, with related functions and tools for numerical calculations.

In the following sections *NumPy arrays* and higher-level data containers built on top of them (namely **pandas** *DataFrames* and **xarray** *Datasets*) will be introduced. The last section will describe how to load scientific data and conveniently store it in the *NeXus/HDF5* file format.

**Important note**: before going through this lecture you need to add the ``conda-forge`` channel to your environment and install the ``nxarray`` package through pip. Check the section on :doc:`Packages installation </appendices/packages_installation>` to learn how to do it.


2.2 NumPy arrays
================

*Numpy arrays*, provided by the `NumPy <https://numpy.org/>`_ package, are the core objects for numerical calculation in Python. Such arrays are multi-dimensional data containers, efficiently mapped into hardware memory. An array, for example, could contain measurement of an experiment, a recorded signal, pixel intensities of an image or point values in multi-dimensional space.

To have a first overview of the NumPy package and *NumPy arrays* follow the related `chapter 1.4 <https://scipy-lectures.org/intro/numpy/index.html>`_ of the SciPy lectures, the official `quick-start guide <https://numpy.org/devdocs/user/quickstart.html>`_ and the `basics for beginners <https://numpy.org/devdocs/user/absolute_beginners.html>`_. Few of these examples will also introduce already some basics of data plotting. For a more technical insight, you can have also a look at `chapter 2.2 <https://scipy-lectures.org/advanced/advanced_numpy/index.html>`_ of the SciPy lectures.


2.3 Extending NumPy
===================

NumPy provides a set of very powerful functions for data analysis, and *NumPy arrays* are extremely robust and efficient for numerical computation. On the other hand, in practical data analysis, it could be difficult to handle, explore and relate between them these arrays.

To this concern, several Python packages exist, providing more flexible and expressive data structure, extending *NumPy arrays* (which are always under the hood) and making them easier and more intuitive to use.

The most popular of these packages is `pandas <https://pandas.pydata.org/>`_, which is designed to simplify the handling of 'labeled' and tabular data, by providing the *Series* (1D) and *DataFrame* (2D) data structures. The `10 minutes introduction <https://pandas.pydata.org/docs/getting_started/10min.html>`_ and the `basic functionalities <https://pandas.pydata.org/docs/getting_started/basics.html>`_ on the official website are a good starting point to have an idea of this package.

Pandas is a very powerful package that makes tabular data handling much easier. Nevertheless, it does not well support higher-dimensional data and it is missing an integrated management of metadata (the attributes related to your data), thus making it not always suited for scientific research data.

To this concern, the `xarray <http://xarray.pydata.org/en/stable/>`_ package, built on top of NumPy and pandas, fills in excellently these lacks, being often the recommended choice in managing scientific research data. **xarray** provides the *DataArray* structure, a labeled N-dimensional array with its coordinates and attributes, and the *Dataset* structure, a container of *DataArrays* sharing the same coordinates. To have a better idea of the implementation of these two data structures, check their `design description <http://xarray.pydata.org/en/stable/data-structures.html>`_ and to have an insight on their basic usage have a look at the `quick overview <http://xarray.pydata.org/en/stable/quick-overview.html>`_ on the official website.

Here, it is worth noting that another important feature provided by xarray is the possibility to easily extend it with domain-specific functionalities, by `adding custom 'accessors' <http://xarray.pydata.org/en/stable/internals.html#extending-xarray>`_ on the xarray objects. This aspect will be covered in more detail in chapter 4. Analysis.


2.4 Loading and saving
======================

The examples and tutorials in the previous sections already showed some basics of data loading and saving, for `NumPy <https://scipy-lectures.org/intro/numpy/advanced_operations.html#loading-data-files>`_, `pandas <https://pandas.pydata.org/docs/getting_started/10min.html#getting-data-in-out>`_ and `xarray <http://xarray.pydata.org/en/stable/quick-overview.html#read-write-netcdf-files>`_ respectively.

Despite all these packages support import/export of `HDF5 <https://www.hdfgroup.org/solutions/hdf5/>`_ (a file format designed to efficiently store and organize large amount of data), none of them provide an integrated interface to the `NeXus file format <https://www.nexusformat.org/>`_, the standard *de facto* for scientific data storage, based on HDF5 and increasingly adopted in `laboratories and large-scale facilities <https://www.nexusformat.org/Facilities.html>`_ all over the world.

With this respect, the `nxarray <https://nxarray.readthedocs.io/en/latest/>`_ package comes into play, bridging xarray with the NeXus format. This package actually extends xarray, providing convenient loading and saving methods for NeXus files, directly to *DataArrays* and *Datasets*. The architecture of a NeXus file closely resembles the structure of an xarray *Dataset*, and indeed, even if they have been developed independently, both of them are actually specifically designed for handling scientific data with its relevant metadata.

After installation, you can already start to use nxarray, by importing it at any moment with:

.. code-block:: python
    
    import nxarray as nxr

Now the ``nxr.save()`` method will be available to xarray objects. For example, the ``ds`` *Dataset* of the `previous examples <http://xarray.pydata.org/en/stable/quick-overview.html>`_ can be saved to a NeXus file to disk simply with:

.. code-block:: python
    
    ds.nxr.save('ds.nxs')

You can load it back, let's say to another *Dataset* ``my_ds`` with:

.. code-block:: python
    
    my_ds = nxr.load('ds.nxs')

and you can check that the whole structure of your Dataset is the same.

A *DataArray* can also be saved to a NeXus file. In this case, a *Dataset*, with your *DataArray* inside, will be created and saved to file. For example the ``data`` *DataArray* of the previous examples can be equally saved with:

.. code-block:: python
    
    data.nxr.save('data.nxs')

This time, when you will load it, a *Dataset* will be returned, with your original *DataArray* inside it:

.. code-block:: python
    
    ds2 = nxr.load('data.nxs')
    my_data = ds2['data']

This section concludes with a consideration. **NeXus**, as reported by its `website introduction <https://manual.nexusformat.org/introduction.html>`_, 'is an effort by an international group of scientists motivated to define a common data exchange format'. Indeed, NeXus/HDF5 files are the best choice to save scientific data, and scientist are (and should) adopting it extensively.
Data values stored in .nxs file are in binary format, which is the most efficient way to handle numbers, in term of disk space and computational speed. At the same time, .nxs files can be easily loaded and their content visualized quickly, together with all the relevant metadata associated. If you still are inclined to save your data as plain text because 'I can see what's inside', most probably you are simply using the wrong tools to access your data. As the wise man said:

*"You are a scientist, not a novelist. Save your data as binary, not as text."*

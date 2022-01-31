==============================================
Useful Python packages for scientific research
==============================================

This page lists some useful packages for scientific research with Python. If you are new to Python, start with the introductory tutorials of the :doc:`reScipy lectures </index>` to learn how to use this programming language to perform data analysis.

The packages are divided into categories depending on the application domain, with a link to the relevant section of the lectures. Many of these packages are already included in the most common Python distributions, others can be installed as explained in their related documentation or in the :doc:`Packages installation </appendices/packages_installation>` appendix.


Environments
============
See :doc:`Python language </python>` for a brief introduction to these packages.

* `jupyterlab <https://jupyter.org/>`_ | Extensible user interface for interactive and reproducible computing.
* `spyder <https://docs.spyder-ide.org/>`_ | Integrated development environment for scientific data analysis.


Data structures
===============
See :doc:`Data handling </data>` for a brief introduction to these packages.

* `numpy <https://numpy.org/>`_ | Multi-dimensional arrays and matrices, with a collection of high-level mathematical functions to operate on them.
* `pandas <https://pandas.pydata.org/>`_ |  Data structures and operations for manipulating columnar and tabular data, built on NumPy.
* `xarray <https://xarray.pydata.org/>`_ | Labeled multi-dimensional NumPy-based arrays with dimensions, coordinates and attributes.


NeXus/HDF5
==========
See :doc:`Data handling </data>` for a brief introduction to these packages.

* `nexusformat <https://nexpy.github.io/nexpy/>`_ | Python API to open, create, and manipulate NeXus data written in the HDF5 format.
* `nxarray <https://nxarray.readthedocs.io/>`_ | xarray extension for high-level NeXus file input and output.


Core plotting libraries
=======================
See :doc:`Plotting </plotting>` for a brief introduction to these packages.

* `matplotlib <https://matplotlib.org/>`_ | Core plotting library for Python and NumPy arrays.
* `bokeh <http://bokeh.org/>`_ | Plotting library for interactive visualization in web browsers.


High-level plotting
===================
See :doc:`Plotting </plotting>` for a brief introduction to these packages.

* `seaborn <https://seaborn.pydata.org/>`_ | High-level interface to make plotting with matplotlib quick and effective.
* `hvplot <https://hvplot.holoviz.org/>`_ | High-level plotting library to quickly produce bokeh plots from pandas and xarray objects, based on holoviews.
* `holoviews <http://holoviews.org/>`_ | Descriptive data plotting built on top of matplotlib and bokeh.


Data analysis
=============
See the related websites and the documentation links provided for an exhaustive description of these packages.

* `scipy <https://scipy.org/>`_ | Performant algorithms for scientific computing such as optimization, integration, interpolation, algebraic equations, differential equations. See also `Scipy : high-level scientific computing <https://scipy-lectures.org/intro/scipy.html>`_ and `Image manipulation and processing using Numpy and Scipy <https://scipy-lectures.org/advanced/image_processing/index.html>`_.
* `scikit-image <https://scikit-image.org/>`_ | Collection of algorithms for image processing. See also `Scikit-image: image processing <https://scipy-lectures.org/packages/scikit-image/index.html>`_.
* `lmfit <https://lmfit.github.io/lmfit-py/>`_ | Advanced high-level interface to non-linear optimization and curve fitting.
* `nexpy <https://nexpy.github.io/nexpy/>`_ | Graphical user interface for easily access and analyse NeXus data. See in particular `Python Graphical User Interface <https://nexpy.github.io/nexpy/pythongui.html>`_.


If you are specifically interested in an overview of the packages for data visualization and dashboarding then `pyviz.org <https://pyviz.org/>`_ is what you are looking for. In the following are listed some of these packages.


Multi-dimensional visualization
===============================

* `ipyvolume <https://ipyvolume.readthedocs.io/>`_
* `pyvista <https://docs.pyvista.org/>`_
* `mayavi <https://docs.enthought.com/mayavi/mayavi/>`_
* `paraview <https://www.paraview.org/>`_


Dashboarding
============

* `ipywidgets <https://ipywidgets.readthedocs.io/>`_
* `voila <https://voila.readthedocs.io/>`_
* `panel <https://panel.holoviz.org/>`_
* `param <https://param.holoviz.org/>`_

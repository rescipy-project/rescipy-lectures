===========
3. Plotting
===========


3.1 Introduction
================

Now that you learn how to properly handle your data, it is time to visualize it!

Plotting in Jupyter Notebooks, and in general in Python, relies mainly on two alternative but complementary packages: `matplotlib <https://matplotlib.org/>`_ and `bokeh <https://bokeh.org>`_.

*Matplotlib* is the standard and widely used Python plotting backend that provides static, publication-quality plots, which can be tuned and controlled down to the smallest detail.

*Bokeh*, on the other hand, provides interactive and dynamic plotting inside Jupyter Notebooks and it is best suited to easily explore your data.

To make plotting (but not only) easier and more descriptive, the `holoviz <https://holoviz.org/>`_ project provides several packages extending matplotlib and bokeh (such as `hvplot <https://hvplot.holoviz.org>`_ and `holoviews <https://holoviews.org>`_). Make sure to check them out to be proficient in plotting with Python.

..  See Section 3.4 for more info.

**Note**: to go through this lecture you need to install the ``hvplot`` package from the ``pyviz`` channel. Check the section on :doc:`Packages installation </appendices/packages_installation>` to learn how to do it.

Before even introducing how these plotting packages work, let's try them out quickly. Indeed, in case your data is available as an xarray (or pandas) object, you can already plot it very easily with the available methods and without any prior knowledge of the plotting packages. Supposing you have a ``ds`` *Dataset* (such as the one from the `xarray examples <http://xarray.pydata.org/en/stable/quick-overview.html>`_), it can be simply plotted just with:

.. code-block:: python
    
    ds.plot()

A *matplotlib* plot will appear, representing the first available DataArray in your Dataset. Obviously the same ``.plot()`` method is directly available also for single DataArrays (as well as for pandas Series and DataFrames). As you can see, matplotlib plots are static images (see Section 3.2 for more information).

To try out *bokeh* instead, the simplest way is to import the ``hvplot`` package, which specifically provides additional methods to xarray (and pandas) objects for bokeh plotting:

.. code-block:: python
    
    import hvplot.xarray

Now you can simply type:

.. code-block:: python
    
    ds.hvplot()

And in this case a *bokeh* plot will appear, representing the same data as the plot before. As before the ``.hvplot()`` method is available for DataArrays (as well as for pandas Series and DataFrames). As you can see, bokeh plots can be zoomed and panned and many other tools are provided (see Section 3.3 for more details).


3.2 Publication-quality figures: matplotlib
===========================================

Matplotlib is the most used Python package for 2D plotting. The interface to the plotting library is provided by its *pyplot* module.
Supposing we have few simple numpy arrays:

.. code-block:: python
    
    import numpy as np
    
    x = np.linspace(-np.pi, np.pi, 256)
    c = np.cos(x)

we can import *pyplot*:

.. code-block:: python
    
    import matplotlib.pyplot as plt

and create a plot simply with:

.. code-block:: python
    
    plt.plot(x, c)

The plot properties can be set through the dedicated *plt* methods, *e.g.*:

.. code-block:: python
    
    plt.title("My Simple Plot")
    plt.plot(x, c, label='myData')
    plt.legend()

This workflow is the so-called *pyplot-style* approach, in which everything is passed to the *plt* module, which automatically manages the plots. An alternative way to use the matplotlib interface is the so-called *Object-Oriented (OO)-style* in which plot objects are assigned explicitly to variables on which methods are called:

.. code-block:: python
    
    fig, ax = plt.subplots()
    ax.set_title("My Simple Plot")
    ax.plot(x, c, label='myData')
    ax.legend()

To plot an image (*i.e.* a 2D array, here ``yy``) you can use ``imshow()``:

.. code-block:: python
    
    plt.imshow(yy)

To have a basic introduction on matplotlib functioning and terminology go through the `Usage Guide <https://matplotlib.org/tutorials/introductory/usage.html>`_ while to learn using pyplot check the `tutorial <https://matplotlib.org/tutorials/introductory/pyplot.html>`_ and the dedicated `SciPy lecture <https://scipy-lectures.org/intro/matplotlib/index.html>`_.

*Useful tip*: to understand when a plot should show up (or why it is not) be sure to read the `interactive mode <https://matplotlib.org/tutorials/introductory/usage.html#what-is-interactive-mode>`_ section of the Usage Guide.

If you are looking for a simpler and quicker interface to matplotlib have a look at `seaborn <https://seaborn.pydata.org/>`_, an high-level interface built on top of matplotlib and integrating closely with pandas data structures. Check out the `gallery <https://seaborn.pydata.org/examples/index.html>`_ to see how to obtain publication quality figures with few lines of codes.


3.3 Interactive plotting: bokeh
===============================

Matplotlib is very powerful when it comes to control each aspect of your figure. On the other hand it is not always the quickest way to explore your data. In this case, Bokeh comes into play, providing several tools to explore or stream your data, but also to combine plots and widgets within applications or dashboards.

The standard import for Bokeh in a Jupyter Notebook is:

.. code-block:: python
    
    from bokeh.plotting import figure, output_notebook, show
    output_notebook()

Here ``output_notebook()`` tells Bokeh to show the plot inline.

To create a plot just type:

.. code-block:: python
    
    p = figure()
    p.line(x)
    show(p)

Also in this case we can explicitly use the *OO-style* and change the plot properties:

.. code-block:: python
    
    p = figure(title="simple line example", x_axis_label='x', y_axis_label='y')
    l = p.line(x, legend_label="Temp.", li)
    l.glyph.line_width = 2
    show(p)

To learn more about Bokeh usage check the `User Guide <https://docs.bokeh.org/en/latest/docs/user_guide.html>`_ and the `Tutorials <https://nbviewer.ipython.org/github/bokeh/bokeh-notebooks/blob/master/index.ipynb>`_.


..  3.4 Expressive visualization: holoviews
    =======================================
    
    `Holoviews <https://holoviews.org>`_ (part of the `holoviz <https://holoviz.org>`_ project) is a Python package designed to simplify the plotting of your data, focusing on data exploration.

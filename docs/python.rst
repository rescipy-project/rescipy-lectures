===============
Python language
===============

Introduction
============

Python is a multi-platform, free and open-source programming language, first released in 1991. The current version, Python 3, is one of the most widely used programming languages to date. Python is an *interpreted* language (as opposed to *compiled* as C or Fortran), which means one does not need to compile the code before executing it. This allows you to run Python code *interactively* (you can modify it and immediately run it) through the provided Python **interpreter**, a command-line which can run the code you type in on-the-fly. Python is defines as an high-level, general purpose language and supports object-oriented programming.

An overview of the Python scientific ecosystem is given in `section 1.1 <https://scipy-lectures.org/intro/intro.html>`_ of the Scipy Lecture Notes. 


Installation
============

Python comes in various flavors and can be installed in different ways. However, the easiest way to have Python in your system is to install a scientific distribution such as the `Anaconda distribution <https://www.anaconda.com/distribution/>`_, which provides a manager for a full set of libraries and software to perform data analysis with Python.


Usage
=====

After the `Anaconda installation <https://www.anaconda.com/distribution/>`_, you can run the Ananconda Navigator which provides you with all the tools to use and setup your Python installation. 

Between these tools, `JupyterLab <https://jupyterlab.readthedocs.io/en/stable/>`_ is the core application you will use to actually perform all your data analysis. It consists of a browser-based user-interface for managing `Jupyter Notebooks <https://jupyter-notebook.readthedocs.io/en/stable/>`_.
A Jupyter Notebook is an interactive-programming browser-interface with a Python interpreter running under the hood.

After opening JupyterLab, in the Launcher main window you can open a new Notebook (or do *File > New > Notebook*) and start already to type some Python code. In the empty cell that appears, you can try to type:

.. code-block:: python
    
    print("Hello World!")

or simply

.. code-block:: python
    
    7 * 6

and press the Run button ▸ (the small triangle just above the cell) or just hit *Shift+Enter*. Congratulations, you just run your first Python code! See the next paragraph for more information on Python programming.

To have an idea on what you can actually do into a Jupyter Notebook, check the `Bokeh <https://docs.bokeh.org/en/latest/docs/gallery.html>`_ and `Holoviews <http://holoviews.org/gallery/index.html>`_ galleries, which provides some interactive examples.

You can go through the `JupyterLab User Guide <https://jupyterlab.readthedocs.io/en/stable/user/interface.html>`_ and the `Jupyter Notebook documentation <https://jupyter-notebook.readthedocs.io/en/stable/notebook.html>`_ to to get familiar with the user interface.


Actual programming
==================

Printing ``Hello World!`` has been pretty exciting but with Python you can do quite more!

Actually, one do not need at all to be a programmer to use Python for data analysis, still, knowing the basis of the language will help you immensely in doing it properly.

The `section 1.2 <https://scipy-lectures.org/intro/language/python_language.html>`_ of the Scipy Lecture Notes dedicated to Python provides a very good introduction to the language itself, and initially one should at least be familiar with the sections `1.2.1 <https://scipy-lectures.org/intro/language/first_steps.html>`_, `1.2.2 <https://scipy-lectures.org/intro/language/basic_types.html>`_ and `1.2.3 <https://scipy-lectures.org/intro/language/control_flow.html>`_. It would still be useful to go through the rest if you are interested in write some code or automatize some operations. In the latter case, the `Spyder <https://docs.spyder-ide.org/>`_ development environment, included in Anaconda, could come in handy.

Depending on your inclination, these same basic aspects are covered in more detail in chapters 1 to 5 of the excellent official `Python tutorial <https://docs.python.org/3/tutorial/>`_, while if you are planning to develop code, consider going through the chapters 6 to 10.


Modules and packages
====================

In the following are reported a few key concepts strictly related to programming, but which have to be clear in order to use efficiently Python for data analysis.

When launching a new Notebook (*i.e.* a new Python interpreter) you are provided by default with just a very basic set of functions, such as *e.g.* ``print()`` seen above or ``abs()``:

.. code-block:: python
    
    abs(-7)

which returns the absolute value of a number.

In order to perform something more, you have to load (or more precisely to **import**) additional *packages* into the active session. Many of these packages are already present by default, others can be installed. For example, supposing you want to calculate the cosine of Pi, you would do:

.. code-block:: python
    
    import math
    math.cos(math.pi)

This piece of code already illustrates two important aspects in Python:

* **Importing.** Here, ``math`` is a *module*, which is included by default in the Python distribution, but needs to be 'activated' with the ``import math`` statement.

* **Object-oriented programming.** The ``math`` module contains several objects, like functions (which in Python are called *methods*, such as ``cos()``) and variables (which in Python are named *attributes*, such as ``pi``). These objects are accessed through the dot ``.`` notation. So ``math.cos()`` or ``math.sin()`` give the cosine and sine functions, respectively, or ``math.pi`` returns the Pi constant.

To better illustrate this let's try a variant of the importing:

.. code-block:: python
    
    from math import cos, pi

This line of code is pretty self-explaining. In this way, ``cos()`` and ``pi`` have been made directly available and one can type:

.. code-block:: python

    cos(pi)

with the same result as before.

You can inspect the type of ``cos`` and ``pi`` objects with the ``type()`` function. For example:

.. code-block:: python

    type(pi)

will return ``float``, indicating ``pi`` is a floating point number.

To summarize, here ``math`` is a *module*, which contains several *methods* (*i.e.* functions, as ``cos()``) and *attributes* (*i.e.* variables, as ``pi``).

Similarly, other types of objects in Python can have their own methods and attributes. As an example, the object ``mydata``, which we assume has been properly constructed, can posses, let's say, the ``mydata.temperature`` attribute (which would probably be a float number representing the temperature at which data has been acquired) or the ``mydata.normalize()`` method (which, for example, could rescale ``mydata`` values, so that the integral under the curve is equal to one).

A collection of modules is called a *package*. So to give another example, let's take the ``convolve`` *method* contained in the ``signal`` *module* of the ``scipy`` *package*. To access this function any of this will work:

.. code-block:: python
    
    import scipy
    scipy.signal.convolve()

.. code-block:: python
    
    from scipy import signal
    signal.convolve()

.. code-block:: python
    
    from scipy.signal import convolve
    convolve()

.. code-block:: python
    
    from scipy.signal import convolve as conv
    conv()

In the last example, ``convolve`` as been imported with the *shorthand* ``conv``. This is an useful and extensively used practice, especially when you need to use the same object several times.

The same concept of importing applies similarly to Python *scripts*, simple text files, you may have written by yourself, typically with '.py' extension, and containing custom definitions of functions or other objects you want to reuse. To have an insight into this, check the section `1.2.5 <https://scipy-lectures.org/intro/language/reusing_code.html>`_ of Scipy lectures and `chapter 6 <https://docs.python.org/3/tutorial/modules.html>`_ of the Python tutorial.

===========================
Python programming language
===========================

Introduction
============

Python is a multi-platform, free and open-source programming language, first released in 1991. The current version, Python 3, is one of the most widely used programming languages at date. It is an *interpreted* language (as opposed to *compiled* as C or Fortran), which means one does not need to compile Python code before executing it. It is an high-level, general purpose language and supports object-oriented programming.

An overview of the Python scientific ecosystem is given in `section 1.1 <https://scipy-lectures.org/intro/intro.html>`_ of the Scipy Lecture Notes. 

Installation
============

Python comes in various flavors and can be installed in different ways.

However, the easiest and recommended way to have Python in your system is to install a scientific distribution such as the `Anaconda distribution <https://www.anaconda.com/distribution/>`_, which provides a manager for a full set of libraries and software to perform data analysis with Python.


Usage
=====

After the `Anaconda installation <https://www.anaconda.com/distribution/>`_, you can run the Ananconda Navigator which provides you with all the tools to use and setup your Python installation. 

Between them, `JupyterLab <https://jupyterlab.readthedocs.io/en/stable/>`_ is the core application you would use to actually perform all your data analysis. It integrates a browser-based user-interface for managing the `Jupyter Notebooks <https://jupyter-notebook.readthedocs.io/en/stable/>`_.
A Jupyter Notebook is an interactive programming interface with a Python interpreter running under the hood.

After opening JupyterLab, in the Launcher main window you can open a new Notebook (or do *File > New > Notebook*) and start already to type some Python code. In the empty cell that appears, you can try to type:

``print("Hello World!")``

and press the Run button ▸ (the small triangle just above the cell) or just hit *Shift+Enter*. Congratulations, you just run your first Python code! See the next paragraph for more information on Python programming.

To have an idea on what you can actually do, check the `Bokeh <https://docs.bokeh.org/en/latest/docs/gallery.html>`_ and `Holoviews <http://holoviews.org/gallery/index.html>`_ galleries, which provides some interactive examples.

You can go through the `JupyterLab User Guide <https://jupyterlab.readthedocs.io/en/stable/user/interface.html>`_ and the `Jupyter Notebook documentation <https://jupyter-notebook.readthedocs.io/en/stable/notebook.html>`_ to to get familiar with the user interface.


Actual Python programming
=========================

Printing ``Hello World!`` has been pretty exciting but with Python you can do quite more..

Actually, one do not need at all to be a programmer to use Python to do some data analysis, still, knowing the basis of the language will help you immensely in doing it properly.

The `section 1.2 <https://scipy-lectures.org/intro/language/python_language.html>`_ of the Scipy Lecture Notes dedicated to Python provides a very good introduction to the language itself, and one would at least be familiar with the sections `1.2.1 <https://scipy-lectures.org/intro/language/first_steps.html>`_, `1.2.2 <https://scipy-lectures.org/intro/language/basic_types.html>`_ and `1.2.3 <https://scipy-lectures.org/intro/language/control_flow.html>`_. It would still be useful to go through the rest if you are interested in write some code or automatize some operations.

Depending on your inclination, the same basic aspects are covered in much more detail in chapter 1 to 5 of the excellent official `Python tutorial <https://docs.python.org/3/tutorial/>`_, while if you are planning to develop some code, consider going through the chapters 6 to 10.

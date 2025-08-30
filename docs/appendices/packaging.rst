=========
Packaging
=========

Prerequisites
=============

In case you want to package and publish your on project, here you can find the `pip instructions <https://packaging.python.org/en/latest/tutorials/packaging-projects/>`_

Install pip utilities:

pip install build
pip/conda install twine

In the pyproject.toml folder, create the package:

python3 -m build

Upload it to PyPi (you need an account):

python3 -m twine upload dist/*


`conda instructions <https://docs.conda.io/projects/conda-build/en/latest/user-guide/tutorials/build-pkgs-skeleton.html>`_

Once you have a package [packagename] in PyPi, install conda utilities:

conda install conda-build anaconda-client

Generate setup files:

conda skeleton pypi [packagename]

If [packagename] requires additional packages use:

conda skeleton pypi --extra-specs [additionalpackage] [packagename]

If the [additionalpackage] is in a particular channel (e.g. conda-forge) you have also to add the channel to you rconfiguration:

conda config --append channels conda-forge

Building for your platform and the Python version of your environment:

conda-build [packagename]

Building for your platform and a specific Python version
conda-build --python 3.7 [packagename]

this will create build files:
~/miniconda3/conda-bld/linux-64/[packagename]-py37_0.tar.bz2

Converting for all platforms:

conda convert --platform all ~/miniconda3/conda-bld/linux-64/[packagename].tar.bz2 -o outputdir/

Upload to Anaconda (you need an account on Anaconda.org). Login first:

anaconda login

Upload (you need to to this for each platform/Python version you created):

anaconda upload ~/miniconda3/conda-bld/linux-64/[packagename]-py37_0.tar.bz2

Logout:

anaconda logout

To clean up your folders:

conda build purge

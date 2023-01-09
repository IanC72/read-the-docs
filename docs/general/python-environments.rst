===================
Python Environments
===================

- The default Python is typically 3.8. We do not officially support Python 2 usage as most packages have updated to support Python 3.
    - Look into `2to3 <https://docs.python.org/3/library/2to3.html>`__ if your code is still using Python 2!
- :code:`virtualenv` is installed across most of our servers and as many dev boards as possible.
    - We recommend to use either :code:`virtualenv` or :code:`venv` with :code:`pip` or :code:`pipenv` to install packages into your local virtual environments. Note that :code:`venv` and :code:`pip` are default packages for all Python 3.3+ installations.
- We do not typically recommend using conda, miniconda, or anaconda as these quickly eat up home directory space. 
    - However, if you want to use conda or miniconda please consider `using miniconda with your scratch space folder <https://gt-crnch-rg.readthedocs.io/en/main/general/rg-filesystems.html>`__ to store your conda environment and venvs.
    
What's the difference between pip, venv, env, conda, etc?
=============

.. list-table:: **Python Environment Tools**
    :widths: auto
    :header-rows: 1
    :stub-columns: 1

    * - Tool Name
      - Supported Python Versions
      - Purpose
      - Default on CRNCH RG
      - Notes
    * - `pip <https://pypi.org/project/pip/>`__
      - All Versions
      - Default package manager
      - Y
      - 
    * - `pipenv <https://pypi.org/project/pipenv/>`__
      - 2+
      - Package, dependency, and environment manager
      - Y
      - Combines pip and virtualenv
    * - `virtualenv <https://virtualenv.pypa.io/en/latest/>`__
      - 2+
      - Environment manager
      - Y
      - 
    * - `venv <https://docs.python.org/3/library/venv.html>`__
      - 3.3+
      - Environment manager
      - Y
      - venv is a subset of virtualenv installed by default with Python 3.3+
    * - `miniconda <https://docs.conda.io/en/latest/miniconda.html>`__
      - NA
      - Minimalist package and environment manager 
      - N
      - Suggested version of conda to use on RG; Installs its own conda/Python as well as non-Python packages
    * - `anaconda <https://www.anaconda.com/>`__
      - NA
      - Package and environment manager 
      - N
      - Not supported on RG; Installs its own Python
    * - `poetry <https://python-poetry.org/>`__
      - 3.7+
      - Package and dependency manager
      - N
      - Not supported on RG


Using venv on CRNCH RG
======================
Venv is the default virtual environment module included since Python 3.3, and it totally replaces `pyenv` since Python 3.6. Virtualenv has many similarities to venv in terms of its functionality, but we recommend using venv unless you need to use a version of Python older than 3.3. 

Installing venv
---------------

Creating a new virtual environment with venv
---------------

Activating/deactivating an environment
---------------

Installing and using packages
---------------

Using pipvenv on CRNCH RG
======================

Installing pipenv
---------------
Using the official installation instructions `here <https://pipenv.pypa.io/en/latest/install/#installing-pipenv>`__:

.. code:: shell

    python3 -m pip install pipenv

Creating a new virtual environment with pipenv
---------------

.. code:: shell

    $ pipenv install
    Creating a virtualenv for this project...
    Pipfile: /nethome/gburdell/Pipfile
    Using /usr/bin/python3.8 (3.8.13) to create virtualenv...
    ⠦ Creating virtual environment...created virtual environment CPython3.8.13.final.0-64 in 2991ms
      creator CPython3Posix(dest=/nethome/gburdell/.local/share/virtualenvs/gburdell-hxKrwMjp, clear=False, no_vcs_ignore=False, global=False)
      seeder FromAppData(download=False, pip=bundle, setuptools=bundle, wheel=bundle, via=copy, app_data_dir=/nethome/gburdell/.local/share/virtualenv)
        added seed packages: pip==22.3, setuptools==65.5.0, wheel==0.37.1
        activators BashActivator,CShellActivator,FishActivator,NushellActivator,PowerShellActivator,PythonActivator

    ✔ Successfully created virtual environment!
    Virtualenv location: /nethome/gburdell/.local/share/virtualenvs/gburdell-hxKrwMjp
    Pipfile.lock not found, creating...
    Locking [dev-packages] dependencies...
    Locking [packages] dependencies...
    Updated Pipfile.lock (db4242)!
    Installing dependencies from Pipfile.lock (db4242)...
      🐍   ▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ 0/0 — 00:00:00
    To activate this project's virtualenv, run pipenv shell.
    Alternatively, run a command inside the virtualenv with pipenv run.

Activating/deactivating an environment
---------------

.. code:: shell

   $ pipenv shell
   Launching subshell in virtual environment...
    . /nethome/gburdell/.local/share/virtualenvs/gburdell-hxKrwMjp/bin/activate
   gburdell@rg-login:~$  . /nethome/gburdell/.local/share/virtualenvs/gburdell-hxKrwMjp/bin/activate
   (gburdell) gburdell@rg-login:~$
   
OR use the code::`pipenv run` method

.. code:: shell

   $ python3 --version
   Python 3.6.8
   $ pipenv run python3 --version
   Python 3.8.13
   

Installing and using packages
---------------

.. code:: shell

   $ pipenv install 2to3
   Installing 2to3...
   Adding 2to3 to Pipfile's [packages]...
   ✔ Installation Succeeded
   Pipfile.lock (db4242) out of date, updating to (7d7dfd)...
   Locking [dev-packages] dependencies...
   Locking [packages] dependencies...
   Building requirements...
   Resolving dependencies...
   ✔ Success!
   Updated Pipfile.lock (7d7dfd)!
   Installing dependencies from Pipfile.lock (7d7dfd)...
     🐍   ▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ 0/0 — 00:00:00
   To activate this project's virtualenv, run pipenv shell.
   Alternatively, run a command inside the virtualenv with pipenv run.

Pip
==============

Conda
===================
**Note:** We typically don't recommend using anaconda due to the amount of dependencies it pulls into your home directory. If you get to where you need anaconda for a project this is typically some software that should be installed in a project space or system-wide!

Resources with more details on conda:

- `Understanding conda and pip <https://www.anaconda.com/blog/understanding-conda-and-pip>`__
- `Explaining the many flavors of conda <https://whiteboxml.com/blog/the-definitive-guide-to-python-virtual-environments-with-conda>`__
- `OLCF's guide to using conda, which assumes a sitewide installation of conda <https://docs.olcf.ornl.gov/software/python/conda_basics.html>`__.
- `NERSC's guide on using python with anaconda <https://docs.nersc.gov/development/languages/python/>`__

Poetry
===============
Poetry is a tool for dependency management and packaging similar to pipenv (which combines pip and venv). While we don't currently support it, you may be interested to try it out in your user-local setup. Read more about Poetry at the `official website <https://python-poetry.org/docs/>`__.

Bonus: IPython, IPykernel, and Jupyter
======================================
You may see some reference to IPython kernels which switching between virtual environments or especially for Jupyter notebooks. In short, IPython (`see site <https://ipython.org/>`__) is a command shell for interactive Python execution that can be extended for GUI applications and parallel computing. Jupyter is a web-based interactive tool that builds on IPython but also supports many other kernels for languages like Julia and R. You can read more about kernels for Jupyter `at this link <https://docs.jupyter.org/en/latest/projects/kernels.html>`__. 

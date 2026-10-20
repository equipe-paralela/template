.. _docs-installation:

Installation
============

The documentation requires Sphinx and Doxygen, each with its dependencies.

Doxygen
-------

.. note::
    **Doxygen** is only used in repositories that contain C source code. If it is not the case, skip this section.

Install Doxygen:

.. code-block:: bash

   sudo apt install doxygen

Sphinx
------

Go to the ``docs`` directory and create a Python virtual environment named ``env``:

.. code-block:: bash

   cd docs
   python3 -m venv env

Activate the virtual environment and install the dependencies listed in ``requirements.txt``:

.. code-block:: bash

   source env/bin/activate
   pip install -r requirements.txt

GEOLib
=============================

GEOLib is a Python package to generate, execute and parse several D-Serie and D-GEO Suite numerical models.

Installation
------------

Install GEOLib with:

.. code-block:: bash

    $ pip install d-geolib

Configure your environment using the instructions on our `Setup <https://deltares.github.io/GEOLib/latest/user/setup.html>`_ page.
You may get the console executables from the Deltares download portal, or in the case of the D-GEO Suite, you may copy the contents of the installation 'bin' directory to your console folder.

Running the source code
-----------------------

If you want to make changes to GEOLib you can run the source code from GitHub directly on your local machine, 
please follow the instructions below on how to set up your development environment using pip or poetry.

You do not need to follow these instructions if you want to use the GEOLib package in your project.

Requirements
------------

To install the required dependencies to run GEOLib code, run:

.. code-block:: bash

    $ pip install -r requirements.txt

Or, when having poetry installed (you should):

.. code-block:: bash

    $ poetry install


Testing & Development
---------------------

Make sure to have the server dependencies installed: 

.. code-block:: bash

    $ poetry install -E server

In order to run the testcode, from the root of the repository, run:

.. code-block:: bash

    $ pytest

or, in case of using Poetry

.. code-block:: bash

    $ poetry run pytest

Running flake8, mypy is also recommended. For mypy use:

.. code-block:: bash

    $ mypy --config-file pyproject.toml geolib

Running standard linters is advised:

.. code-block:: bash

    $ poetry run isort .
    $ poetry run black .


Documentation
-------------

In order to run the documentation, from the root of the repository, run:

.. code-block:: bash

    $ cd docs
    $ sphinx-build . build -b html -c .


The documentation is now in the `build` subfolder, where you can open 
the `index.html` in your browser.

Build wheel
-----------

To build a distributable wheel package, run:

.. code-block:: bash

    $ poetry build

The distributable packages are now built in the `dist` subfolder.

Update requirements.txt
-----------------------

The requirements.txt file is generated by poetry based on the pyproject.toml and poetry.lock files. In order to update/regenerate this file, run:

.. code-block:: bash

    $ poetry install
    $ poetry export -E server -f requirements.txt --output requirements.txt --without-hashes
    $ poetry export -E server -f requirements.txt --output requirements-dev.txt --with dev --without-hashes

Code linter
-----------------------

In order to run code cleanup/linter use the following commands:

.. code-block:: bash

    $ poetry run isort .
    $ poetry run black .
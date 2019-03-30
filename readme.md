# Cookiecutter PyPackage

Cookiecutter template for a Python package.

## Features

* Testing setup with ``unittest`` and ``python setup.py test`` or ``py.test``
* Travis-CI_: Ready for Travis Continuous Integration testing
* Tox_ testing: Setup to easily test for Python 3.5, 3.6, 3,7
* Bumpversion_: Pre-configured version bumping with a single command
* Auto-release to PyPI_ when you push a new tag to master (optional)
* Command line interface using Click (optional)


## Quickstart

Install the latest Cookiecutter if you haven't installed it yet (this requires
Cookiecutter 1.4.0 or higher):

```console
pip install -U cookiecutter
```

```console
cookiecutter cookieutter-pypackage
```

Then:

* Create a repo and put it there.
* Create a virtualenv: `python -m venv venv`
* Activate the environment.
* Update pip: `python -m pip install pip --force`
* Install the dev requirements into a virtualenv. (`pip install -r requirements_first_start.txt`)

Additional

* Register_ your project with PyPI.
* Add the repo to your Travis-CI_ account.
* Run the Travis CLI command `travis encrypt --add deploy.password` to encrypt your PyPI password in Travis config
  and activate automated deployment on PyPI when you push a new tag to master branch.
* Release your package by pushing a new tag to master.
* Activate your project on `pyup.io`.

## Dependency management.

`pip-tools` is used for dependency management.

Populate your `requirements.in` or `requirements_dev.in` file for pinning your dependencies.

From there generate the actual requirements txt files:

```console
pip-compile --upgrade --generate-hashes --output-file requirements.txt requirements.in
pip-compile --upgrade --generate-hashes --output-file requirements_dev.txt requirements_dev.in
```


Installing packages:

```
pip-sync requirements.txt requirements_dev.txt
```

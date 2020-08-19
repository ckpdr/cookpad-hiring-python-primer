# Python exercise prerequisites

Follow this guide to make sure that you have all the prerequisites needed for the Python
exercise. By the end of this guide, you will be able to:

- Create a local environment using [Pipenv](https://github.com/pypa/pipenv).
- Install some placeholder dependencies in that environment, using the Pipfile and required Python version.

Please use whichever method of installing an appropriate Python version on your machine that you feel comfortable
with. The end of this document provides guidance on using Pyenv for this purpose.

## Instructions

### Pipenv installation

You can follow the instructions to install Pipenv on your machine [here](https://github.com/pypa/pipenv#installation).
This primer and the exercise have been verified to work with Pipenv version `2020.6.2` and later.

### Pipenv basic usage

Once Pipenv is installed, make sure you can run the following command that will create a Python 3.8 virtual environment
for this project, including its dependencies:

```bash
pipenv install
```

The above command should produce output like:

```text
Creating a virtualenv for this project…
Pipfile: /Users/user123/cookpad-hiring-python-primer/Pipfile
Using /Users/user123/.pyenv/versions/3.8.5/bin/python3.8 (3.8.5) to create virtualenv…
⠦ Creating virtual environment...created virtual environment CPython3.8.5.final.0-64 in 364ms
  creator CPython3Posix(dest=/Users/user123/.local/share/virtualenvs/cookpad-hiring-python-primer-N69bFxr_, clear=False, global=False)
  seeder FromAppData(download=False, pip=latest, setuptools=latest, wheel=latest, via=copy, app_data_dir=/Users/user123/Library/Application Support/virtualenv/seed-v1)
  activators BashActivator,CShellActivator,FishActivator,PowerShellActivator,PythonActivator,XonshActivator

✔ Successfully created virtual environment!
Virtualenv location: /Users/user123/.local/share/virtualenvs/cookpad-hiring-python-primer-N69bFxr_
Pipfile.lock (444a6d) out of date, updating to (be5b46)…
Locking [dev-packages] dependencies…
Locking [packages] dependencies…
Building requirements...
Resolving dependencies...
✔ Success!
Updated Pipfile.lock (be5b46)!
Installing dependencies from Pipfile.lock (be5b46)…
  🐍   ▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ 5/5 — 00:00:01
To activate this project's virtualenv, run pipenv shell.
Alternatively, run a command inside the virtualenv with pipenv run.
```

Once the dependencies have been installed in the local environment, confirm that:

```text
$ pipenv run python --version
python 3.8
```

As an alternative, you can activate the environment. This way you won't have to type `pipenv run` before each command:

```text
$ pipenv shell
(python-exercise-primer) $ python --version
python 3.8
```

Finally, verify that the hello world example works correctly:

```text
$ pipenv run python -m hello
Loading .env environment variables…
Hello world
```

## Troubleshooting

In case `pipenv install` command outputs:

```text
$ pipenv install
Warning: Python 3.8 was not found on your system…
You can specify specific versions of Python with:
  $ pipenv --python path/to/python
```

You will need to install Python 3.8 on your machine. One option is [Pyenv](https://github.com/pyenv/pyenv) to
install and manage multiple Python versions on your machine. The installation instructions can be found
[here](https://github.com/pyenv/pyenv#installation).

Once `pyenv` is installed, you would be able to install the python version required in the `Pipfile`:

```bash
pyenv install 3.8
```

Now `pipenv install` should produce the expected result.

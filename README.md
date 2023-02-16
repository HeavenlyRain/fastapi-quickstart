# FastAPI - Quickstart

## Python Virtual Environments

To handle our dependencies, without needing to install packages globally, we will use python virtual environments.

### What is a virtual environment?

In simple terms, a Python virtual environment is a tool that allows you to create an isolated environment for your Python projects, separate from your system's Python environment. *Very cool! Right?*

This isolated environment contains its own Python interpreter and packages, which are independent of those installed on your system.

### How do I create a virtual enviromnet?

#### Linux

Fire up your favorite terminal. Do you have python installed? You should! I am assuming so.

To confirm you have python:

```bash
python --version
```

You can also check with `python3` or `python3.10` or so...
This guide assumes you are using python 3.x.x

Once we have checked we have python, we do the following:

```bash
python -m venv .venv
```

**What is this?**

Let's disect it:

- `python -m`: We are telling python to use a specific module
- `venv`: The specific module in this case, is `venv`
  - HELP! I don't have venv installed:
    - Odd. `venv` comes natively with python. Try installing it through apt-get or apt. See what your OS tells you.
- `.venv`: This is the name of our virtual environment. Personally, I add the preceding `.` to make it a hidden directory.
  - This will also be the name of the directory that will be created to handle the virtual environment.

Boom! Enviromnet created.

We need to activate it, though. To do that, we simply use:

```bash
source /path/to/.venv/bin/activate
```

Nice! If for whatever reason you need to get out of your virtual environment, simply type: `deactivate` in your terminal.

Now, to verify that we are in our virtual enviromnet, apart from the obvious (environment_name) in our terminal, you can also do:

```bash
which python
```

and it should output the path to our environment's `bin` directory.

### Installing packages

You can install packages from a `requirements.txt` file by using the `pip` command in the following way:

```bash
pip install -r requirements.txt
```

This command tells `pip` to install all the packages listed in the `requirements.txt` file. The `-r` option tells `pip` to read the list of packages from a file, rather than from the command line.

Make sure that the `requirements.txt` file is in the same directory where you are running the `pip` command, or provide the full path to the file in the command.

The `requirements.txt` file should contain a list of package names, one per line.

### All set! How do I use the app?

On your favorite terminal, just type:

```bash
uvicorn main:app --reload
```

Boom! api running.

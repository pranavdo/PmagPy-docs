# Installing **PmagPy**

You have multiple options for using PmagPy.

-   If you only want to use the graphical user interfaces (GUIs), you
    can download them as standalone programs ([](section_Standalone_GUI)). The
    standalone install doesn't require that you have Python, but is 
    limited to the functionality that is available in [Pmag GUI](../programs/pmag_gui.md) 
    (which includes [Demag Gui](../programs/demag_gui.md)
    and [Thellier GUI](../programs/thellier_gui.md)) without the rest of the functionality
    of PmagPy.

If you want the full **PmagPy** functionality, you have two options:

-   You can use pip to download and install the **PmagPy** function
    library and the **PmagPy** [](../programs/command_line_programs.md).

-   If you want to actively participate in developing and modifying
    **PmagPy** or be linked with the most recent commits to the project, 
    you will want to do a [](section_developer_install).

An alternative way to use the pmagpy package without downloading anything, 
is to go to the Jupyter notebooks that our hosted online at our Jupyterhub:

-   If you do not have an earthref account, go to
    <https://earthref.org/log-in> and create an account with your ORCID.
    If you do not have one of those, you need to get one.

-   Once you have logged in, go to the website:
    <https://jupyterhub.earthref.org> and login with your earthref
    account

-   Click on the 'PmagPy Online - Setup.ipynb' link and follow the
    instructions.

-   To learn more about Jupyter notebooks and Python, check out the
    online class for Earth Scientists:
    <https://github.com/ltauxe/Python-for-Earth-Science-Students>

(section_pip_install)=
## pip install

To get going with full **PmagPy** functionality, you can pip install the package
within your Python environment (e.g. your conda environment):

```
>>> pip install pmagpy
```

to get the associated command line programs, you can pip install pmag-cli

```
>>> pip install pmagpy-cli
```

You can find more specific pip install instructions for each operating system at these pages:

[OSX pip](osx_pip)

[Windows pip](windows_pip)

[Linux pip](linux_pip)

(section_Standalone_GUI)=
## Standalone GUI download

If you do not need the full PmagPy functionality, and you only want to
use Pmag GUI, MagIC GUI, Thellier GUI, and Demag GUI you can download
a standalone program. You won't need to install Python to use these
programs.

### OSX Standalone download

You can find the latest OS X standalone download here:
<https://github.com/PmagPy/PmagPy-Standalone-OSX/releases/latest>

### Windows Standalone download

You can find the latest Windows standalone download here:
<https://github.com/PmagPy/PmagPy-Standalone-Windows/releases/latest>

### Linux Standalone download

This binary has only been tested on a Ubuntu 14.04 (Trusty) distribution
and might be buggy on other distributions.

You can find the latest Linux standalone download here:
<https://github.com/PmagPy/PmagPy-Standalone-Linux/releases/latest>

(section_developer_install)=
## PmagPy developer install

If you want to get into the nitty-gritty of the code such that you are
directly working from the current version of the code in the repository, you
should do a developer install. 

If you just want to use **PmagPy** out of the box, do a regular
pip install. \*Note\*: you cannot have both a developer install and a
pip install within the same environment. 
If you want to do a developer install, make sure you
uninstall pmagpy/pmagpy-cli first if you have already installed them.

Next, choose installation instructions based on your preferred install method
(pip/developer) and your operating system (OSX/Windows/Linux).

[OSX developer](osx_developer)

[Windows developer](windows_developer)

[Linux developer](linux_developer)

## Install help

Check out our guidelines on [how to contribute to
PmagPy](https://github.com/PmagPy/PmagPy/blob/master/CONTRIBUTING.md)
for information on how to raise issues, request features, and make pull
requests.

### Details of setting your PATH

Here are the details of what the developer install script actually does.
For OS X and Linux, it adds these lines editing \$PATH to your .bashrc
file (on recent OS X version, you may need to use .zshrc instead, see more
info below):

        export PATH=/Users/***/Desktop/PmagPy/programs:$PATH
        export PATH=/Users/***/Desktop/PmagPy/programs/conversion_scripts:$PATH

And this line to your \$PYTHONPATH to your .bashrc file:

        export PYTHONPATH=$PYTHONPATH:/Users/***/Desktop/PmagPy/

where \*\*\* is your username. (Of course, these lines will depend on
exactly where you have put your PmagPy folder -- if it lives on your
home directory, your \$PATH will point there:

        export PATH=/Users/***/PmagPy/programs

If you are using Z shell instead of bash (which is the new default for
Mac starting with OSX Catalina), you will need to manually add the same
\$PATH and \$PYTHONPATH lines to .zshrc instead of .bashrc. You can
determine which shell you are using by looking at the text at the top of
your Terminal window.

For Windows, \$PATH and \$PYTHONPATH will be set in your [Control Panel
(Environment
Variables)](https://www.java.com/en/download/help/path.xml).

In Windows 10, this is done by opening Control Panel `->` System and
Security `->` System `->` Advanced system settings `->` Environment
Variables. You can see details
[here](https://www.java.com/en/download/help/path.xml). Alternatively,
just search for "environment variables" in the Windows 10 search bar
select "Edit the system environment variables".

To make the needed edits, you will first add to your existing PATH
variable or create a new PATH variable with the following values:

      C:\Users\***\Desktop\PmagPy\programs\conversion_scripts

and

      C:\Users\***\Desktop\PmagPy\programs\conversion_scripts

Next, add to your existing PYTHONPATH variable or create a new
PYTHONPATH variable with:

      C:\Users\***\Desktop\PmagPy

Important: you will need to modify the above paths based on \*your\*
username and the location where \*you\* have put the PmagPy folder. So,
if my username is limatango and I put PmagPy in my Downloads folder, my
path would read:

      C:\Users\limatango\Downloads\PmagPy

and so on.

### Common installation problems

-   Make sure you have the correct version of Python. If you run the
    command "python", you should see a message like this:

        Python 3.7.0 (default, Jun 28 2018, 07:39:16)
        [Clang 4.0.1 (tags/RELEASE_401/final)] :: Anaconda, Inc. on darwin
        Type "help", "copyright", "credits" or "license" for more information.
        >>>

-   If you try to run a **PmagPy** program and you get an ```ImportError```,
    you are probably missing a required package. Go back and install all
    required, non-default packages. If the ImportError is for a
    **PmagPy** package, go back and make sure you installed pmagpy and
    pmagpy-cli via pip or dev_setup.py.

-   If you are trying to run PmagPy programs and you run into an issue
    with python vs pythonw, you may need to link your python to pythonw:

            ln -s ~/anaconda3/bin/python3 ~/anaconda3/bin/pythonw

For more help, see the [troubleshooting section](./troubleshooting.md).

### OS-specific differences

We try to support all platforms, but there are some quirks that will
affect how you invoke **PmagPy** programs depending on your platform.
For OSX users with a pip install, you will invoke the GUIs with a
special syntax:

      pmag_gui_anaconda

For all platforms with a developer install:

      pmag_gui.py

For Windows users with a pip install:

      pmag_gui

If you see an error message like this:

      This program needs access to the screen.
      Please run with a Framework build of python, and only when you are
      logged in on the main display of your Mac.

you need to use "pmag_gui_anaconda"

If you see an error message like this:

      -bash: pmag_gui: command not found

You are either using the wrong command for your operating system, or you
haven't fully installed **PmagPy**.

## Quickstart with PmagPy notebooks

Once you have installed **PmagPy**, you may want to run the example
notebooks. You can copy example data_files and launch the **PmagPy**
notebooks from your command line with the following:

        cd Desktop
        move_data_files.py
        cd PmagPy-data
        jupyter notebook

The final command (**jupyter notebook**) will open a browser window, and
you can then click on the notebook you want to run (we recommend you
start with PmagPy_introduction.ipynb).

\*\*Note\*\*: You only have to do the move_data_files.py command once
after initial installation and then once after each update. You should
make a copy of any notebook (see File menu) if you want to make any
changes as each update will overwrite the standard notebooks.

## Next steps

Where do you want to go from here?

-   [Learn more about the **MagIC** database and download data.](../MagIC/MagIC.md)

-   [Analyze and/or upload demagnetization](../programs/demag_gui.md) and/or
    paleointensity measurement data to the **MagIC** database.

-   [Learn how to write your own programs in Python.](../resources/survival_skills.md)

-   [Learn how to use Jupyter notebooks for managing your data analysis
    workflow.](../documentation_notebooks/PmagPy_introduction.ipynb)

-   [Learn more about command line programs in the **PmagPy** software
    package.](../programs/command_line_programs.md)
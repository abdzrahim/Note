<div class="row article-body">

### Table of Contents

* * *

*   [Introduction](#introduction)
*   [Conventions throughout this tutorial](#conventions-throughout-this-tutorial)
*   [Installing git](#installing-git)
*   [Installing python 2](#installing-python-2)
*   [Installing virtual environment and virtual environment wrapper](#installing-virtual-environment-and-virtual-environment-wrapper)
*   [Installing python 3](#installing-python-3)
*   [Specifying which python to use on our virtual environments with `virtualenvwrapper`](#specifying-which-python-to-use-on-our-virtual-environments-with-virtualenvwrapper)
*   [References](#references)

### Introduction

* * *

This tutorial will show you how to set up your Windows system for python development using python 2, python 3, git, a bash terminal, virtual environments and virtual environment wrapper (`virtualenvwrapper`), a versatile tool that greatly facilitates the process of dealing with virtual environments.

The tutorial is demonstrated with Windows 7; with a little bit of google help the reader can apply the concepts to different versions of Windows.

I assume that the reader would want to install both python 2 and python 3 on the same system, which is quite typical for python developers. Some readers may even need to install more than one version of the same python (e.g., python 3.5 and python 3.6) but that's beyond the scope of this tutorial ([relatively easy to do, though](https://stackoverflow.com/questions/2547554/official-multiple-python-versions-on-the-same-machine)). If you only wanted to install just one major release of python, the tutorial would work too (just tailor your reading accordingly).

### Conventions throughout this tutorial

* * *

Please review the [conventions page](http://www.tumblingprogrammer.com/conventions-used-on-tumbling-programmer-dot-com/ "tumbling programmer's conventions page"), which will help you understand how I communicate with you through this blog.

### Installing git

* * *

Let's install [git for windows](https://git-scm.com/download/win). As of this writing, the latest version is 2.13.1.

Below are the screenshots of the options that I chose during the installation process:

![ tumbling programmer - setting windows for python development - git - select components ](https://www.tumblingprogrammer.com/media/2017/06/git-select-components.png " tumbling programmer - setting windows for python development - git - select components ")

From the above, it's critical to select the `Git Bash Here` option. It will give you the ability to run *nix like bash commands on windows (like `ls`, `grep`, etc.).

![ tumbling programmer - setting windows for python development - git - adjusting your path environment ](https://www.tumblingprogrammer.com/media/2017/06/git-adjusting-your-path-environment.png " tumbling programmer - setting windows for python development - git - adjusting your path environment ")

Ignore the red font and the warning (unless you are an advanced user of the windows command prompt; most people aren't).

![ tumbling programmer - setting windows for python development - git - choosing the ssh executable ](https://www.tumblingprogrammer.com/media/2017/06/git-choosing-the-ssh-executable.png " tumbling programmer - setting windows for python development - git - choosing the ssh executable ")

![ tumbling programmer - setting windows for python development - git - choosing https transport backend ](https://www.tumblingprogrammer.com/media/2017/06/git-choosing-https-transport-backend.png " tumbling programmer - setting windows for python development - git - choosing https transport backend ")

![ tumbling programmer - setting windows for python development - git - configuring the line ending conventions ](https://www.tumblingprogrammer.com/media/2017/06/git-configuring-the-line-ending-conventions.png " tumbling programmer - setting windows for python development - git - configuring the line ending conventions ")

![ tumbling programmer - setting windows for python development - git - configuring the terminal emulator to use with git bash ](https://www.tumblingprogrammer.com/media/2017/06/git-configuring-the-terminal-emulator-to-use-with-git-bash.png " tumbling programmer - setting windows for python development - git - configuring the terminal emulator to use with git bash ")

![ tumbling programmer - setting windows for python development - git - configuring extra options ](https://www.tumblingprogrammer.com/media/2017/06/git-configuring-extra-options.png " tumbling programmer - setting windows for python development - git - configuring extra options ")

Learning to use git or configuring it is beyond the scope of this tutorial. There is plenty of info out there, including [Getting Started - Git Basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics), [Getting Started - First-Time Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup) and [Customizing Git - Git Configuration](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration).

You now should be in a position to open a `bash` terminal by right-clicking on any Windows Explorer folder, and selecting the option shown below.

![ tumbling programmer - setting windows for python development - git - git bash here ](https://www.tumblingprogrammer.com/media/2017/06/git-git-bash-here.png " tumbling programmer - setting windows for python development - git - git bash here ")

**TIP!** | When on Windows, I usually start working on my projects by right-clicking on the python project folder, and selecting the `Git Bash Here` option.

### Installing python 2

* * *

Below are the options that I chose when I installed it on my system.

![ tumbling programmer - setting windows for python development - python 2 - select scope of installation ](https://www.tumblingprogrammer.com/media/2017/06/python2-select-scope-of-installation.png " tumbling programmer - setting windows for python development - python 2 - select scope of installation ")

![ tumbling programmer - setting windows for python development - python 2 - customize python ](https://www.tumblingprogrammer.com/media/2017/06/python2-customize-python.png " tumbling programmer - setting windows for python development - python 2 - customize python ")

Make sure to select the `Add python.exe to Path` so you can run python directly from the bash terminal (or the windows command prompt) without having to provide the whole path to the python executable file. This will allow you to run...

`./python name_of_your_python_script.py`

as opposed to...

`/c/Python27/python name_of_your_python_script.py`

Notice that for the above example I used `bash` notation, which includes forward-slash for directory separators.

Let's test that python works OK by opening a `bash` terminal anywhere and by running `which python` and `python --version`. On my system I get the following:

    jose.pumar@host ~
    $ which python
    /c/Python27/pytho

    jose.pumar@host ~
    $ python --version
    Python 2.7.13

### Installing virtual environment and virtual environment wrapper

* * *

While on the `bash` terminal, let's install `virtualenv` and `virtualenvwrapper`. Below is what it looked like for me:

**virtualenv**

    $ pip install virtualenv
    Collecting virtualenv
      Using cached virtualenv-15.1.0-py2.py3-none-any.whl
    Installing collected packages: virtualenv
    Successfully installed virtualenv-15.1.0

**virtualenvwrapper**

    $ pip install virtualenvwrapper
    Collecting virtualenvwrapper
      Using cached virtualenvwrapper-4.7.2.tar.gz
    Requirement already satisfied: virtualenv in c:\python27\lib\site-packages (from
     virtualenvwrapper)
    Collecting virtualenv-clone (from virtualenvwrapper)
      Using cached virtualenv-clone-0.2.6.tar.gz
    Collecting stevedore (from virtualenvwrapper)
      Using cached stevedore-1.23.0-py2.py3-none-any.whl
    Collecting six>=1.9.0 (from stevedore->virtualenvwrapper)
      Using cached six-1.10.0-py2.py3-none-any.whl
    Collecting pbr!=2.1.0,>=2.0.0 (from stevedore->virtualenvwrapper)
      Using cached pbr-3.0.1-py2.py3-none-any.whl
    Installing collected packages: virtualenv-clone, six, pbr, stevedore, virtualenv
    wrapper
      Running setup.py install for virtualenv-clone ... done
      Running setup.py install for virtualenvwrapper ... done
    Successfully installed pbr-3.0.1 six-1.10.0 stevedore-1.23.0 virtualenv-clone-0.
    2.6 virtualenvwrapper-4.7.2

Once `virtualenvwrapper` is installed, let's add the `virtualenvwrapper.sh` script to our `.bashrc` file by running:

    echo "source virtualenvwrapper.sh" >> ~/.bashrc

Let's source our `.bashrc` by running:

    source ~/.bashrc

Below is the output that I got:

    virtualenvwrapper.user_scripts creating C:\Users\jose.pumar\.virtualenvs\premkproject
    virtualenvwrapper.user_scripts creating C:\Users\jose.pumar\.virtualenvs\postmkproject
    virtualenvwrapper.user_scripts creating C:\Users\jose.pumar\.virtualenvs\initialize
    virtualenvwrapper.user_scripts creating C:\Users\jose.pumar\.virtualenvs\premkvirtualenv
    virtualenvwrapper.user_scripts creating C:\Users\jose.pumar\.virtualenvs\postmkvirtualenv
    virtualenvwrapper.user_scripts creating C:\Users\jose.pumar\.virtualenvs\prermvirtualenv
    virtualenvwrapper.user_scripts creating C:\Users\jose.pumar\.virtualenvs\postrmvirtualenv
    virtualenvwrapper.user_scripts creating C:\Users\jose.pumar\.virtualenvs\predeactivate
    virtualenvwrapper.user_scripts creating C:\Users\jose.pumar\.virtualenvs\postdeactivate
    virtualenvwrapper.user_scripts creating C:\Users\jose.pumar\.virtualenvs\preactivate
    virtualenvwrapper.user_scripts creating C:\Users\jose.pumar\.virtualenvs\postactivate
    virtualenvwrapper.user_scripts creating C:\Users\jose.pumar\.virtualenvs\get_env_details

By sourcing our `.bashrc` file we are making a set of scripts available on our bash terminal prompt, scripts that allow us to create, list, and delete virtual environments. More info on `virtualenvwrapper` can be found [here](http://virtualenvwrapper.readthedocs.io/en/latest/).

We are ready to test if `virtualenvwrapper` works by running `mkvirtualenv test`, which creates a virtual environment called `test`, and which is stored under `C:\Users\[your_user_name]\.virtualenvs\`. All your virtual environments will be stored there. Once the script is finished running, my terminal outputs the following:

    (test)
    jose.pumar@host MINGW64 ~
    $

Notice the name of the virtual environment that we just created (i.e., `(test)`), which signifies that our virtual environment is active.

Let's go ahead and deactivate and delete the virtual environment by running `deactivate test` and `rmvirtualenv test`. Another useful command is `lsvirtualenv`, which lists all virtual environments in your system.

### Installing python 3

* * *

Let's go ahead and install python 3\. Below are the options that I chose when I did it:

![ tumbling programmer - setting windows for python development - python 3 - install python ](https://www.tumblingprogrammer.com/media/2017/06/python3-install-python.png " tumbling programmer - setting windows for python development - python 3 - install python ") Note that on my setup I had already chosen to add python 2 to my Path in windows. Because of that, adding Python 3 to the `PATH`, as shown above, doesn't make much sense - you should only have either python 2 or python 3 but not both for one of them will not work anyways. Don't worry about the PATH issue. That's where having `virtualenvwrapper` is handy, for when we create a virtual environment we can specify which python version to use, and our virtual environment will remember that for us.

**TIP!** | If you are installing only one python (i.e., python 2 or python 3), do make sure to select the `Add Python X.Y to PATH` option.

![ tumbling programmer - setting windows for python development - python 3 - advanced installation options ](https://www.tumblingprogrammer.com/media/2017/06/python3-advanced-installation-options.png " tumbling programmer - setting windows for python development - python 3 - advanced installation options ")

Note also the path I chose to install python 3 under. The default that the installer picks is buried deep in a typical windows user app folder. I purposely chose an easier path, similar to the one that the python 2 installer picked.

### Specifying which python to use on our virtual environments with `virtualenvwrapper`

* * *

When we create virtual environments, we can tell `virtualenvwrapper` to use a particular python, like so:

    mkvirtualenv --python='[path_to_your_python]' [name_of_environment]

Example:

    mkvirtualenv --python='C:\Python36\python.exe' python36env

Below is what I get after the script is finished, and I test for version and which python is being used.

    (python36env)
    jose.pumar@host MINGW64 /c
    $ python --version
    Python 3.6.1
    (python36env)
    jose.pumar@host MINGW64 /c
    $ which python
    /C/Users/jose.pumar/.virtualenvs/python36env/Scripts/python

Go ahead and deactivate and delete the `python36env` we just created.

Similarly, I can run `mkvirtualenv --python='C:\Python27\python.exe' python27env` to create a python 2 virtual environment. Below is the output that I get when I test for version and which python is being used.

    (python27env)
    jose.pumar@host MINGW64 ~
    $ python --version
    Python 2.7.13
    (python27env)
    jose.pumar@host MINGW64 ~
    $ which python
    /C/Users/jose.pumar/.virtualenvs/python27env/Scripts/python

This concludes our tutorial. Your Windows system should be an inch closer to being the platform on which great python apps are developed.


### Syntax
1. make environment

            mkvirtualenv -p '[path_to_your_python]' [name_of_environment]
            mkvirtualenv -p 'C:\Python35\python.exe' python36env
            
2. folder of the environment
    
                (python27env)
                jose.pumar@host MINGW64 ~
                $ which python
                /C/Users/jose.pumar/.virtualenvs/python27env/Scripts/python
         
3. activate virtualenv
            
                workon python36env
                
4. deactivate virtualenv

                deactivate
                
5. remove virtualenv
                
               rmvirtualenv python35env -r


### References

* * *

This tutorial is a blend of curated information from the below sources. Many thanks to them.

1.  [Obey the Testing Goat - Pre-requisites and Assumptions](http://www.obeythetestinggoat.com/book/pre-requisite-installations.html)
2.  [Timmy Reilly's Blog - Python, Pip, virtualenv installation on Windows](http://timmyreilly.azurewebsites.net/python-pip-virtualenv-installation-on-windows/)
3.  [Timmy Reilly's Blog - Setup a virtualenv for Python 3 on Windows](http://timmyreilly.azurewebsites.net/setup-a-virtualenv-for-python-3-on-windows/)
4. **[Setting up Windows for Python development - Python 2, Python 3, Git , Bash terminal, and Virtual Environments](http://www.tumblingprogrammer.com/setting-up-windows-for-python-development-python-2-python-3-git-bash-terminal-and-virtual-environments/)**
5. **[Pip and Virtualenv on Windows](http://programwithus.com/learn-to-code/Pip-and-virtualenv-on-Windows/)

### Pip & Virtualenv on Windows
<div class="post-text">

### Install pip

Pip (Python Package Installer), [official documentation for pip.](https://pip.pypa.io/en/stable/installing/)

Usually Python3 comes with pip preinstalled. If you get an error "pip command not found", use the following command to install pip:

Download [get-pip.py](http://pip.readthedocs.io/en/stable/installing/#do-i-need-to-install-pip), make sure you're saving file to Desktop

In your Command Prompt navigate to Desktop

`cd Desktop`

Execute get-pip.py

`python get-pip.py`

Now pip should work system wide.

### virtualenv

In your Command Prompt enter:

`pip install virtualenv`

### Launch virtualenv

In your Command Prompt navigate to your project:

`cd your_project`

Within your project:

`virtualenv env`

Activate your virtualenv:

on Windows, virtualenv creates a batch file

`\env\Scripts\activate.bat`

to activate virtualenv on Windows, activate script is in the Scripts folder :

`\path\to\env\Scripts\activate`

Example:

`C:\Users\'Username'\venv\Scripts\activate.bat`

### Another way to install pip

Save the "ez_setup.py" file to your desktop form [https://bootstrap.pypa.io/ez_setup.py](https://bootstrap.pypa.io/ez_setup.py)

In your Command Prompt navigate to Desktop:

`cd Desktop`

Execute ez_setup.py:

`python ez_setup.py`

install pip:

`easy_install pip`</div>

</div>

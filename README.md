pyenv-register
==============
pyenv-register is a [pyenv](https://github.com/yyuu/pyenv) plugin
to use system installed Python.

Installing versions of python `pyenv install` takes longer time
than package management of system (like apt-get, yum).

`pyenv-register` import system installed python to pyenv environment.

Installation
------------
### Install as a pyenv plugin

    $ git clone https://github.com/doloopwhile/pyenv-register.git ~/.pyenv/plugins/pyenv-register
    $ exec "$SHELL"

Usage
-----
### Register python of package management system

    $ sudo apt-get install -y python3.3  # install by package management system

    $ /usr/bin/python3.3 --version
    Python 3.3.2+

    $ pyenv register /usr/bin/python3.3

    $ pyenv versions
    * system (set by /home/xxxx/.pyenv/version)
      system-3.3.2

A envrionment named `system-x.x.x` will be created.
The environment contains system installed libraries.

    $ sudo apt-get install -y python3-lxml

    $ pyenv register /usr/bin/python3.3

    $ pyenv shell system-3.3.2

    $ pip freeze | grep lxml
    lxml==3.2.0


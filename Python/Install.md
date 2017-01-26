## Install Python on Mac

```sh
brew install python python3
```

## Install virtualenv

```sh
pip3 install virtualenv
```

## prepare project folder

```sh
mkdir -p ~/python_projects
```

## Virtualenv

let’s install [virtualenv](https://virtualenv.pypa.io/en/stable/)

```
mkdir ~/Virtualenvs
```

open the ~/.bashrc or open ~/.zshrc file

```
vim ~/.bashrc
```

or 

```
vim ~/.zshrc
```

… and add some lines to it:

```
export PIP_REQUIRE_VIRTUALENV=true
```

restart the terminal after save the config file

after restart, we will create python 2 and python 3 environment 

```
cd ~/Virtualenvs
virtualenv -p python2 python-2-env
virtualenv -p python3 python-3-env
```

By enforce the pip only valid in Virtualenv, whenever you try to install package without Virtualenv active, pip will show below message. 

```
$ pip install markdown
Could not find an activated virtualenv (required).
```

If you need to temporarily disable this checking to install package to global, you can refer to below link 
https://hackercodex.com/guide/python-development-environment-on-mac-osx/

defining a new function in `~/.bashrc` or `~/.zshrc`

```
gpip(){
   PIP_REQUIRE_VIRTUALENV="" pip "$@"
}
```

```
$ gpip install markdown

......
Successfully installed markdown-2.6.7

```

To use python 2.7

```
cd ~/Virtualenvs
cd python-2-env
source bin/activate
```


To use python 3.x

```
cd ~/Virtualenvs
cd python-3-env
source bin/activate
```

To disable virtualenv console

```
deactivate
```

## pyenv 

Install [pyenv](https://github.com/yyuu/pyenv-installer)

```sh
curl -L https://raw.githubusercontent.com/yyuu/pyenv-installer/master/bin/pyenv-installer | bash
```

Install Python 2.7.8

```sh
pyenv install 2.7.8
```

Install Python 3.6.0

```sh
pyenv install 3.6.0
```

Create Virtualenvs for python 3.6.0 inside pyenv

```sh
pyenv virtualenv venv36
```

add default python version 3.6.0 to user profile

```sh 
echo "venv36" > ~/.pyenv/version
```

setting per folder ( optional )

```sh 
echo "venv36" > .python-version
```

For more information to sepecify the python version, please refer to [pyenv-local](https://github.com/yyuu/pyenv/blob/master/COMMANDS.md#pyenv-local)

Install numpy module

```sh
pip install numpy
```

Test numpy 

```sh
$ python

>>> import numpy as np
>>>
```

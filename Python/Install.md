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

## Miniconda3

Conda is a package manager application that quickly installs, runs, and updates packages and their dependencies

```sh 
curl -O https://repo.continuum.io/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
```

```sh 
sh Miniconda3-latest-MacOSX-x86_64.sh
```

add miniconda3 path to bash / zsh profile ( `~/.bashrc` or `~/.zshrc` )

```sh 
export PATH="/Users/moming2k/miniconda3/bin:$PATH"
```

restart terminal after save the setting

```sh 
conda create -n style-transfer python=2.7.9
```

```sh 
source activate style-transfer
```

```sh 
conda install -c conda-forge tensorflow=0.11.0
```

```sh 
conda install scipy pillow
```


## Requirements Files

"Requirements files" are files containing a list of items to be installed using pip install like so:

```sh
pip install -r requirements.txt
```

To create requirements.txt from current environment contains a pinned version of everything that was installed when pip freeze was run

```sh
pip freeze > requirements.txt
```

details can refer to pip [user guide](https://pip.readthedocs.io/en/stable/user_guide/#requirements-files)

## numpy 

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

## scikit-learn

Scikit-learn requires:
Python (>= 2.6 or >= 3.3),
NumPy (>= 1.6.1),
SciPy (>= 0.9).

```sh 
pip install SciPy
pip install NumPy
pip install sklearn

```

## TensorFlow

select proper version of TensorFlow from [this link](https://www.tensorflow.org/get_started/os_setup)

For example, `Mac OS X, GPU enabled, Python 3.4 or 3.5:`

```sh 
export TF_BINARY_URL=https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-0.12.1-py3-none-any.whl
```

```sh 
pip3 install --upgrade $TF_BINARY_URL
```


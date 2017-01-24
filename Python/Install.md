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



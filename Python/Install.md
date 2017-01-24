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

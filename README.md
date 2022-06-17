# A guide on using Python software at 42 Bangkok

# Introduction

Using python software may look daunting at first, but it is actually very simple 3 lines command after setting up. This tutorial assums you have very basic programming knowledge,

```bash
When you see this block in this turorial,
it means you have to run your code in a terminal emulator
like terminal, iterm, windows termial, command prompt, etc.
```

If you have some backgrounds in programming you may skip to [Let’s practice](https://www.notion.so/Let-s-practice-f502671f68db47758cd87d1ea3afb697)

# Installing python on your system using conda (easy)

<aside>
💡 This is only done once!

</aside>

You may already have python on your system but we don’t want install packages directly on it. We use conda to saperate working python from system python.

Go to → [https://docs.conda.io/en/latest/miniconda.html](https://docs.conda.io/en/latest/miniconda.html) . Download and install latest version.

You will be asked if you want to make conda environment default. Choose Yes.

If you used bash script to install, restart terminal.

# Althernate method for installing python on your system using Homebrew

<aside>
💡 This is only done once!

</aside>

Homebrew is a packagemanager for MacOS and Linux.

Open your terminal and type:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Then install miniconda using:

```bash
brew install --cask miniconda
conda init "$(basename "${SHELL}")"
```

# Running programs the first time

<aside>
💡 This is only done once!

</aside>

## Creating a virtual environment to run the software

```bash
conda create --name <env_name> python=<version> -y
```

Replace <env_name>, <version> with your own values,

## Install dependencies

```bash
# on some OS you can drag drop the folder to get path_to_program
cd <path_to_program>
conda activate <env_name>
pip install -r requirements.txt
```

# Running programs after initialization

```bash

conda activate <env_name>
cd <path_to_program>
python main.py
```

That’s it.

# Updating the program

<aside>
💡 For programs downloaded from git repository only. If you received a zip file, please redownload from the release page.

</aside>

```bash
cd <path_to_app>
git pull
pip install -r requirements.txt
```

# Let’s practice

Install conda using [Installing python on your system using conda (easy)](https://www.notion.so/Installing-python-on-your-system-using-conda-easy-40d75540a9b84de993d2d0a99b7d46f3)

In this example we are going to download a small program that says `hello42` from a public git repository. The program will not run if you missed a step!

## First run

```bash
# lets put our apps in a folder name Apps in your home directory
# ~ is shorthand for home directory

# crete a virtual environment to run our app
conda create --name hello42 python=3.9.7 -y
# activate the virtual environment
conda activate hello42
# check python version
python -V
>> Python 3.9.7

# change working directory to home
cd ~
# create a folder name Apps
mkdir Apps
# change working directory to Apps
cd Apps
# clone a git remote git repository
git clone git@github.com:Lodimup/Hello42.git
# change working directory to Hello42
cd Hello42
# install dependencies
pip install -r requirements.txt
# run the program
python main.py

```

You should see:

![ouput00](img/ouput00.png)

Now close the terminal. We will try subsequent runs.

## Next run

Open a new terminal tab:

<aside>
💡 Notice that we don’t need to create a virtual environment nor install dependencies

</aside>

```bash
conda activate hello42
cd ~/Apps/Hello42
python main.py
```

You should see:

![ouput00](img/ouput00.png)

# Updating the program

```bash
cd ~/Apps/Hello42
git pull
pip install -r requirements.txt
```

# Conclusion

Congratulations! You’ve learned how to use a python CLI (command line interface) program.

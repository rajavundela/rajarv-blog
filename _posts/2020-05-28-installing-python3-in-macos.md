---
title: How to install and setup Python3 in macOS
date: 2020-05-28T00:00:00.000Z
last_modified_at: 2020-06-11T11:20:20.969Z
tags:
  - "Python3"
comments: true
---
## Checking Python Installation
Starting from macOS Catalina, Python2 & Python3 is installed by default in macOS.You can check by entering `python3 --version` command in Terminal.

![python3 version](/assets/images/uploads/2020-05-28-0.jpeg){: .align-center}

Now Enter `python2 --version`  or `python --version` to check if python2 was installed. Remember entering just `python` defaults to python2.

![python2 version](/assets/images/uploads/2020-05-28-1.jpeg){: .align-center}

## [](https://pip.pypa.io/en/stable/)Pip

[Pip](https://pip.pypa.io/en/stable/) also called as Pypi is a package manager for python. For installing new packages and to update existing packages for our projects, we need pip.

### Download pip

But there's no pip installed by default. We have to install pip by downloading and running python file get-pip.py.

* Download [get-pip.py](https://bootstrap.pypa.io/get-pip.py) file.
* Go to the directory where get-pip.py file exists and execute file by entering `python3 get-pip.py`
* You can check installation by entering `pip --version`

> Note: Open new terminal window to check pip installation so that environment variables take in effect.

## Virtual Environments
Because different projects may have different python versions and packages, it is a better approach to create virtual environments for your projects to avoid dependency errors across projects.  
Creating a virtual environment makes less overhead in future.

### Create Virtual Environment
Install python packge `virtualenv` by using below command.
```shell
pip install virtualenv
```
To create a virtual environment you have to specify the path to the directory `virtualenv <path and name of virtual environment>`  
To create virtual environment named 'myvenv' in current directory enter below command.
```shell
virtualenv myvenv
```

### Activate Virtual Environment
To activate virtual environment on mac/linux enter
```shell
source myvenv/bin/activate
```
for windows enter
```
myvenv\Scripts\activate
```
You can see the name of virtual environment preceeding in your terminal.

### Deactivate Virtual Environment
For getting out of virtual environment to use your actual environment type 'deactivate'.
```shell
deactivate
``` 
![python virtual environment](/assets/images/uploads/2020-05-28-2.jpeg){: .align-center}

Happy Coding!
---
layout: page
title: Install
permalink: /install/
---

As we proceed, you will install many tools and systems on your personal computer. This page wil help you. Look here for procedures and howtos.

- - - - - 

<br/>

# Download and install [Csound](http://csound.github.io/download.html).

<br/>

- - - - - -

<br/>

# IPython and Jupyter Notebook

[IPython](http://ipython.org) within the [Jupyter Notebook](http://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/what_is_jupyter.html) is the first environment/tool we use to explore audio programming. Along with several software libraries (i.e., [NumPy](http://www.numpy.org), [SciPy](https://www.scipy.org), and [matplotlib](http://matplotlib.org)), this [stack](https://en.wikipedia.org/wiki/Solution_stack) of free/libre and open-source software (FLOSS) form a powerful and popular toolbox for scientists, engineers, and professionals.

Install these tools using one of the procedures below. When Jupyter's browser interface opens, click on _Audio IO.ipynb_. When that notebook opens, choose from the menu: _Kernel > Restart & Run All_. Check for things that look like errors and show the instructor or the TA.


## macOS

Open the Terminal app. It's in `/Applications/Utilities`. Now issue these commands:

	/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
	brew install python3
	which python # should output: /usr/local/bin/python
	pip3 install numpy scipy Pillow matplotlib jupyter ipython
	brew install git
	cd your/file/system # choose where to put the course notebooks
	git clone --depth 1 https://github.com/kybr/240A-ipython.git
	cd 240A-ipython
	jupyter notebook # this should launch your browser
	


### Windows

First, download [_numpy‑1.12.1+mkl‑cp36‑cp36m‑win\_amd64.whl_](http://www.lfd.uci.edu/~gohlke/pythonlibs/#numpy) and [_scipy‑0.19.0‑cp36‑cp36m‑win\_amd64.whl_](http://www.lfd.uci.edu/~gohlke/pythonlibs/#scipy) to your desktop.


Open PowerShell: Try<font style="font-family:Wingdings;">ÿ</font>-R, then type `powershell` and hit ENTER. Now issue the commands below:

	iex (new-object net.webclient).downloadstring('https://get.scoop.sh')
	scoop install python
	cd $HOME\Desktop
	pip install numpy‑1.12.1+mkl‑cp36‑cp36m‑win_amd64.whl scipy‑0.19.0‑cp36‑cp36m‑win_amd64.whl
	pip install Pillow matplotlib jupyter ipython
	scoop install git
	cd your/file/system # choose where to put the course notebooks
	git clone https://github.com/kybr/240A-ipython.git
	cd 240A-ipython
	copy .\afplay.vbs $HOME\AppData\Local\Microsoft\WindowsApps
	jupyter notebook # this should launch your browser
	


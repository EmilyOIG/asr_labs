# Automatic Speech Recognition (INFR 11033) Labs 

## Setup for labs

The Informatics computing labs use DICE, a Linux environment If you are not familiar with Linux and its basic usage, you can find help on [this webpage](https://computing.help.inf.ed.ac.uk/linux).

The labs all use Python within a Jupyter notebook that you can edit in your web browser.  If you are experienced with Python programming and prefer to edit code directly in your own development tool, this is fine too.

****

### Commands for setting up the Python environment

At the start of first lab, you need to set up your Python environment.  This can be used for subsequent weeks of labs, so these commands only need to be run once.

Here are the commands for setting up the environment.  These commands have been tested on DICE, but work in most other computing environments (with possible minor changes)

```shell
git clone https://github.com/ZhaoZeyu1995/asr_labs.git
cd asr_labs
source /opt/conda/etc/profile.d/conda.sh
conda create -n asr_env python=3.7
conda activate asr_env
pip install openfst-python jupyter
```

**NOTE: You will need to run some other commands to sync later weeks’ lab exercises when they become available.**

****

### Working on a computer in the lab in-person (the recommended way of working)

1.  Log in to a computer with your DICE account and password
2.  Run the commands for setting up the environment above.

Now we have set up the environment for our labs. From now on, every time we log in, we just need to run the following commands.

```shell
source /opt/conda/etc/profile.d/conda.sh 
cd asr_labs ## if you are not in this directory already
conda activate asr_env 
jupyter notebook
```

After running the last command, the default browser will be opened automatically and you can view all the files with Jupyter notebook. 
We will update the repository regularly (at least every week), and you will need to `git pull` the repository to update it with the new exercises. 
By doing so, you can also obtain the solutions, amendments of files and bug fixes. 
If you are not familiar with Git, the safest thing to do is to make a copy of the file you would like to edit (e.g. to make a copy of `asr_lab1.ipynb`, you can run `cp asr_lab1.ipynb asr_lab1_copied.ipynb`) and only make changes and run the code in the copied files (`asr_lab1_copied.ipynb` in the example). 
To get updates, all you need to do is to run `git pull` in the `asr_labs` directory (of course, you will have to `cd` to this directory first).

**NOTE: You are recommended to run `git pull` every time you `cd asr_labs` to obtain the latest files**

**NOTE: When you run `git pull`, in certain circumstances you may get an error as below**

```
error: Your local changes to the following files would be overwritten by merge:
 asr_lab1.ipynb
Please commit your changes or stash them before you merge.
Aborting
```

In this case, you can run

```
git stash
```

which stashes your changes to this repository. 

After that, you can run

```
git pull
git stash pop
```

which will update your local version to the one on Github and then merge the changes you made. 
You can view all the changes we made and the new files we uploaded to the repository on your machine now. 

**NOTE: If you are not familiar with Git is safest to create a backup copy of all your files before doing this.**

****

For remote working please refer to [Remote Working](RemoteSetup.md)

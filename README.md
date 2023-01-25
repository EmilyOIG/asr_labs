# Automatic Speech Recognition (INFR 11033) Labs 

## Setup for labs

If you are not that familiar with Linux and its basic usage, you may refer to [this webpage](https://computing.help.inf.ed.ac.uk/linux).

****

### Commands for setting up the environment

Here are the commands for setting up the environment, which can be used in most computing environments (with possible minor changes).  These commands only need to be run once for setting up the lab environment at the beginning.

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

### Working on a computer in the lab (in-person, mostly in this semester)

1.  Log in to a computer with your dice account and password
2.  Run the commands for setting up the environment above.

Now we have set up the environment for our labs. From now on, every time we log in, we just need to run the following commands.

```shell
source /opt/conda/etc/profile.d/conda.sh 
cd asr_labs ## if you are not in this directory
conda activate asr_env 
jupyter notebook
```

After running the last command, the default browser will be opened automatically and you can view all the files with jupyter notebook. 
Every week, we update new labs, and you will need to `git pull` the repository. 
By doing so, you will obtain the solutions, amendments of files and bug fixes. 
If you are not familiar with Git, the safest thing to do is to make a copy of the file you would like to edit (e.g. to make a copy of `asr_lab1.ipynb`, you can run `cp asr_lab1.ipynb asr_lab1_copied.ipynb`) and only make changes and run the codes in the copied files (`asr_lab1_copied.ipynb` in the example). 
To get updates, all you need to do is to run `git pull` in the `asr_labs` directory (of course, you will have to `cd` to this directory first).


**NOTE: When you run `git pull`, you may get an error as below**

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

### Remote working (online, not highly recommended but acceptable)

There are 3 main methods to do the labs and assignment remotely.

1.  Use the [remote desktop service](https://computing.help.inf.ed.ac.uk/remote-desktop)
2.  Use the [informatics VPN](https://computing.help.inf.ed.ac.uk/openvpn)
3.  Run codes on your own PC or Mac (not recommended as different problems may occur).

#### Remote desktop

1.  Set up the [remote desktop service](http://computing.help.inf.ed.ac.uk/remote-desktop)
2.  Connect to a remote desktop
3.  Open a terminal on the remote desktop
4.  Run `ssh s1234567.lab.inf.ed.ac.uk` (please try `ssh student.compute.inf.ed.ac.uk` instead, if the former does not work for you).
5.  Run the [commands for setting up the environment](#commands-for-setting-up-the-environment)

After the above is finished, every time you log in, you only need to run the following commands.

```shell
source /opt/conda/etc/profile.d/conda.sh 
cd asr_labs ## if you are not in this directory
conda activate asr_env 
jupyter notebook --ip=*
```

If the token is not working, `jupyter notebook password` lets you set a password.

#### VPN

1.  Set up the [informatics VPN](https://computing.help.inf.ed.ac.uk/openvpn)
2.  Connect to the VPN
3.  Open a terminal
4.  Run `ssh s1234567@s1234567.lab.inf.ed.uk` (please try `ssh s1234567@student.compute.inf.ed.ac.uk` if the former does not work for you).
5.  Enter your DICE password
6.  Run the [commands for setting up the environment](#commands-for-setting-up-the-environment)

From now on, every time you log in, you only need to run the following commands

```shell
source /opt/conda/etc/profile.d/conda.sh
cd asr_labs ## if you are not in this directory
conda activate asr_env
jupyter notebook --no-browser --ip=*
```

**NOTE: there is a `--no-browser` added in the last command.**

#### Run Jupyter on your own PC or Mac (NOT RECOMMENDED)

Before this, you might need to check if [openfst](https://www.openfst.org/twiki/bin/view/FST/WebHome) and [openfst-python](https://pypi.org/project/openfst-python/) are compatible with your operating system. 
Please make sure of this before you do the following.

1.  Install [anaconda](https://www.anaconda.com/)
2.  Open a terminal
3.  Install [openfst](https://www.openfst.org/twiki/bin/view/FST/WebHome) and [graphviz](https://graphviz.org/) by `conda install -c conda-forge openfst`and `conda install graphviz`
4.  Run the [commands for setting up the environment](#commands-for-setting-up-the-environment) but omit `source /opt/conda/etc/profile.d/conda.sh`

After setting up the environment, we may run
```shell
cd asr_labs ## if you are not in this directory
conda activate asr_env
jupyter notebook --no-browser
```

and open the link returned by jupyter notebook. 
If this does not work well, we think the easiest option is to use the [remote desktop](#remote-desktop), while the VPN and the SSH tunnel will give you the most responsive experience. 
Running jupyter on your local (personal) machine is not recommended, but you can do it, in a pinch, for the first few labs.
The files we will use for the assignment are on the school’s AFS filesystem and can’t be copied locally for data protection. While it is possible to have [AFS on your personal machine](http://computing.help.inf.ed.ac.uk/informatics-filesystem), it’s a bit complicated, and we are not able to provide any support about it. 
We suggest you do this set-up a few days before the lab starts, so it’s ready for the lab day. 
Leave some time for troubleshooting and dealing with problems that might crop up.

****
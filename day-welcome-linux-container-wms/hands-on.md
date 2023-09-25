# Workshop: Linux re-cap, Container, and WMS

## Hands-on

### Linux practices and examples

Here are some example commands and things you can try on your own. Always remember:

* use _auto completion_ as often as possible, you can always use the _tab_/_tabulator_ key to get suggestions for a command you are typing and to auto-complete folder/file names and paths - it's much faster and less error prone! (preventing typos!)
* prevent whitespaces in all folder and file names! You can use whitespaces in general, but it will complicate your work on a Linux system! Use `-`, `_`, etc... instead, e.g. `new-file.txt`
* be always careful when you delete a folder or file! It's not as easy as on windows to get your data back!

Now, open a terminal and try the following commands.

```bash
# when opening a new terminal, you always start in your home directory

# the following command shows the current path you are located (remember the tree-like structure of folders on a linux system!)
pwd

# create a new directory
mkdir testdir

# change into that new directory
cd testdir

# check where you are located now
pwd

# generate a new empty file
touch genome.fasta

# list content of the current directory
ls

# list more details, in a human readable format
ls -lah

# write some content into that file
printf ">Sequence\nATCGTACGTACGTAC\n" > genome.fasta

# check content of the file
cat genome.fasta

# change to your home directory
#     ~ is a short version of /home/$USER
cd ~

# check again the content of the file you created
# now you have to type the full path to find the file! Use auto-complete! Here we use the so-called relative path
cat testdir/genome.fasta

# you can also use the absolute path
cat /home/$USER/testdir/genome.fasta

# Hint: $USER is a so-called variable. To see the content of a variable you can also use echo:
echo $USER

# in $USER your terminal stored the information about the current user running the session. You can also define your own variables, for example you could store the absolute path to your file in a variable for easier re-usage:
GENOME=/home/$USER/testdir/genome.fasta
cat $GENOME

# please notice that we always use a leading $ sign when we want to access the content of a variable! See the difference:
echo GENOME
echo $GENOME

# generate another file
touch genome2.fasta

# copy the file to the test folder
cp genome2.fasta testdir/

# list the content of the test folder
ls -lah testdir/

# remove the original file we just generated in your home dir 
rm genome2.fasta

# is it gone?
ls -lah

# however, remember we copied the file so a copy of the file we just deleted is still in the test folder
ls -lah testdir/
```

### HPC setup 

If you are using your own (Linux) laptop or one provided for the workshops you are good to go. If you are using **an RKI Windows laptop**, you have to connect to the Linux High-Performance Cluster (HPC). You also need an account that you can request via an IT ticket. If you are working on another HPC that runs the SLURM job scheduler, such as the FU cluster, the following commands might be also interesting for you (see `srun` examples below).

#### HPC access

* Install `MobaXterm` via the RKI Software Kiosk
* Open `MobaXterm`
* Connect to the HPC login node, your instructors will tell you the name
    * Select "Session": "SSH"
    * "Remote host": "provided login node name" 
    * "Username": RKI account name

#### HPC usage

* Detailed information on HPC infrastructure and usage can be found in the RKI Confluence, search for:
    * "HPC Aufbau"
    * "HPC Nutzung"
    * "HPC FAQ"
* Opening an interactive Shell
    * On the HPC we have login and compute nodes. We dont want to compute on login nodes.
    * An interactive shell is simply any shell process that you use to type commands, and get back output from those commands. That is, a shell with which you interact. We want to connect to a compute node for the workshop.
    * Open `MobaXterm`` and connect to one of the login nodes (ask instructors)

Opening an interactive shell on the RKI HPC:
```sh
#start an interactive bash session using the default ressources
srun --pty bash -i

#start an interactive bash session using 8 CPUs, 40GB RAM, 30GB HDD
srun --cpus-per-task=8 --mem=40GB --gres=local:30 --pty bash -i

#start an interactive bash session using 10 CPUs, 80GB RAM, 50GB HDD, 1GPU
srun --cpus-per-task=10 --mem=80GB --gres=local:50 --gpus=1 --pty bash -i

#IMPORTANT to free the blocked resources after our work is done close the interactive shell via:
exit
```
Due to competing requests it may take some time until the requested resources can be provided by the system. Therefore, wait patiently until the prompt appears. Reducing requested resources might help as well.


### Install mamba (if done already on your machine: skip)

* Mamba is a packaging manager that will help us to install bioinformatics tools and to handle their dependencies automatically
* Mamba works together with the conda package manager, and makes installing packages faster
* You will use the mamba command to create environments and install packages, and conda command for some other package management tasks like configuration and activating environments (yes it can be a bit confusing)
* __Hint:__ You can create as many environments as you want! It is often convenied to have separate environments for separate tasks, pipelines, or even tools 
* In the terminal enter:

```bash
# Switch to a directory with enough space, this can be /scratch on a HPC or your ~ (remember that's short for /home/$USER) on your laptop
cd /scratch/$USER #Only if you are on the HPC, otherwise go to your $HOME

# make a new folder called 'workshop'
mkdir workshop

# switch to this folder
cd workshop

# Download mamba installer
wget "https://github.com/conda-forge/miniforge/releases/latest/download/Mambaforge-Linux-x86_64.sh"

# ATTENTION: the space in your home directory might be limited (e.g. 10 GB) and per default conda installs tools into ~/.conda/envs
# Thus, take care of your disk space!
# On the HPC you can take care of this by moving ~/.conda to /scratch and making a symlink from your home directory:
# mv ~/.conda /scratch/dot-conda
# ln -s /scratch/dot-conda ~/.conda

# Run installer
bash Mambaforge-Linux-x86_64
# Use space to scroll down the license agreement
# then type 'yes'
# accept the default install location with ENTER
# when asked whether to initialize mamba type 'yes'

# Now start a new shell or simply reload your current shell via
bash

# You should now be able to create environments, install tools and run them
```

* Set up mamba

```bash
# add repository channels for bioconda
conda config --add channels defaults
conda config --add channels bioconda
conda config --add channels conda-forge
```

* Create and activate a new conda/mamba environment

```bash
# -n parameter to specify the name
mamba create -n workshop

# activate this environment
conda activate workshop

# You should now see (workshop) at the start of each line.
# You switched from the default 'base' environment to the 'workshop' environment.
# Which is placed in a folder workshop in the ~/mambaforge/envs directory
```



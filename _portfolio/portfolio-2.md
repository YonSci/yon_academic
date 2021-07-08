---
title: "Anaconda Installation"
collection: portfolio
---

### Step: 1 Update the ubuntu package manager: 
Open the ubuntu terminal & enter the following:  
> sudo apt-get update

### Step: 2 To use desktop GUI called Anaconda Navigator the following packages must be installed:     
> apt-get install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6

### Step: 3 Installing Wget package in order to easily download the Anaconda package:
Wget package is primarily used for downloading data & files using HTTP, HTTPS, & FTP protocols from various servers. In this case, we'll use wget to download the Anaconda package.

Let's begin by installing the wget package:<br>       
> sudo apt-get install -y wget  

Once installation finished check its version by running:<br>         
> wget --version

### Step: 4 Download the anaconda installation script via wget: 
First, move to the `/tmp` directory to place the script file   
> cd /tmp   

Then, download the Anaconda installation script, it may take some time   
> wget -P /tmp https://repo.anaconda.com/archive/Anaconda3-2020.02-Linux-x86_64.sh

Verify the download script via `sha256sum` command    
> sha256sum /tmp/Anaconda3–2020.02–Linux–x86_64.sh

You should see an output that looks similar to this:  
> 2b9f088b2022edb474915d9f69a803d6449d5fdb4c303041f60ac4aefcc208bb  /tmp/Anaconda3-2020.02-Linux-x86_64.sh

Run the following command to begin the installation process; this may also take some time: 
> bash /tmp/Anaconda3-2020.02-Linux-x86_64.sh

You should see an output like the following:  
> Welcome to Anaconda3 2020.02
>
> In order to continue the installation process, please review the license agreement.  
> Please, press ENTER to continue 

Continue by pressing `<ENTER>` until you are prompted to accept the license terms: 
> Do you approve the license terms? [yes|no]  

Accept the license agreement by typing `yes`, & you'll be prompted to select an installation location & press `<ENTER>` to confirm the location
> Anaconda3 will now be installed into this location:
> /home/linuxize/anaconda3
>
>   - Press ENTER to confirm the location
>   - Press CTRL-C to abort the installation
>   - Or specify a different location below
   
Next,  you'll be asked if you want to run `conda init` & type `yes` again  
> Installation finished.
> Do you wish the installer to initialize Anaconda3
> by running conda init? [yes|no]  
  
This step will add the command-line tool conda to your system's PATH .

To activate the Anaconda installation type:  
> source ~/.bashrc
 
This will put you in the standard base environment

Cheers!!! You have now successfully installed Anaconda on your Ubuntu system.

Some more conda command lines:

To view the installation conditions, type:
> conda info

To updating conda:
> conda update conda
or 
> conda update --all

To updating anaconda:
> conda update anaconda

To create environment:
> conda create -- name  env_name

To activate conda environment named env_name:
> conda activate env_name

To deactivate the conda environment:
> conda deactivate

To see the available environments, type:
> conda info --envs

To list installed packages:
> conda list

To start Anaconda GUI type: 
> anaconda-navigator

{% include comments.html %}

---
title: "Anaconda Installation"
collection: portfolio
---

<div align="justify"> Anaconda is an open-source distribution for programming languages such as <b> <em>Python</em> </b> and <b> <em>R</em> </b>. It provides cross-platform package manager, python packages/libraries, & IDE/editors. It is mainly used for data science & scientific computing applications. It can be used with either the <b> <em> conda command-line </em> </b>  tool or the <b> <em> Anaconda Navigator</em> </b> desktop GUI. The primary benefit of Anaconda for our field is that it enables us to easily install and run various computing software packages & all dependencies in separate environments, preventing package conflict. This <a href="https://yonsci.github.io/yon_academic//portfolio/portfolio-2/" target="_top">tutorial</a> will walk you through the installation of Anaconda on an Ubuntu system. If you are using Windows & do not have Ubuntu installed, this <a href="https://yonsci.github.io/yon_academic//portfolio/portfolio-1/" target="_top">link</a> will take you to the Ubuntu installation steps on Windows-10. If you're using an Ubuntu system, you're good to go 😎 </div>

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

### Step: 5 Verify the downloaded script via `sha256sum` command:    
> sha256sum /tmp/Anaconda3–2020.02–Linux–x86_64.sh

You should see an output that looks similar to this:  
> 2b9f088b2022edb474915d9f69a803d6449d5fdb4c303041f60ac4aefcc208bb  /tmp/Anaconda3-2020.02-Linux-x86_64.sh

## Step: 6 Begin the installation process by running the following command: 
> bash /tmp/Anaconda3-2020.02-Linux-x86_64.sh

You should see an output like the following:  
> Welcome to Anaconda3 2020.02
>
> In order to continue the installation process, please review the license agreement.  
> Please, press ENTER to continue 

Continue by pressing `<ENTER>` until you are prompted to accept the license terms: 
> Do you approve the license terms? [yes,no]  

Accept the license agreement by typing `yes`, then `<ENTER>`, you'll be prompted to select an installation location & ou should see an output like the following:  
> Anaconda3 will now be installed into this location:
> /home/linuxize/anaconda3
>
>   - Press ENTER to confirm the location
>   - Press CTRL-C to abort the installation
>   - Or specify a different location below

Confirm the location by press `<ENTER>`

### Step: 7 Adding  `conda command-line`:
Next,  you'll be asked if you want to run `conda init`, type `yes` & press `<ENTER>`   
> Installation finished.
> Do you wish the installer to initialize Anaconda3
> by running conda init? [yes|no]  
  
This will add `conda command-line` tool to your system's PATH

### Step: 8 Activate Anaconda:
To activate the Anaconda installation type:  
> source ~/.bashrc
 
This will put Anaconda in the standard base environment

**_Cheers!!!🥇🥇🥇 You have now successfully installed Anaconda on your Ubuntu system_**

### Some important `conda command lines`:

To verify your Anaconda installation, type:  
<textarea style="border: none;background-color:DodgerBlue;">
conda info
</textarea>

To view the conda version:   
<textarea style="border: none;background-color:DodgerBlue;">
conda --version
</textarea>

To update conda
<textarea style="border: none;background-color:DodgerBlue;">
conda update --all
</textarea>  
or  
<textarea style="border: none;background-color:DodgerBlue;">
conda update conda
</textarea>

To update anaconda:
<textarea style="border: none;background-color:DodgerBlue;">
conda update anaconda
</textarea>

To create new environment called `env_name`: 
<textarea style="border: none;background-color:DodgerBlue;">
conda create -- name  env_name
</textarea>

To activate conda environment named env_name:
<textarea style="border: none;background-color:DodgerBlue;">
conda activate env_name
</textarea>

To deactivate the conda environment:
<textarea style="border: none;background-color:DodgerBlue;">
conda deactivate
</textarea>

To see a list of all available environments, type:
<textarea style="border: none;background-color:DodgerBlue;">
conda info --envs
</textarea>

To list installed packages:
<textarea style="border: none;background-color:DodgerBlue;">
conda list
</textarea>

To start Anaconda GUI type: 
<textarea style="border: none;background-color:DodgerBlue;">
anaconda-navigator
</textarea>
    
{% include comments.html %}

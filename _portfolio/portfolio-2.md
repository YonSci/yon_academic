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


{% include comments.html %}

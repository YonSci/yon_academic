---
title: "Anaconda Installation"
collection: portfolio
---

### Step: 1 Update the ubuntu package manager: 
Open the ubuntu terminal & enter the following:  
> sudo apt-get update

### Step: 2 To use desktop GUI called Anaconda Navigator the following packages must be installed:     
> apt-get install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6

### Step: 3 Installing & downloading Wget package in order to easily download the Anaconda package:
Wget package is primarily used for downloading data & files using HTTP, HTTPS, & FTP protocols from various servers. Wget has a number of options for downloading data. A separate tutorial on how to use Wget package will be added to the site in the near future. In this case, we'll use wget to download the Anaconda package. Let's begin by downloading and installing the wget package.
  
Open the ubuntu terminal & type in:<br>      
> sudo apt-get update -y  
> sudo apt-get install -y wget  

Once installation finished check its version by running:<br>         
> wget --version

The general wget syntax of wget:<br>       
> wget [option][URL]

To download file to specific directory use the -P option:<br>      
> wget -P [wanted_directory] [URL]

{% include comments.html %}

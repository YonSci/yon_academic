---
title: "Anaconda Installation"
collection: portfolio
---
### Step: 1 Installing Wget package
Before installing Anaconda, it's important to download Wget package which is primarily used for downloading data & files using HTTP, HTTPS, and FTP protocols from various servers. Wget has a number of options for downloading data. A separate tutorial on how to use Wget package will be added to the site in the near future. In this case, we'll use wget to download the Anaconda package. Let's begin by downloading and installing the wget package.
  
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

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
<textarea disabled="false" style="border: none;background-color:orange;">
conda info
</textarea>

To verify your Anaconda installation, type:   
<textarea disabled> conda info </textarea>

To verify your Anaconda installation, type:  
<textarea disabled="true" style="border: none;background-color:SlateBlue;">
conda info
</textarea>

To verify your Anaconda installation, type:  
<textarea disabled="true" style="border: none;background-color:DodgerBlue;">
conda info
</textarea>

To verify your Anaconda installation, type:  
<textarea disabled="true" style="border: none;background-color:Tomato;">
conda info
</textarea>

To verify your Anaconda installation, type:  
<textarea disabled="true" style="border: none;background-color:#000000;">
conda info
</textarea>


To verify your Anaconda installation, type:  
<textarea disabled="true" style="border: none;background-color:#00b71d;">
conda info
</textarea>

To verify your Anaconda installation, type:  
<textarea disabled="true" style="border: none;background-color:#ff0000;">
conda info
</textarea>



To verify your Anaconda installation, type:  
<textarea disabled="true" style="border: none;background-color:#0000ff;">
conda info
</textarea>


To verify your Anaconda installation, type:

```conda info
```      

To view the conda version:    
conda --version

To updating conda
<pre><code>
conda update --all
    </code>
 </pre>
 or
 <pre><code>
 conda update conda
 </code>
 </pre>
 
To updating anaconda:
<pre>
 <code>
conda update anaconda
</code>
</pre>

To create new environment called `env_name`: 
<pre>
 <code>
conda create -- name  env_name
</code>
</pre>

To activate conda environment named env_name:
<pre>
 <code>
conda activate env_name
</code>
</pre>

To deactivate the conda environment:
<pre>
 <code>
conda deactivate
</code>
</pre>

To see a list of all available environments, type:
<pre>
 <code>
conda info --envs
</code>
</pre>

To list installed packages:
<pre>
 <code>
conda list
</code>
</pre>

To start Anaconda GUI type: 
<pre>
 <code>
anaconda-navigator
</code>
</pre>
    
<p>This is the <code>Panel</code> constructor:</p>
<pre><code>function Panel(element, canClose, closeHandler) {
      this.element = element;
      this.canClose = canClose;
      this.closeHandler = function () { if (closeHandler) closeHandler() };
    }</code></pre>
    
{% include comments.html %}

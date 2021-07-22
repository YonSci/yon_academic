---
title: "Setting up NCO"
collection: portfolio
---

`NCO (NetCDF Operators)` is a set of open source command-line tools for analyzing, processing, viewing, & manipulating netCDF files. It was developed by atmospheric scientists at UC-Irvine.
This tutorial includes `NCO` installation steps with `conda package manager`. If you have not previously installed Anaconda on your system, you can do so by following the previous [tutorial](https://yonsci.github.io/yon_academic//portfolio/portfolio-2/).

To install NCO, launch ubuntu terminal and type the following commands:  

First create NCO environment:
<textarea style="border: none;background-color:orange;">
conda create --name nco_stable	
</textarea>  
Choose y when prompted

Once the environment is created, activate it by typing:  
<textarea style="border: none;background-color:orange;">
source activate nco_stable
</textarea>

Install the NCO package:
<textarea style="border: none;background-color:orange;">
conda install -c conda-forge nco
</textarea>

To update NCO environment to its latest version:
<textarea style="border: none;background-color:orange;">
conda update --all  
</textarea>
Choose y to approve of the udpates

You have now successfully installed NCO. To exit from `nco_stable` environment, simply type:  
<textarea style="border: none;background-color:orange;">
conda deactivate
</textarea>

#### Well done! 🥇🥇🥇 Good luck! 

{% include social-share.html %}
{% include comments.html %}

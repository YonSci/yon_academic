---
title: "Setting up CDO"
collection: portfolio
---
`Climate Data Operators(CDO)`: is a collection of command line operators for manipulating & analyzing climate model & observational data. Various formats like `GRIB1/2`, `netCDF 3/4`, `SERVICE`, `EXTRA`, & `IEG`. It is equipped with over 600 operators that are vital for climate studies. 

This tutorial includes CDO installation steps with conda package manager. If you have not previously installed Anaconda on your system, you can do so by following the previous [tutorial](https://yonsci.github.io/yon_academic//portfolio/portfolio-2/).

To install CDO, launch ubuntu terminal and type the following commands:  

First create CDO environment:
<textarea style="border: none;background-color:orange;">
conda create --name cdo_stable
</textarea>  
Choose y when prompted 

Once the environment is created, activate it by typing:  
<textarea style="border: none;background-color:orange;">
conda activate cdo_stable	
</textarea>

Install the CDO package:  
<textarea style="border: none;background-color:orange;">
conda install -c conda-forge cdo
</textarea>

To update CDO environment to its latest version:  
<textarea style="border: none;background-color:orange;">
conda update --all  
</textarea>  
Choose y to approve of the udpates

To know cdo version:  
<textarea style="border: none;background-color:orange;">
cdo -V 
</textarea>

To get help with cdo command lines, type:  
<textarea style="border: none;background-color:orange;">
cdo -h
</textarea>

You have now successfully installed CDO. To exit from `cdo_stable` environment, simply type:  
<textarea style="border: none;background-color:orange;">
conda deactivate
</textarea>

{% include comments.html %}

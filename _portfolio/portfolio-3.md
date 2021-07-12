---
title: "Conda based installation of various climate & weather data processing tools"
collection: portfolio
---
## Setting up CDO

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

                                                               
## Setting up NCO
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

## Setting up NCAR Command Language(NCL)

NCL is an interpreted language developed by [National Center for Atmospheric Research](https://ncar.ucar.edu/) for the analysis &  visualization of climate & weather data. It supports importing and exporting files in a variety of formats, including NetCDF, GRIB, HDF, HDF-EOS, & shapefile data. It is also capable of producing high-quality plots.

This tutorial includes `NCL` installation steps with `conda package manager`. If you have not previously installed Anaconda on your system, you can do so by following the previous [tutorial](https://yonsci.github.io/yon_academic//portfolio/portfolio-2/).

To install NCL, launch ubuntu terminal and type the following commands:  

First create NCL environment:
<textarea style="border: none;background-color:orange;">
onda create --name ncl_stable  
</textarea>  
Choose y when prompted

Once the environment is created, activate it by typing:
<textarea style="border: none;background-color:orange;">
conda activate ncl_stable  
</textarea>

Install the NCL package:
<textarea style="border: none;background-color:orange;">
conda install -c conda-forge ncl
</textarea>

To update NCL environment to its latest version:
<textarea style="border: none;background-color:orange;">
conda update --all
</textarea>
choose y to approve of the udpates

To check the version:
<textarea style="border: none;background-color:orange;">
ncl -V
</textarea>

You have now successfully installed `NCL`. To exit from `ncl_stable` environment, simply type:  
<textarea style="border: none;background-color:orange;">
conda deactivate
</textarea>

#### Well done! 🥇🥇🥇 Good luck! 

{% include comments.html %}

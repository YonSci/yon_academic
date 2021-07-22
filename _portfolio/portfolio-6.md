---
title: "Setting up NCAR Command Language(NCL)"
collection: portfolio
---

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

{% include social-share.html %}

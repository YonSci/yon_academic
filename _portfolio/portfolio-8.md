---
title: "NetCDF data with Python"
collection: portfolio
---

**`netCDF`** is a scientific multidimensional data format designed to store geospatial data. If you work with climate, hydrology, or oceanography data, this data format is unavoidable. As a result, the purpuse of this tutorial is to provide relevant information on how to work with netCDF files. In this tutorial, we will use the <kbd>netCDF4</kbd> python module.

📖 _**Learning objectives**_:
* Table of contents
{:toc}

## Installing netCDF4 package

To install the latest version of netCDF4, use the conda package manager. If you haven't already  installed Anaconda on your PC, you can install it by following the previous <a href="https://yonsci.github.io/yon_academic//portfolio/portfolio-2/" target="_top">post</a>.  <br> 

Start an Ubuntu terminal or an Anaconda prompt & type the following command:

<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code><span style="font-size: 200%;color:#0000ff">conda install netcdf4</span></code></pre>
</div>
</div>

Or

<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code><span style="font-size: 200%;color:#0000ff">conda install -c conda-forge netCDF4</span></code></pre>
</div>
</div>

## Reading netCDF data using Python `netCDF4` package

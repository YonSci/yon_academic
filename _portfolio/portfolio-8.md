---
title: "NetCDF data with Python"
collection: portfolio
---

📖 _**Learning objectives**_:
* Table of contents
{:toc}


## Introduction

**`netCDF`** is a scientific multidimensional data format designed to store geospatial data. If you work with climate, hydrology, or oceanography data, this data format is unavoidable. As a result, the purpuse of this tutorial is to provide relevant information on how to work with netCDF files. We will make use of the `netCDF4` python module.


## Installing netCDF4 package:

To install the latest version of netCDF4, use the conda package manager. If you haven't already  installed Anaconda on your PC, you can install it by following the previous <a href="https://yonsci.github.io/yon_academic//portfolio/portfolio-2/" target="_top">post</a>.  </div> <br> 

Start an Ubuntu terminal or an Anaconda prompt & type the following command:

 ``` python
conda install netcdf4
  ```
Or

``` python
conda install -c conda-forge netCDF4
```

<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code>
<span style="font-size: 200% color:#0000ff">ET_basin[3:5]</span> </code> </pre>
</div>
</div> 

<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">conda create --name geopandas_stable</span> 
</code>
</pre>
</div>
</div>

<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code><span style="font-size: 200%;color:#0000ff">conda create --name geopandas_stable</span></code></pre>
</div>
</div>

To switch directories, type <kbd>cd</kbd> followed by the name of the directory


## Reading netCDF data using Python `netCDF4` package

---
title: "CDO, NCL, & NCO Installation"
header-img: "https://yonsci.github.io/yon_academic//images/p3.png"
collection: portfolio
image: https://yonsci.github.io/yon_academic//images/p3.png
---

<img src="{{page.image}}" width="500" height="100" />

This tutorial demonstrates how to use the conda package manager to easily install Climate Data Operator [(CDO)](https://code.mpimet.mpg.de/projects/cdo/),  NCAR Command Language [(NCL)](https://www.ncl.ucar.edu/overview.shtml), &  netCDF Operators [(NCO)](http://nco.sourceforge.net/#Definition) climate data processing tools. If you want to process, manipulate, & generate high-quality plots from climate & weather data, you need to familiarize yourself with these tools. 

The main advantage of installing these packages with the conda package manager is that it separates environments, which prevents conflicting dependencies between different libraries & versions. First, you need to install Anaconda or Miniconda on your system. If you haven't already  installed  these package & environmental managers, you can do so by following the instructions in my previous [post](https://yonsci.github.io/yon_academic//portfolio/portfolio-2/).


* Table of contents
{:toc}
# Installing CDO
`CDO` is a collection of command line operators for manipulating & analyzing climate model & observational data. It supports importing & exporting files in a variety of formats, including `GRIB1/2`, `netCDF 3/4`, `SERVICE`, `EXTRA`, & `IEG`. It's also equipped with over 600 operators that are vital for climate studies. 

To install CDO, launch the Ubuntu terminal or Anaconda prompt & run the following commands:

Add a new environmental variable named `CDO_environment`:
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">conda create --name CDO_environment</span></code></pre>
</div>
</div>

When prompted, press `y` & `Enter` 

Once the `CDO_environment` is created, activate it by typing:  
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">conda activate CDO_environment</span></code></pre>
</div>
</div>

Install the CDO package:
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">conda install -c conda-forge cdo</span></code></pre>
</div>
</div>

To know the CDO version, type:
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">cdo -V</span></code></pre>
</div>
</div>

If you receive a version number, you have successfully installed the CDO package.

To exit the CDO environment, simply type:
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">conda deactivate</span></code></pre>
</div>
</div>

# Installing NCL

`NCL` is an interpreted language developed by [National Center for Atmospheric Research](https://ncar.ucar.edu/) for the analysis &  visualization of climate & weather data. It supports importing & exporting files in a variety of formats, including `netCDF`, `GRIB`, `HDF`, `HDF-EOS`, & `shapefiles`. It is also capable of producing high-quality plots.

To install NCL, launch the Ubuntu terminal or Anaconda prompt & run the following commands:

Add a new environmental variable named `NCL_environment`:
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">conda create --name NCL_environment</span></code></pre>
</div>
</div>

When prompted, press `y` & `Enter` 

Once the `NCL_environment` is created, activate it by typing:  
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">conda activate NCL_environment</span></code></pre>
</div>
</div>

Install the NCL package:
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">conda install -c conda-forge ncl</span></code></pre>
</div>
</div>

To know the NCL version, type:
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">ncl -V</span></code></pre>
</div>
</div>

If you receive a version number, you have successfully installed the NCL package.

To exit the NCL environment, simply type:
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">conda deactivate</span></code></pre>
</div>
</div>

# Installing NCO

`NCO` is a set of open source command-line tools for analyzing, processing, viewing, & manipulating netCDF files. It was developed by atmospheric scientists at UC-Irvine.

To install NCO, launch the Ubuntu terminal or Anaconda prompt & run the following commands:

Add a new environmental variable named `NCO_environment`:
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">conda create --name NCO_environment</span></code></pre>
</div>
</div>

When prompted, press `y` & `Enter` 

Once the `NCO_environment` is created, activate it by typing:  
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">conda activate NCO_environment</span></code></pre>
</div>
</div>

Install the NCO package:
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">conda install -c conda-forge nco</span></code></pre>
</div>
</div>
After the installation is completed, exit the NCO environment by typing:
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">conda deactivate</span></code></pre>
</div>
</div>

---

Now, to use these tools, you can use the `conda activate` command. For example, to use the CDO package, simply type:
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">conda activate CDO_environment</span></code></pre>
</div>
</div>

When you have completed your work with your CDO, type:
<div class="language-python highlighter-rouge">
<div class="highlight">
<pre class="highlight">
<code><span style="font-size: 200%;color:#0000ff">conda deactivate</span></code></pre>
</div>
</div>

Follow the same procedure to work with other packages.

**Well done! 🥇🥇🥇 Good luck!!!** 

{% include comments.html %}

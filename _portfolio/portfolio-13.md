---
title: "GIS4WRF QGIS Plugin"
author: "Yonas M."
date: "`r format(Sys.Date(),'%eth %B, %Y')`"
---
# Installation, configuration, and running the WPS and WRF programs using the GIS4WRF-QGIS Plugin

`GIS4WRF` is an opensource [QGIS](https://qgis.org/) plug-in used to pre-process input data, run simulations, and post-process results of the  [Advanced Research Weather Research and Forecasting](https://www.mmm.ucar.edu/weather-research-and-forecasting-model) (WRF) modelling workflows.

`GIS4WRF` can be used to pre-process data, configure domains, run WPS and WRF, and visualize your simulation results in your local machine. It provides pre-compiled binaries. It also allow to download geographical data and meteorological data used by the WRF Model.

Detail information on the `GIS4WRF` can be found at the <https://gis4wrf.github.io/>

## Installation of GIS4WRF QGIS Plugin

The installation of GIS4WRF is a straightforward. Go to `Plugins` ➡️ `Manage and Install Plugins...`, on the left side you will see list of all plugins available for QGIS, search for `GIS4WRF` and press the `Install Plugin` button.

![](/home/yoni/Pictures/Screenshots/GISWRF_plugin1.png)

## Configuration of GIS4WRF QGIS Plugin

To configure `GIS4WRF` within QGIS: Go to the `Settings`➡️ `Option...&rarr️ `GIS4WRF` menu in QGIS. ![](/home/yoni/Pictures/Screenshots/setting.png) Here you can configure:

1)  Working directory for your GIS4WRF projects.

2)  Enable integration with WPS/WRF.

3)  Download pre-built WPS/WRF binaries.

4)  Enable integration with NCAR's Research Data Archive.

### Set Working Directory

The GIS4WRF working directory is used for

-   storing GIS4WRF projects,

-   datasets

-   pre-compiled WRF/WPS binaries.

Make sure that you have enough space and have set the correct permissions for the default working directory.

![](/home/yoni/Pictures/Screenshots/gis4wrf_options_working_dir.png)

### Enable integration with WPS and WRF

The `WRF Pre-Processing System (WPS)` is a collection of Fortran and C programs that provides data used as input to the `real.exe` program. There are three main programs and a number of auxiliary programs that are part of WPS.

The three main programs are:

-   geogrid.exe

    -   Defines the model horizontal domain

    -   Horizontally interpolates static data to the model domain

    -   Output conforms to the WRF I/O API

-   ungrib.exe

    -   Decodes Grib Edition 1 and 2 data

    -   Uses tables to decide which variables to extract

    -   Supports isobaric and generalized vertical coordinates

    -   Output is in a non-WRF-I/O-API form, referred to as an intermediate format

-   metgrid.exe

    -   Ingest static data and raw meteorological fields

    -   Horizontally interpolate meteorological fields to the model domain

    -   Output conforms to WRF I/O API

There are two options to run the WPS and WRF on your machine:

1)  You can use the pre-compiled WPS and WRF binaries prepared by the `GIS4WRF`.

2)  If you have your own WPS and WRF binaries set the path of the WPS and WRF directory.  

This can be done in the WPS/WRF distribution section and first you have to install MPI in your system. On Linux system you can install it using the following command:

`sudo apt-get update && sudo apt-get install mpich`

-   Make sure you check the MPI box

-   Set the number of MPI processors that matches your processors.

-   To use the pre-compiled WPS and WRF binaries prepared by GISWRF plugin first click the `Download Pre-Compiled WPS Distribution...` and when completed click the `Download Pre-Compiled WRF Distribution...` button.

![](/home/yoni/Pictures/Screenshots/gis4wrf_options_wps_wrf_distro.png)

### Integration with NCAR's Research Data Archive

The integration with  [NCAR's Research Data Archive](https://rda.ucar.edu/) through the [GIS4WRF Met data downloader](https://gis4wrf.github.io/documentation/#met) are needed to download the following two dataset:

1.  Geographical data used by the WRF Preprocessing System (WPS),

2.  Meteorological data used to create initial and boundary conditions.

    ![](/home/yoni/Pictures/Screenshots/gis4wrf_options_rda.png)

First you need to create account at the <https://rda.ucar.edu/index.html?hash=data_user&action=register> and put these login information (`username` and `password`) at the NCAR's Research Data Archive section as shown in the above image. Finally click OK to save all changes and restart the QGIS.

Detail information on the configuration can be found at <https://gis4wrf.github.io/configuration/>

### Running WRF

The GIS4WRF has three main tabs `Datasets`, `Simulation`, and `View`. To successfully run WRF simulations/experiments on your local machine using GIS4WRF, the following steps are mandatory.

1)  **Create project**

Start by launching `QGIS` &rarr️ `Plugins`&rarr️ `GIS4WRF`.

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-07%2011-51-54.png)

Create a new GIS4WRF project by going to `Simulation`➡️ `General`&rarr `Create a GIS4WRF Project`.

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-07%2011-33-57.png)

The General tab is used to create a new project or open an existing GIS4WRF project. By default a project is created inside the GIS4WRF default working directory. This will open a new window. Create a new folder named `arba_minch_2020_07_08_09` and click on `Choose`.

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2006-42-20.png)

**Define domain**

GIS4WRF defines domains from the inside out. This allows you to have full control on positioning the inner-most domain.

It is advisable to set the extent of the datasets  first in-order to reduce the amount of data to be download. GIS4WRF allow to easily create, import, and export WRF domains through a GUI interface.

This configuration will be used to generate the relevant sections in `namelist.wps` and `namelist.wrf`. `Namelist` are inputs to the main programs.

Navigate to `Simulation` &rarr `Domain`➡️ `Map Type` and fill the sections as follows:

Select coordinate System (GCS) or Projection

-   GCS/Projection: `Mercator`

-   True Latitude 1: `5.99`

-   Click on `Set Map CRS`

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-07%2012-38-12.png)

**Set the Horizontal Grid Spacing:** `1000 m`:

**Enable (tick) Advanced Configuration**

-   Center Point Longitude: `37.55`
-   Center Point Latitude: `5.99`

**Grid Extent**

-   Grid Extent (Horizontal): `21`
-   Grid Extent (Vertical): `21`

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2006-47-30.png)

**Enable (tick) Parenting**

-   Number of Parenting: `1`
-   `Parent 1`: Child-to-Parent Ratio: `3`
-   Padding (Top, Right, Bottom, Left): `10`
-   `Parent 2`: Child-to-Parent Ratio:`3`
-   Padding (Top, Right, Bottom, Left): `10`

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2007-20-28.png)

You can view the domain layers individually by clicking and expanding the WRF domain vector and grid groups in the QGIS panel. The WRF Domain Vector layers with 2 domains. ![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2007-35-09.png)

The WRF Domain Raster layers with 2 domains. ![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2007-38-43.png)

**Download input data**

-   Geographical data

Navigate to `Dataset`  ➡️  `Geo`. Click on `Select Mandatory Fields in Lowest Resolution` and `Download Selected Datasets`. The lowest resolution fields are useful for model testing and educational purposes.

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-07%2013-33-36.png)

When the process is complete, you will receive a message indicating that the data was successfully downloaded.

-   Meteorological data

To download the meteorological data navigate to `Dataset`➡️ `Met` and select:

-   Dataset: `ds083.3`
-   Product: `Analysis`
-   Start: `7/8/20 12:00 PM` 
-   End: `7/9/20 7:00 AM` 

Under `Extent` click on `subset`, then select `Domain 2` on the `Layers` panel of QGIS and click on `Set from Active Layer`  to subset your request. Finally, click `Download` to submit and download your request. 

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-07%2019-03-12.png) 

When the process is complete, you will receive a message indicating that the data was successfully downloaded.

**Select input data**

GIS4WRF automatically pre-populates WPS and WRF namelists based on your domain configuration and data selection.

Go to `Simulation`➡️ `Data`. As you already have downloaded geographical and meteorological data, simply type `lowres` in the `Domain 1` and  `Domain 2` fields.

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2007-47-55.png) click on `2020-07-08 12:00 - 2020-07-09 06:00` and `Use Dataset Selection from List` to select the meteorological data. It will show the current configuration period

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-07%2019-21-01.png)

**Configure and run**

There are two main processes involved in running a real-case simulation:

To view the default configuration, Go to `Simulation`➡️ `Run`, and click on `Open configuration` and it will display the general setting of the`namelist.wps`.


![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2007-53-34.png)

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2007-52-28.png)

1)  To configure and run the WRF Preprocessing System (WPS), the following three programs must be successfully run: `Geogrid`,  `Ungrib`, and `Metgrid`.

Go to `Simulation`➡️ `Run` and click on the `Geogrid`&rarr️  `Ungrib` &rarr️ `Metgrid` buttons individually.

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-07%2019-42-46.png) All the programs must finish without errors.

![](/home/yoni/Pictures/Screenshots/wps_outputs.png)

2)  To configure and run the WRF: there are two programs you will need to run:

-   Real

-   WRF

GIS4WRF already pre-populates most of the namelist used by Real and WRF (`namelist.input`) for you, however it will not select physics and dynamics options for you by design, as a result you need to set the correct physics and dynamics options for your particular experiment. You can click on `Open configuration`  and replace all values in the configuration with your own `namelist.input`.

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-07%2020-49-01.png) 

**Time Control**  

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2007-59-35.png)

**Domains**

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2007-59-50.png) \|

**Physics and Dynamics**

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2008-00-27.png)

Now you are good to go, run `Real` and `WRF` .

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2008-16-34.png) 

First click on `Run Real` and `Run WRF`. The Run program creates the initial condition for the both domains and boundary condition data for the outer domain. Both program should complete without errors. To run this case it takes 708 seconds (11.8 min) in my laptop it may differ on other machines.

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2008-23-13.png)

**View results**

After the simulation is complete, click on `Visualize Output` to select the the WRF output files `wrfout_d01_2015-07-08_12_00_00` and click `Open`.

|                                   Visualize Open                                   |                                Open WRF NetCDF File                                |
|:----------------------------------:|:----------------------------------:|
| ![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2011-52-54.png) | ![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2011-54-26.png) |

WRF NetCDF datasets can also be opened under `QGIS`➡️ `Layers `&rarr
`Add Layer` &rarr `Add WRF NetCDF Layer`. Variables included in WRF NetCDF datasets are shown as a list in the *View* tab. You can view the simulation output as follow:

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2011-49-34.png)

The time slider at the end of the list of variables provides a fast way to slice through different time stamps. For variables that include vertical levels, the vertical level drop down menu will become selectable.

![](/home/yoni/Pictures/Screenshots/Screenshot%20from%202023-01-08%2012-12-34.png) 


**You have successfully run the WPS and WRF programs on your personal machine using the QGIS-GISWRF plugin.**

### Reference:

Meyer, D., & Riechert, M. (2019). Open source QGIS toolkit for the Advanced Research WRF modelling system. Environmental Modelling & Software, 112, 166--178. <https://doi.org/10.1016/j.envsoft.2018.10.018>

Meyer, D., & Riechert, M. (2018). The GIS4WRF Plugin. Zenodo. <https://doi.org/10.5281/zenodo.1288569>

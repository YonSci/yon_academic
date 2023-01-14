---
title: "High-Resolution Digital Elevation Model Data for WRF-Hydro Model"
header-img: "https://yonsci.github.io/yon_academic//images/logo.png"
collection: portfolio
image: https://yonsci.github.io/yon_academic//images/logo.png
---

<img src="{{page.image}}" width="400" height="400" />

---

## Source of High-resolution Digital Elevation Models (DEM)

High-resolution Digital Elevation Models (DEMS) can be obtained from the Earth Engine Data Catalog.The Earth Engine Data Catalog can be found at the following URL <https://developers.google.com/earth-engine/datasets/catalog>

## Datasets

1)  **NASA SRTM Digital Elevation 30m (SRTM V3)**:     

 -   Provider: NASA/USGS/JPL-Caltech: Shuttle Radar Topography Mission
 -   Resolution: approximately 30 meters (1 arcsec )
 -   Source: <https://developers.google.com/earth-engine/datasets/catalog/USGS_SRTMGL1_003>
   
2)  **ALOS DSM Global 30m v3.2 dataset**:

-   Provider: JAXA Earth Observation Research Center
-   Resolution: approximately 30 meters (1 arcsec )
-   Source: <https://developers.google.com/earth-engine/datasets/catalog/JAXA_ALOS_AW3D30_V3_2>
   
3)  **NASADEM: NASA NASADEM Digital Elevation 30m**

-   Provider: NASA / USGS / JPL-Caltech
-   Resolution: approximately 30 meters (1 arcsec )
-   Source: <https://developers.google.com/earth-engine/datasets/catalog/NASA_NASADEM_HGT_001>
   
4)  **Copernicus Global Digital Elevation Models**

-   Provider: European Space Agency, Copernicus Programme
-   Resolution: approximately 30 meters (1 arcsec )
-   Source: <https://portal.opentopography.org/datasetMetadata?otCollectionID=OT.032021.4326.1>


## Tool for downloading high-resolution DEM

### OpenTopography DEM Downloader

The OpenTopography QGIS-plugin facilitates access to high-resolution DEM from `OpenTopography.org`. The available global high-resolution topographic DEMs includes:

-   SRTM 30m
-   ALOS World 3D 30m
-   SRTM GL1 Ellipsoidal 30m
-   Copernicus Global DSM 30m
-   NASADEM Global DEM

The plugin's detailed information can be found at <https://opentopography.org/> or <https://github.com/OpenTopography>

### Install `OpenTopography` plugin

Step-1: Open `QGIS` and go to `Plugins` menu then `Manage and Install Plugins…`

![](https://yonsci.github.io/yon_academic//images/plugin1.png)

Step-2: Click on `All`, in the search bar type `opentopography` plugin, and when the `OpenTopography DEM Downloader` appears click on the `Install Plugin`

![](https://yonsci.github.io/yon_academic//images/plugin2.png)

Step-3: Once the installation is complete, open to the following URL: <https://portal.opentopography.org/newUser> and create account on `OpenTopography` site. You need to conform your registration via your email.

![](https://yonsci.github.io/yon_academic//images/fill_form.png)

Step-4: Get an API Key from OpenTopography.org. Login to your new OpenTopography account via [https://portal.opentopography.org](https://portal.opentopography.org/myopentopo) and click on the `myopentopo` tab.

![](https://yonsci.github.io/yon_academic//images/myopentopo.png)

Go the bottom of the page on `My Account` and click the following link `myOpenTops Authorizations and API Key` <https://portal.opentopography.org/lidarAuthorizationInfo> to create API Key.

![](https://yonsci.github.io/yon_academic//images/account.png)

Click on request `API KEY`

![](https://yonsci.github.io/yon_academic//images/apikey.png)

This will give you the API KEY for downloading DEM data from `OpenTopography` repository. Copy the KEY and save it somewhere for later use. 

![](https://yonsci.github.io/yon_academic//images/key.png)

### Downloading High resolution DEM

Let's use `QGIS` and `OpenTopography` to download high resolution DEM. Click on the `OpenTopography DEM Downloader` button as shown in the following figure.

![](https://yonsci.github.io/yon_academic//images/open.png)

This will bring up the `OpenTopography DEM Downloader` dialog box. In the `Parameters` tab fill the following information:

-   **Select DEM to Download**: Select either `SRTM 30`, `ALOS World 3D 30m`, `SRTM GL1 Ellipsoidal 30m`, `Copernicus Global DSM 30m`, or `NASADEM Global DEM`

-   **Define Extent to Download**: Here you have multiple options to define the extent of the study area. This includes: `Calculate from Layer`, `Use Current Map Canvas Extent`, and `Draw on Map Canvas`

-   **Enter your API Key or use the existing one bellow** Paste the API Key you get from previous step.

-   **Output Raster**: Give output name for the DEM and finllay Click the `Run` button.

![](https://yonsci.github.io/yon_academic//images/download.png)

When the data download is complete, the QGIS Layer will be automatically loaded, as shown below. Here we downloaded a 30 meter SRTM high resolution DEM for Dire Dawa city and its surrounding areas.

![](https://yonsci.github.io/yon_academic//images/data.png)

Finally, we should re-project the DEM in order to use it in the WRF-Hydro model for hydrological applications. Go to `Raster` then `Projection`, and `Warp (Projection...)` . This will open the projection dialog box:

![](https://yonsci.github.io/yon_academic//images/reproject1.png)

-   In the **Input Layer** select the DEM data you downloaded. In this case the `Dem_Dire_Dawa.tif`

-   **Source CRS**: select `EPSG:4326`

-   **Target CRS**: select `EPSG:32637 - WGS/UTM zone 37N`

-   **Re-sampling Method to Use**: `Nearest Neighbour`

-   **ReProjected**: Output name: `projected_dire_dem.tif` and finally click `Run`

![](https://yonsci.github.io/yon_academic//images/reproject2.png)

![](https://yonsci.github.io/yon_academic//images/reproject3.png)

This will load the re-pojected DEM data in the QGIS Layer Panel.

![](https://yonsci.github.io/yon_academic//images/final.png)

This DEM can be used as input for building hydrological routing grids in the WRF-Hydro GIS pre-processing tool.


                                 🥇**Happy WRF-Hydro Modelling.** 🥇




{% include comments.html %}



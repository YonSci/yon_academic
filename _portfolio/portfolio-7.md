---
title: "Python Geopandas package for shapefile management"
collection: portfolio
---
<div align="justify">Geopandas combines the ability of pandas & shapely for manipulating geographic data mainly vector data such as points, polylines, & polygons. Geopandas can read & write vector data in a variety of formats, including the ESRI shapefile format (.shp) & others such as KML, & GeoJSON. </div>

## 🎓 Learning objectives:
 - Installing Geopandas package       
 - Reading & manipulating shapefile geodataframes      
 - Shapefile plotting    
 - Overlaying shapefiles     
 - Shapefile re-projectioning    
 - Shapefile dissolving    
 - Shapefile clipping    
 - Exporting shapefile    
 
# Installing Geopandas package:

<div align="justify"> To install the latest version of GeoPandas, the conda package manager will be utilized. If you haven't already  installed Anaconda on your PC , you can install it by following the previous <a href="https://yonsci.github.io/yon_academic//portfolio/portfolio-2/" target="_top">post</a>.  </div> <br>

To start, add a new environment variable named geopandas_stable. Start ubuntu terminal & enter the following commands:
 
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">conda create --name geopandas_stable</span> 
</code>
</pre>
</div>
</div>
  
Activate the geopandas_stable environment:
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">conda activate geopandas_stable</span> 
</code>
</pre>
</div>
</div> 

 Add & set conda-forge channel:
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">conda config --env --add channels conda-forge</span> 
  <span style="font-size: 200%;color:#0000ff">conda config --env --set channel_priority strict</span> 
</code>
</pre>
</div>
</div> 
 
Install Geopandas package with python-3:
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">conda install python=3 geopandas</span> 
</code>
</pre>
</div>
</div> 

Import the Geopandas library: 
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">import geopandas as gpd</span> 
</code>
</pre>
</div>
</div> 

Check the Geopandas version: 
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">print(gpd.__version__)</span> 
</code>
</pre>
</div>
</div> 

<p>You have successfully installed Geopandas if you receive the version number. Finally, for reading & writing shapefiles, you can use any Python Notebook or IDE, such as Jupyter-Notebook & Spyder.</p>
   
<h1 id="coding-in-python">Reading & manipulating shapefile dataframes</h1>
 
Import the matplotlib library for visualization purposes:
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">import matplotlib.pyplot as plt</span> 
  <span style="font-size: 200%;color:#0000ff">from matplotlib.ticker import ScalarFormatter</span> 
</code>
</pre>
</div>
</div> 
 
All of the shapefiles used in this tutorial have been compressed & saved at this <a href="https://yonsci.github.io/yon_academic//files/Geopandas_data" target="_top">URL</a> 

There are two methods to read the data:
 <ul>
  <li>You can download the compressed shapefiles from the above <a href="https://yonsci.github.io/yon_academic//files/Geopandas_data" target="_top">link</a> to your local directory, extract it, & use this local directory to locate the path of the shapefiles</li>  
     
 <li>Or you can directly read the compressed shapefiles from the above <a href="https://yonsci.github.io/yon_academic//files/Geopandas_data" target="_top">site</a> if you are connected to internate </li>
</ul>
 
Load the shapefile using <b> <em>gpd.read_file</em> </b> function: 
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">zipfile_basins = "https://yonsci.github.io/yon_academic//files/Geopandas_data/ETH_basins.zip"</span> 
  <span style="font-size: 200%;color:#0000ff">ET_basin = gpd.read_file(zipfile_basins)</span> 
</code>
</pre>
</div>
</div>  

Inspect the attribute table of the data by typing:
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">ET_basin</span> 
</code>
</pre>
</div>
</div>  

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" width="10px" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>AREA</th>
      <th>PERIMETER</th>
      <th>RIVERBASIN</th>
      <th>RIVERBAS_1</th>
      <th>BASINNAME</th>
      <th>layer</th>
      <th>Basin_type</th>
      <th>geometry</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2.000141e+11</td>
      <td>2836371.545</td>
      <td>5</td>
      <td>4</td>
      <td>ABBAY</td>
      <td>Abby</td>
      <td>1</td>
      <td>POLYGON ((35.75669 12.67180, 35.75921 12.67317...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1.121677e+11</td>
      <td>2050391.912</td>
      <td>6</td>
      <td>5</td>
      <td>AWASH</td>
      <td>Awash</td>
      <td>1</td>
      <td>POLYGON ((39.52930 11.72403, 39.52891 11.72624...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4.755561e+09</td>
      <td>318650.138</td>
      <td>7</td>
      <td>6</td>
      <td>AYSHA</td>
      <td>Aysha</td>
      <td>1</td>
      <td>POLYGON ((42.30811 10.99144, 42.32126 10.99586...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>7.572123e+10</td>
      <td>2128499.780</td>
      <td>8</td>
      <td>7</td>
      <td>BARO AKOBO</td>
      <td>Baro_akobo</td>
      <td>1</td>
      <td>POLYGON ((34.47938 10.83318, 34.48112 10.83473...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>6.524619e+10</td>
      <td>1228197.473</td>
      <td>4</td>
      <td>3</td>
      <td>DENAKIL</td>
      <td>Denakil</td>
      <td>1</td>
      <td>POLYGON ((39.37495 14.50856, 39.41100 14.52892...</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1.722588e+11</td>
      <td>2006366.812</td>
      <td>13</td>
      <td>12</td>
      <td>GENALE DAWA</td>
      <td>Genale_dawa1</td>
      <td>1</td>
      <td>POLYGON ((41.13743 6.94134, 41.14177 6.93580, ...</td>
    </tr>
    <tr>
      <th>6</th>
      <td>5.868187e+09</td>
      <td>534670.622</td>
      <td>2</td>
      <td>1</td>
      <td>MEREB GASH</td>
      <td>Mereb1</td>
      <td>1</td>
      <td>POLYGON ((37.80309 14.70250, 37.91271 14.88540...</td>
    </tr>
    <tr>
      <th>7</th>
      <td>7.969898e+10</td>
      <td>1613036.102</td>
      <td>9</td>
      <td>8</td>
      <td>OGADEN</td>
      <td>Ogaden</td>
      <td>1</td>
      <td>POLYGON ((43.31527 9.60498, 43.35539 9.58202, ...</td>
    </tr>
    <tr>
      <th>8</th>
      <td>7.871230e+10</td>
      <td>1832234.370</td>
      <td>11</td>
      <td>10</td>
      <td>OMO GIBE</td>
      <td>Omo_gibe</td>
      <td>1</td>
      <td>POLYGON ((38.02335 8.93136, 38.03574 8.91034, ...</td>
    </tr>
    <tr>
      <th>9</th>
      <td>5.298484e+10</td>
      <td>1381422.016</td>
      <td>12</td>
      <td>11</td>
      <td>RIFT VALLY</td>
      <td>Rift_valley</td>
      <td>1</td>
      <td>POLYGON ((38.40912 8.39296, 38.41411 8.39297, ...</td>
    </tr>
    <tr>
      <th>10</th>
      <td>8.367317e+10</td>
      <td>1468016.695</td>
      <td>3</td>
      <td>2</td>
      <td>TEKEZE</td>
      <td>Tekeze</td>
      <td>1</td>
      <td>POLYGON ((39.40391 14.25409, 39.45916 14.23977...</td>
    </tr>
    <tr>
      <th>11</th>
      <td>2.017996e+11</td>
      <td>2336905.978</td>
      <td>10</td>
      <td>9</td>
      <td>WABI SHEBELE</td>
      <td>Wabi_shebelle</td>
      <td>1</td>
      <td>POLYGON ((42.69533 9.58651, 42.69804 9.58040, ...</td>
    </tr>
  </tbody>
</table>
</div> 
  
Instead of displaying the entire dataframe, I recommend displaying only the first & last 5 rows of the dataframe using the <b> <em>.head()</em> </b> & <b> <em>.tail()</em> </b> built-in functions. To display the first 5 rows of the dataframe, type: 
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">ET_basin.head()</span> 
</code>
</pre>
</div>
</div> 
 
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>AREA</th>
      <th>PERIMETER</th>
      <th>RIVERBASIN</th>
      <th>RIVERBAS_1</th>
      <th>BASINNAME</th>
      <th>layer</th>
      <th>Basin_type</th>
      <th>geometry</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2.000141e+11</td>
      <td>2836371.545</td>
      <td>5</td>
      <td>4</td>
      <td>ABBAY</td>
      <td>Abby</td>
      <td>1</td>
      <td>POLYGON ((35.75669 12.67180, 35.75921 12.67317...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1.121677e+11</td>
      <td>2050391.912</td>
      <td>6</td>
      <td>5</td>
      <td>AWASH</td>
      <td>Awash</td>
      <td>1</td>
      <td>POLYGON ((39.52930 11.72403, 39.52891 11.72624...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4.755561e+09</td>
      <td>318650.138</td>
      <td>7</td>
      <td>6</td>
      <td>AYSHA</td>
      <td>Aysha</td>
      <td>1</td>
      <td>POLYGON ((42.30811 10.99144, 42.32126 10.99586...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>7.572123e+10</td>
      <td>2128499.780</td>
      <td>8</td>
      <td>7</td>
      <td>BARO AKOBO</td>
      <td>Baro_akobo</td>
      <td>1</td>
      <td>POLYGON ((34.47938 10.83318, 34.48112 10.83473...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>6.524619e+10</td>
      <td>1228197.473</td>
      <td>4</td>
      <td>3</td>
      <td>DENAKIL</td>
      <td>Denakil</td>
      <td>1</td>
      <td>POLYGON ((39.37495 14.50856, 39.41100 14.52892...</td>
    </tr>
  </tbody>
</table>
</div>

 Similarly, to display the last 5 rows of the dataframe, type:
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">ET_basin.tail()</span> 
</code>
</pre>
</div>
</div> 

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>AREA</th>
      <th>PERIMETER</th>
      <th>RIVERBASIN</th>
      <th>RIVERBAS_1</th>
      <th>BASINNAME</th>
      <th>layer</th>
      <th>Basin_type</th>
      <th>geometry</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>7</th>
      <td>7.969898e+10</td>
      <td>1613036.102</td>
      <td>9</td>
      <td>8</td>
      <td>OGADEN</td>
      <td>Ogaden</td>
      <td>1</td>
      <td>POLYGON ((43.31527 9.60498, 43.35539 9.58202, ...</td>
    </tr>
    <tr>
      <th>8</th>
      <td>7.871230e+10</td>
      <td>1832234.370</td>
      <td>11</td>
      <td>10</td>
      <td>OMO GIBE</td>
      <td>Omo_gibe</td>
      <td>1</td>
      <td>POLYGON ((38.02335 8.93136, 38.03574 8.91034, ...</td>
    </tr>
    <tr>
      <th>9</th>
      <td>5.298484e+10</td>
      <td>1381422.016</td>
      <td>12</td>
      <td>11</td>
      <td>RIFT VALLY</td>
      <td>Rift_valley</td>
      <td>1</td>
      <td>POLYGON ((38.40912 8.39296, 38.41411 8.39297, ...</td>
    </tr>
    <tr>
      <th>10</th>
      <td>8.367317e+10</td>
      <td>1468016.695</td>
      <td>3</td>
      <td>2</td>
      <td>TEKEZE</td>
      <td>Tekeze</td>
      <td>1</td>
      <td>POLYGON ((39.40391 14.25409, 39.45916 14.23977...</td>
    </tr>
    <tr>
      <th>11</th>
      <td>2.017996e+11</td>
      <td>2336905.978</td>
      <td>10</td>
      <td>9</td>
      <td>WABI SHEBELE</td>
      <td>Wabi_shebelle</td>
      <td>1</td>
      <td>POLYGON ((42.69533 9.58651, 42.69804 9.58040, ...</td>
    </tr>
  </tbody>
</table>
</div>

Alternatively, you can view a specific section of the dataframe by defining the row numbers, but keep in mind that Python counts starting from zero. For example, to display only the 3rd & 4th rows, you can type:
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">ET_basin[3:5]</span> 
</code>
</pre>
</div>
</div> 
 
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>AREA</th>
      <th>PERIMETER</th>
      <th>RIVERBASIN</th>
      <th>RIVERBAS_1</th>
      <th>BASINNAME</th>
      <th>layer</th>
      <th>Basin_type</th>
      <th>geometry</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3</th>
      <td>7.572123e+10</td>
      <td>2128499.780</td>
      <td>8</td>
      <td>7</td>
      <td>BARO AKOBO</td>
      <td>Baro_akobo</td>
      <td>1</td>
      <td>POLYGON ((34.47938 10.83318, 34.48112 10.83473...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>6.524619e+10</td>
      <td>1228197.473</td>
      <td>4</td>
      <td>3</td>
      <td>DENAKIL</td>
      <td>Denakil</td>
      <td>1</td>
      <td>POLYGON ((39.37495 14.50856, 39.41100 14.52892...</td>
    </tr>
  </tbody>
</table>
</div>

To find out the size of the dataframe, type:
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">ET_basin.shape</span> 
</code>
</pre>
</div>
</div>  
`Output: (12, 8)`  
As can be seen, the dataframe has 12 rows and 8 columns

To obtain the row numbers or length of the dataframe, type:
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">len(ET_basin)</span> 
</code>
</pre>
</div>
</div>  
`Output: 12`  

To print the column names, type: 
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">ET_basin.columns</span> 
</code>
</pre>
</div>
</div>  
`Output: Index(['AREA', 'PERIMETER', 'RIVERBASIN', 'RIVERBAS_1', 'BASINNAME', 'layer', 'path', 'Basin_type', 'geometry'],
          dtype='object')`

To list the column's contents:
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">ET_basin.BASINNAME.values</span> 
</code>
</pre>
</div>
</div>
`Output: array(['ABBAY', 'AWASH', 'AYSHA', 'BARO AKOBO', 'DENAKIL', 'GENALE DAWA',
           'MEREB GASH', 'OGADEN', 'OMO GIBE', 'RIFT VALLY', 'TEKEZE',
           'WABI SHEBELE'], dtype=object)`

The `geometry` column is the most essential of the columns  & it contains the `x`-`y` coordinate values of the vector data. For instance, you can look at the values using `.geometry` function:
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">print(ET_basin.geometry)</span> 
</code>
</pre>
</div>
</div>
`Output: 
    0     POLYGON ((35.75669 12.67180, 35.75921 12.67317...
    1     POLYGON ((39.52930 11.72403, 39.52891 11.72624...
    2     POLYGON ((42.30811 10.99144, 42.32126 10.99586...
    3     POLYGON ((34.47938 10.83318, 34.48112 10.83473...
    4     POLYGON ((39.37495 14.50856, 39.41100 14.52892...
    5     POLYGON ((41.13743 6.94134, 41.14177 6.93580, ...
    6     POLYGON ((37.80309 14.70250, 37.91271 14.88540...
    7     POLYGON ((43.31527 9.60498, 43.35539 9.58202, ...
    8     POLYGON ((38.02335 8.93136, 38.03574 8.91034, ...
    9     POLYGON ((38.40912 8.39296, 38.41411 8.39297, ...
    10    POLYGON ((39.40391 14.25409, 39.45916 14.23977...
    11    POLYGON ((42.69533 9.58651, 42.69804 9.58040, ...
    Name: geometry, dtype: geometry`


To view the geometry type of each vector type: 
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">ET_basin.geom_type.head()</span> 
</code>
</pre>
</div>
</div>
`Output: 
    0    Polygon
    1    Polygon
    2    Polygon
    3    Polygon
    4    Polygon
    dtype: object`

You can use the following function to extract x-y coordinate values of a given polygon, In this case, the first polygon:
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">def coord_lister(geom):</span> 
  <span style="font-size: 200%;color:#0000ff">coords = list(geom.exterior.coords)</span> 
  <span style="font-size: 200%;color:#0000ff">return(coords)</span> 
  <span style="font-size: 200%;color:#0000ff">coordinates = ET_basin.geometry.apply(coord_lister)</span>
  <span style="font-size: 200%;color:#0000ff">Abbay_coord = coordinates[0]</span>
</code>
</pre>
</div>
</div>

Let's look at the first ten x-y coordinate values:
<div class="language-python highlighter-rouge">
 <div class="highlight">
  <pre class="highlight">
  <code>
  <span style="font-size: 200%;color:#0000ff">Abbay_coord[:10]</span> 
</code>
</pre>
</div>
</div>
`Output:
    [(35.756690888078126, 12.671797097608444),
     (35.75921179031758, 12.673172165175462),
     (35.76174531616754, 12.674460456844615),
     (35.7643064966319, 12.675563955460834),
     (35.76690347742137, 12.676383429901467),
     (35.76954908459146, 12.676824219629998),
     (35.77224026615727, 12.676922403038853),
     (35.774962412059814, 12.676764711775403),
     (35.77771230490099, 12.676412056011529),
     (35.780480076318945, 12.675917364792335)]`

You may get a quick overview of the shape file by using the geometry values. For instance, to view the first geometry file, you can use the code below:


```python
ET_basin.at[0,'geometry']
``` 
![svg](output_39_0.svg)
    
```

### To know how the data is represented or stored, type


```python
type(ET_basin)
```
    geopandas.geodataframe.GeoDataFrame
#### In this example, the data is represented as `GeoDataFrame`
### To view the spatial extent or coverage of the shapefile use the `total_bounds` function 


```python
ET_basin.total_bounds
```

    array([33.00541327,  3.40510906, 47.99567693, 14.88539753])

#### The shapefile ranges from `33.00541327` to `47.99567693` longitudes and `3.40510906` to `14.88539753` latitudes

### Use the `geom type` function to get information about the geometry type (polygon, line, or point) of each data recorded in the dataframe


```python
ET_basin.geom_type
```




    0     Polygon
    1     Polygon
    2     Polygon
    3     Polygon
    4     Polygon
    5     Polygon
    6     Polygon
    7     Polygon
    8     Polygon
    9     Polygon
    10    Polygon
    11    Polygon
    dtype: object



#### In this case, all 12 objects are polygons

# Shapefile plotting

### Let's now make a simple plot of the shapefile using `plot()` function 


```python
ET_basin.plot()
```




    <AxesSubplot:>




    
![png](output_55_1.png)
    


### Let's colorize the map with the `cmap` function


```python
ET_basin.plot(cmap ='jet')
```




    <AxesSubplot:>




    
![png](output_57_1.png)
    


### In place of `jet`, you can use one of the Matplotlib color options given below, or you can visit the following link https://matplotlib.org/stable/tutorials/colors/colormaps.html to learn more about the colormaps

'Accent', 'Accent_r', 'Blues', 'Blues_r', 'BrBG', 'BrBG_r', 'BuGn', 'BuGn_r', 'BuPu', 'BuPu_r', 'CMRmap', 'CMRmap_r', 'Dark2', 'Dark2_r', 'GnBu', 'GnBu_r', 'Greens', 'Greens_r', 'Greys', 'Greys_r', 'OrRd', 'OrRd_r', 'Oranges', 'Oranges_r', 'PRGn', 'PRGn_r', 'Paired', 'Paired_r', 'Pastel1', 'Pastel1_r', 'Pastel2', 'Pastel2_r', 'PiYG', 'PiYG_r', 'PuBu', 'PuBuGn', 'PuBuGn_r', 'PuBu_r', 'PuOr', 'PuOr_r', 'PuRd', 'PuRd_r', 'Purples', 'Purples_r', 'RdBu', 'RdBu_r', 'RdGy', 'RdGy_r', 'RdPu', 'RdPu_r', 'RdYlBu', 'RdYlBu_r', 'RdYlGn', 'RdYlGn_r', 'Reds', 'Reds_r', 'Set1', 'Set1_r', 'Set2', 'Set2_r', 'Set3', 'Set3_r', 'Spectral', 'Spectral_r', 'Wistia', 'Wistia_r', 'YlGn', 'YlGnBu', 'YlGnBu_r', 'YlGn_r', 'YlOrBr', 'YlOrBr_r', 'YlOrRd', 'YlOrRd_r', 'afmhot', 'afmhot_r', 'autumn', 'autumn_r', 'binary', 'binary_r', 'bone', 'bone_r', 'brg', 'brg_r', 'bwr', 'bwr_r', 'cividis', 'cividis_r', 'cool', 'cool_r', 'coolwarm', 'coolwarm_r', 'copper', 'copper_r', 'cubehelix', 'cubehelix_r', 'flag', 'flag_r', 'gist_earth', 'gist_earth_r', 'gist_gray', 'gist_gray_r', 'gist_heat', 'gist_heat_r', 'gist_ncar', 'gist_ncar_r', 'gist_rainbow', 'gist_rainbow_r', 'gist_stern', 'gist_stern_r', 'gist_yarg', 'gist_yarg_r', 'gnuplot', 'gnuplot2', 'gnuplot2_r', 'gnuplot_r', 'gray', 'gray_r', 'hot', 'hot_r', 'hsv', 'hsv_r', 'inferno', 'inferno_r', 'jet', 'jet_r', 'magma', 'magma_r', 'nipy_spectral', 'nipy_spectral_r', 'ocean', 'ocean_r', 'pink', 'pink_r', 'plasma', 'plasma_r', 'prism', 'prism_r', 'rainbow', 'rainbow_r', 'seismic', 'seismic_r', 'spring', 'spring_r', 'summer', 'summer_r', 'tab10', 'tab10_r', 'tab20', 'tab20_r', 'tab20b', 'tab20b_r', 'tab20c', 'tab20c_r', 'terrain', 'terrain_r', 'turbo', 'turbo_r', 'twilight', 'twilight_r', 'twilight_shifted', 'twilight_shifted_r', 'viridis', 'viridis_r', 'winter', 'winter_r'

### You can colorize the map based on a specific column, in this case let's use the `BASINNAME` column


```python
ET_basin.plot(cmap ='tab20c', column='BASINNAME')
```




    <AxesSubplot:>




    
![png](output_61_1.png)
    


### You can also use the `figsize` option to change the plot size


```python
ET_basin.plot(cmap ='tab20c', column='BASINNAME', figsize=(6,6))
```




    <AxesSubplot:>




    
![png](output_63_1.png)
    


### You can apply an edge color to each polygon in the shapefile using `edgecolor` function 


```python
ET_basin.plot(cmap ='tab20c', column='BASINNAME', figsize=(6,6), edgecolor='black')
```




    <AxesSubplot:>




    
![png](output_65_1.png)
    


### You may also put a legend in the plot:


```python
ET_basin.plot(cmap ='tab20c', column='BASINNAME', figsize=(9,7), edgecolor='black', legend=True)
```




    <AxesSubplot:>




    
![png](output_67_1.png)
    


### You can also change the legend's position:


```python
fig, ax = plt.subplots(figsize=(9,7))
ET_basin.plot(alpha=1.0, cmap ='tab20c', column='BASINNAME', edgecolor='black', ax=ax, legend=True )
ax.set_title('Major river basins of Ethiopia', fontsize=25)

ax.set_axisbelow(True)
ax.yaxis.grid(color='gray', linestyle='dashdot')
ax.xaxis.grid(color='gray', linestyle='dashdot')

# Here, instead of 'dashdot' you can use 'dotted', 'dashed', 'solid'

ax.set_xlabel("Longitude (Degrees)", fontsize=12)
ax.set_ylabel("Latitude (Degrees)", fontsize=12)

leg = ax.get_legend()
leg.set_bbox_to_anchor((1.25,1.01))

plt.show()
```


    
![png](output_69_0.png)
    


### However, using the `matplotlib` functions is a more convenient way to plot


```python
fig, ax = plt.subplots(figsize=(9,7))
ET_basin.plot(alpha=1.0, cmap ='tab20c', column='BASINNAME', edgecolor='black', legend=True, ax=ax )
ax.set_title('Major river basins of Ethiopia', fontsize=25)

ax.set_xlabel("Longitude (Degrees)", fontsize=12)
ax.set_ylabel("Latitude (Degrees)", fontsize=12)

plt.show()
```


    
![png](output_71_0.png)
    


### You can use the script underneath to add grids to the plot


```python
fig, ax = plt.subplots(figsize=(9,7))
ET_basin.plot(alpha=1.0, cmap ='tab20c', column='BASINNAME', edgecolor='black', legend=True, ax=ax )
ax.set_title('Major river basins of Ethiopia', fontsize=25)

ax.set_axisbelow(True)
ax.yaxis.grid(color='gray', linestyle='dashdot')
ax.xaxis.grid(color='gray', linestyle='dashdot')

# Here, instead of 'dashdot' you can use 'dotted', 'dashed', 'solid'

ax.set_xlabel("Longitude (Degrees)", fontsize=12)
ax.set_ylabel("Latitude (Degrees)", fontsize=12)

plt.show()
```


    
![png](output_73_0.png)
    


### Plots can be saved as image files using the `plt. savefig()` function:


```python
fig, ax = plt.subplots(figsize=(9,7))
ET_basin.plot(alpha=1.0, cmap ='tab20c', column='BASINNAME', edgecolor='black', legend=True, ax=ax )
ax.set_title('Major river basins of Ethiopia', fontsize=25)

ax.set_axisbelow(True)
ax.yaxis.grid(color='gray', linestyle='dashdot')
ax.xaxis.grid(color='gray', linestyle='dashdot')

# Here, instead of 'dashdot' you can use 'dotted', 'dashed', 'solid'

ax.set_xlabel("Longitude (Degrees)", fontsize=12)
ax.set_ylabel("Latitude (Degrees)", fontsize=12)

plt.savefig('basins.jpeg', transparent=True,  bbox_inches='tight', dpi=800)

plt.show()
```


    
![png](output_75_0.png)
    


### You can remove the grids and boundary by using the code below


```python
fig, ax = plt.subplots(figsize=(9,7))
ET_basin.plot(alpha=1.0, cmap ='tab20c', column='BASINNAME', edgecolor='black', legend=True, ax=ax )
ax.set_title('Major Basins of Ethiopia', fontsize=25)
ax.set_axis_off()
plt.show()
```


    
![png](output_77_0.png)
    


### Making subplots


```python
fig, ((ax1, ax2, ax3, ax4), (ax5, ax6, ax7, ax8), (ax9, ax10, ax11, ax12)) = plt.subplots(3, 4, figsize=(15,15))
fig.suptitle("Major Basin's in Ethiopia", fontsize=24)

ET_basin.loc[ET_basin.BASINNAME == "ABBAY"].plot(ax=ax1, facecolor='Blue',  edgecolor='black')
ax1.set_title("ABBAY")
ET_basin.loc[ET_basin.BASINNAME == "AWASH"].plot(ax=ax2, facecolor='Blue',  edgecolor='black')
ax2.set_title("AWASH")
ET_basin.loc[ET_basin.BASINNAME == "AYSHA"].plot(ax=ax3, facecolor='Blue',  edgecolor='black')
ax3.set_title("AYSHA")
ET_basin.loc[ET_basin.BASINNAME == "BARO AKOBO"].plot(ax=ax4, facecolor='Blue',  edgecolor='black')
ax4.set_title("BARO AKOBO")
ET_basin.loc[ET_basin.BASINNAME == "DENAKIL"].plot(ax=ax5, facecolor='Blue',  edgecolor='black')
ax5.set_title("DENAKIL")
ET_basin.loc[ET_basin.BASINNAME == "GENALE DAWA"].plot(ax=ax6, facecolor='Blue',  edgecolor='black')
ax6.set_title("GENALE DAWA")
ET_basin.loc[ET_basin.BASINNAME == "MEREB GASH"].plot(ax=ax7, facecolor='Blue',  edgecolor='black')
ax7.set_title("MEREB GASH")
ET_basin.loc[ET_basin.BASINNAME == "OGADEN"].plot(ax=ax8, facecolor='Blue',  edgecolor='black')
ax8.set_title("OGADEN")
ET_basin.loc[ET_basin.BASINNAME == "OMO GIBE"].plot(ax=ax9, facecolor='Blue',  edgecolor='black')
ax9.set_title("OMO GIBE")
ET_basin.loc[ET_basin.BASINNAME == "RIFT VALLY"].plot(ax=ax10, facecolor='Blue',  edgecolor='black')
ax10.set_title("RIFT VALLY")
ET_basin.loc[ET_basin.BASINNAME == "TEKEZE"].plot(ax=ax11, facecolor='Blue',  edgecolor='black')
ax11.set_title("TEKEZE")
ET_basin.loc[ET_basin.BASINNAME == "WABI SHEBELE"].plot(ax=ax12, facecolor='Blue',  edgecolor='black')
ax12.set_title("WABI SHEBELE")

plt.show()
```


    
![png](output_79_0.png)
    


# Overlaying shapefiles
### As an example, consider overlaying the `ET_basin` over the `African continent` shapefile  
### Let's begin by importing the African continent shapefile


```python
zipfile_Africa = "https://yonsci.github.io/yon_academic//files/Geopandas_data/Africa.zip"
AFRICA = gpd.read_file(zipfile_Africa)
```

### It is critical to remember that the coordinate systems of the two shapefiles must be identical
### The `.crs` command can be used to verify the coordinate system of  the two shapefiles


```python
AFRICA.crs
```




    <Geographic 2D CRS: EPSG:4326>
    Name: WGS 84
    Axis Info [ellipsoidal]:
    - Lat[north]: Geodetic latitude (degree)
    - Lon[east]: Geodetic longitude (degree)
    Area of Use:
    - name: World
    - bounds: (-180.0, -90.0, 180.0, 90.0)
    Datum: World Geodetic System 1984
    - Ellipsoid: WGS 84
    - Prime Meridian: Greenwich




```python
ET_basin.crs
```




    <Geographic 2D CRS: EPSG:4326>
    Name: WGS 84
    Axis Info [ellipsoidal]:
    - Lat[north]: Geodetic latitude (degree)
    - Lon[east]: Geodetic longitude (degree)
    Area of Use:
    - name: World
    - bounds: (-180.0, -90.0, 180.0, 90.0)
    Datum: World Geodetic System 1984
    - Ellipsoid: WGS 84
    - Prime Meridian: Greenwich



### You can see that they both use the `WGS-84` geographic coordinate system `(EPSG:4326)`

### You can now plot the overlaid map


```python
fig, ax = plt.subplots(figsize=(6,6))
AFRICA.plot(ax=ax, color ='None', edgecolor='black',)
ET_basin.plot(ax=ax, cmap ='tab20c', column='BASINNAME')
ax.grid(True)
ax.set_title('Ethiopian basins overlaid on African continent', fontsize=15)
ax.set(xlabel="Longitude (Degrees)", ylabel="Latitude (Degrees)")
plt.show()
```


    
![png](output_87_0.png)
    


# Shapefile re-projectioning

### To know the existing coordinate system of the shapefile use the `.crs` function 


```python
ET_basin.crs
```




    <Geographic 2D CRS: EPSG:4326>
    Name: WGS 84
    Axis Info [ellipsoidal]:
    - Lat[north]: Geodetic latitude (degree)
    - Lon[east]: Geodetic longitude (degree)
    Area of Use:
    - name: World
    - bounds: (-180.0, -90.0, 180.0, 90.0)
    Datum: World Geodetic System 1984
    - Ellipsoid: WGS 84
    - Prime Meridian: Greenwich



### Some examples of widely used spatial reference systems:

Reference systems name                    | EPSG code
------------------------------------------|-------------
WGS-84(Geographic)                        | EPSG:4326
WGS_UTM_37N (projected)                   | EPSG:32637
Spherical Mercator (projected)            | EPSG:3857
World Equidistant cylindrical/spherical   | EPSG:4088
World Equidistant cylindrical             | EPSG:4087 
WGS84/ World Mercator                     | EPSG:3395
WGS84/ World Pseudo Mercator              | EPSG:3857
World Robinson                            | EPSG:54030

The following [website](https://spatialreference.org/) gives you access to several reference coordinate systems (https://spatialreference.org/).

### Let's re-project the `ET_basin` shapefile from `WGS-84` geographic coordinate system to the Universal Transverse Mercator `(UTM)` projected coordinate system


```python
# Re-projecting from EPSG:4326 to EPSG:32637 
ET_basin_utm = ET_basin.to_crs({'init': 'epsg:32637'})

# or simply type:
# ET_basin_utm = ET_basin.to_crs(32637)
```

    /home/yoni/anaconda3/lib/python3.8/site-packages/pyproj/crs/crs.py:53: FutureWarning: '+init=<authority>:<code>' syntax is deprecated. '<authority>:<code>' is the preferred initialization method. When making the change, be mindful of axis order changes: https://pyproj4.github.io/pyproj/stable/gotchas.html#axis-order-changes-in-proj-6
      return _prepare_from_string(" ".join(pjargs))


### Let's review the coordinate system again


```python
ET_basin_utm.crs
```




    <Projected CRS: EPSG:32637>
    Name: WGS 84 / UTM zone 37N
    Axis Info [cartesian]:
    - E[east]: Easting (metre)
    - N[north]: Northing (metre)
    Area of Use:
    - name: World - N hemisphere - 36°E to 42°E - by country
    - bounds: (36.0, 0.0, 42.0, 84.0)
    Coordinate Operation:
    - name: UTM zone 37N
    - method: Transverse Mercator
    Datum: World Geodetic System 1984
    - Ellipsoid: WGS 84
    - Prime Meridian: Greenwich



### You can also confirm by inspecting the shapefile boundaries


```python
ET_basin_utm.total_bounds
```




    array([-161882.56221284,  376388.12499996, 1495282.8685069 ,
           1645935.62500012])



### Let's have a look at the new map under the projected UTM reference system


```python
fig, ax = plt.subplots(figsize=(8, 8))
ET_basin_utm.plot(cmap='flag_r', ax=ax, alpha=.5)
ax.set_title("Ethiopian basin map: UTM zone-37N projected reference system", fontsize=14)
ax.set_xlabel("X Coordinates (meters)", fontsize=12)
ax.set_ylabel("Y Coordinates (meters)", fontsize=12)

from matplotlib.ticker import ScalarFormatter

for axis in [ax.xaxis, ax.yaxis]:
    formatter = ScalarFormatter()
    formatter.set_scientific(False)
    axis.set_major_formatter(formatter)
```


    
![png](output_100_0.png)
    


### Overriding existing CRS, you can use `.set_crs` function 


```python
# ET_basin = ET_basin.set_crs(4088, allow_override=True)
```

# Shapefile Dissolving
### Dissolving polygon (removes the interior geometry)


```python
# First, pick which columns you want to maintain; in this example, the `Basin_type` will be used as a criteria
ET_basin_selected = ET_basin[['Basin_type', 'geometry']]
```

### Use the `.dissolve()` function, which is based on a unique attribute value


```python
ET_dissolved = ET_basin_selected.dissolve(by='Basin_type')
```

### View the resulting geodataframe


```python
ET_dissolved
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>geometry</th>
    </tr>
    <tr>
      <th>Basin_type</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>POLYGON ((43.28204 4.71709, 43.25243 4.70156, ...</td>
    </tr>
  </tbody>
</table>
</div>



### As you can see, the dataframe contains the `geometry` & `Basin_type` fields, & the dissolved polygon can be seen using the simple plot


```python
ET_dissolved.plot()
```




    <AxesSubplot:>




    
![png](output_110_1.png)
    


# Shapefile clipping

### You may easily clip each polygon by selecting one of the column names. In this situation, let's  use the `BASINNAME` field from `ET_basin` geodataframe to select the desired basin name `(ABBAY)`


```python
Abbay_basin = ET_basin.loc[ET_basin.BASINNAME == "ABBAY"]
```

### Let's plot the clipped Abbay basin


```python
fig, ax = plt.subplots(figsize=(6,6))
Abbay_basin.plot(alpha=1.0, cmap ='tab20c', column='BASINNAME', edgecolor='black', legend=True, ax=ax )
ax.set_title('Map of ABBAY basin', fontsize=25)
ax.grid(True)
plt.show()
```


    
![png](output_115_0.png)
    


### You can also use the `intersection` tool to clip data to a specified region, for instance, let's load the major world river shapefile, and clip it to the Ethiopian region

### Load the major world rivers:


```python
zip_World_river = "https://yonsci.github.io/yon_academic//files/Geopandas_data/world_rivers.zip"
World_river = gpd.read_file(zip_World_river)
```

### Let's have a look at the loaded map


```python
World_river.plot(figsize=(8,8))
```




    <AxesSubplot:>




    
![png](output_120_1.png)
    


### Let's use the `ET_dissolved` shapefile to clip the world rivers to the area of interest:


```python
Intersecting_rivers = gpd.overlay(ET_dissolved, World_river, how ='intersection', keep_geom_type=False)
```

### Let's plot the clip data


```python
fig, ax = plt.subplots(figsize=(8, 8))
ET_dissolved.plot(alpha=1, facecolor="none", edgecolor="black", zorder=10, ax=ax)
Intersecting_rivers.plot(ax=ax, legend=True)

ax.yaxis.grid(color='gray', linestyle='dashdot')
ax.xaxis.grid(color='gray', linestyle='dashdot')

ax.set_xlabel("Longitude (Degrees)", fontsize=12)
ax.set_ylabel("Latitude (Degrees)", fontsize=12)

ax.set_title('Major rivers of Ethiopia', fontsize=25)
plt.show()
```


    
![png](output_124_0.png)
    


# Exporting shapefile 


```python
# To export as a shapefile
ET_basin_utm.to_file("Basins_ethio.shp")
```


```python
# To export as a GeoJSON file
ET_basin_utm.to_file("ET_basin_utm_js.json", driver="GeoJSON")    
```
{% include comments.html %}  

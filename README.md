 # Quantitative Assessment of the Risk of Invasion by <i>Alternanthera philoxeroides</i> in India using Species Distribution Modelling 

<p style='text-align: justify;'><b>Background of the species</b>: <i>Alternanthera philoxeroides</i>, commonly known as Alligatorweed, from Kingdom plantae, familiy amaranthaceae and genus Alternanthera. This plant which is considered to be one of the top 10 worst weeds in the world, is also a cause of serious concern in India since it is extremely difficult to eradicate. <i>Alternanthera philoxeroides</i> has already demonstrated an ability to establish and spread elsewhere in the world. The species distribution models (SDM) is used to predict the distribution of species in the geographic space based on the mathematical representation of their known distribution in the environmental space. Within a multidimensional space defined by a set of climatic and soil variables, the boundaries of the species records determine its climatic niche or 'climatic envelope'. SDMs operate by generating a statistical relationship between these known occurrences of a species and environmental covariates. The statistical relationship of the climatic envelope thus developed can be spatially and temporarily extrapolated to generate the potential distribution of the species under novel climatic conditions. Statistical and machine learning techniques are being increasingly used to identify the environmental factors and the resultant environmental covariates are used to build a model distribution on the climatic conditions and soil variations in which species would survive, which are further used to identify the locations of species occurrence. Suitability of climatic conditions between the native and invaded region is known to be a crucial factor for establishment, growth, and reproduction of an invasive species. Identification of the climatically suitable region in the invasive habitat, therefore, can help to identify habitats prone to invasion and guide management decisions. In the similar approaches, SDMs are frequently used to identify areas in a novel habitat that are climatically suitable for an invasive species.</p>

## Coordinate Reference system

<p style='text-align: justify;'>A coordinate system is a set of mathematical rules for specifying how coordinates are to be assigned to points, such as : cylindrical, Cartesian, ellipsoidal, etc. System contains X and Y value located in 2 or n dimensional space. Earth is in 3-D space with round shape. Coordinate system is used to get the locations of objects on earth that adapts to the shape of earth. When we see globe map in 3-D, tranformed into paper map in textbook or map in computer i.e in 2-D. The CRS components define how points on flat surface map to the points on globe surface. We working on located data on world map.</p>

###  The Components of a CRS

<b>Coordinate System</b>: The intersection point of the value of x axis (longitude) and y axis (latitude) where data is located on flat map and where data is located in space 3-D.

<b>Units</b>: Units defined on x, y and z axis.

<b>Datum</b>: Set of reference points used to locate places on the Earth.

<b>Projection</b>: Mathematical calculations are used to convert the coordinate system which is used to map objects on the curved surface of earth to a flat surface.

### Map Coordinate systems

Geodesy is the accurately measuring Earth science and understanding geometric shape of Earth, orientation in space, and gravitational field. Geodesists use coordinate reference systems such as WGS84, NAD27 and NAD83. We are going to work on WGS84(EPSG:4326). As shown in the image, X axis of longitude have X-coordinates between -180 and +180 degrees and Y axis of latitudes have Y-coordinates between -90 and +90 degrees. (X, Y) are Coordinates in a two-dimensional space referenced to a horizontal datum and (X, Y and Z) points not only has position, but also has height referenced to a vertical datum.

<img src="world map.jpeg"> <img src="india map.jpeg">

The visualisation of map is done through code, you will see in next page.

## Required Packages

### Packages for Data Analysis

<b>NumPy</b>: The library add support for large, multi-dimensional arrays and matrices, along with a large collection of high-level mathematical functions to operate on these arrays.

<b>Pandas</b>:It is used for data manipulation and analysis. It offers data structures and operations for manipulating numerical tables.

<b>Imblearn</b>: It provides number of re-sampling techniques commonly used in datasets showing strong between-class imbalance.

### Packages for visualization on map

<b>GeoPandas</b>: GeoPandas is an open source project for working with geospatial data in python easier. It allow spatial operations on georeference data.

<b>Shapely</b>: Shapely is for manipulation and analysis of planar geometric objects. It does not read or write data files, but it can serialize and deserialize using several well known formats and protocols.

<b>georasters</b>: The raster package has functions for creating, reading, manipulating, and writing raster data. The package provides, among other things, general raster data manipulation functions that can easily be used to develop more specific functions.

<b>osmnx</b>: It retrieve, construct, analyze, and visualize street networks from OpenStreetMap.

<b>Scipy</b>: The package contains modules for optimization, linear algebra, interpolation and so on. 

<b>Descartes</b>: It allows the usage of geometry objects as matplotlib paths and patches.

### Package for modelling the data

<b>sklearn</b>: Scikit-learn is a free software machine learning library. It features various classification, regression and clustering algorithms, k-means, Train-test split and so on.

### Packages for Graphical representation

<b>matplotlib</b>: The library used to generate plots, histograms and so on.

<b>seaborn</b>: The library is used for statistical graphics reperesentation.

### Package required to Call R packages and codes

<b>rpy2</b>: It is designed to facilitate the use of R by python programmers.

#### R packages

rgdal, dismo, raster, shapefiles, sf, gamsel

## Installation and Environment setup

Please follow the sequence as it is given. The work is done over windows operating system. So guidelines are basically only for windows. Later will let you know about Linux. If possible forward your work with windows.

For the packages, you need high gb RAM system as 4 gb is not sufficient for the work, unless until you are not working with hpc cluster.

Download Anaconda https://www.anaconda.com/distribution/ by selecting 64-Bit Graphical Installer in windows option. You could try by using 32-bit, because with time many changes occur for the users in case if you are unable to do it with 64-Bit Graphical Installer.

Open Anaconda prompt then upgrade the setup tools for wheel-

<em>python -m pip install --upgrade setuptools wheel pip</em>

1) First package need to be installed is geopandas. But geopandas installation depends on other libraries. For required dependencies of geopandas you need to download wheel file with extension .whl.

The installation of dependencies for geopandas. These five wheel files are GDAL, Fiona, pyproj, rtree, and shapely need to be downloaded from the https://www.lfd.uci.edu/gohlke/pythonlibs/. Press ctrl+F, type name of files, click on the word and download wheel files suitable for your RAM.

* After downloading wheel files, go to Anaconda command prompt.
* Change the directory where you have downloaded the files by typing cd Downloads

<em>cd Downloads</em>

Lets startup with the installing wheel files.

First wheel is GDAL and the library needs environment setup, so first install it with the given command 

<em>pip install GDAL-2.3.2-cp37-cp37m-win_amd64.whl</em> 

Now setup the environment with the following steps:

* Right click on My computer/ PC / This PC (as given in your OS, in my OS 'This PC' is given :)).
* Select properties.
* Click on Advanced system settings.
* Click on Environment Variables.
* In system variables select Path.
* Click Edit.
* At the end(next to ';') type the directory ;C:\Users\jyoti\Anaconda3\Lib\site-packages\osgeo the path is where you have saved your Ananconda file.
* Click ok.
* Click New in system variables.
* In Variable name:
* Type GDAL_DATA
* In Variable value:
* Type C:\Users\jyoti\Anaconda3\Lib\site-packages\osgeo\data
* Click ok.
* Again click New in system variable.
* In Variable name:
* Type GDAL_DRIVER_PATH
* In Variable value:
* Type  C:\Users\jyoti\Anaconda3\Lib\site-packages\osgeo\gdalplugins.
* Keep clicking ok. Environment setup for GDAL has done. Hurray!

Now in sequence follow the listed command in the Anaconda command prompt as given:

<em>pip install Fiona-1.8.6-cp37-cp37m-win_amd64.whl pyproj-2.1.3-cp37-cp37m-win_amd64.whl Rtree-0.8.3-cp37-cp37m-win_amd64.whl Shapely-1.6.4.post1-cp37-cp37m-win_amd64.whl</em>

All dependencies have been installed for geopandas. Now you need to install geopandas with the following command:

<em>pip install geopandas</em>

2) Download other wheel files Rpy2 and rasterio from the same link as used for dependencies of geopandas. Here rasterio is the dependency file for georasters. 

<em>pip install rasterio-1.0.23-cp37-cp37m-win_amd64.whl rpy2-2.9.5-cp37-cp37m-win_amd64.whl</em>

For Rpy2 you again need to setup the enviornment in the following manner:

* Follow the same process as GDAL.
* In system variable click edit.
* At the end(next to the character' ; ') type the directory -C:\Program Files\R\R-3.5.3\bin\i386;C:\Users\jyoti\Anaconda3\Scripts the path is where you have saved your R file and Ananconda file respectively. This is fine for the system having the version of R. But in case your system consisting two or more versions. You need to add one more directory to the path -C:\Program Files\R\R-3.6.0\bin\x64. 
* Click ok.
* Click New in system variables.
* In Variable name:
* Type R_HOME
* In Variable value:
* Type C:\Program Files\R\R-3.5.3
* Click ok.
* Again click New in system variable.
* In Variable name:
* Type R_USER
* In Variable value:
* Type  C:\Users\jyoti\Anaconda3\Lib\site-packages\rpy2
* Keep clicking ok. Environment setup for rpy2 has done.

Here, you have done all installations of the downloaded wheels. Now for installation of other packages, lets come back to our original directory. For that type the following given command in anaconda command prompt.

<em>cd ..</em>

Install georasters, osmnx, seaborn, imblearn with the given following commands:

<em>pip install georatsers, seaborn, osmnx</em>

<em>pip install -U imbalanced-learn</em>

## Import all libraries in Jupyter-notebook


```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from shapely.geometry import Point, Polygon, MultiPolygon
import geopandas as gpd
import georasters as gr
from sklearn.model_selection import train_test_split
from imblearn.over_sampling import SMOTE
from shapely.ops import cascaded_union
from sklearn.linear_model import LogisticRegression
from sklearn.linear_model import RidgeClassifier
from sklearn.linear_model import Ridge
from sklearn.linear_model import Lasso
from sklearn.preprocessing import StandardScaler
from sklearn import metrics
from sklearn.model_selection import GridSearchCV
import rpy2.robjects as ro
from rpy2.robjects.packages import importr
from rpy2.robjects import r, pandas2ri
from rpy2.robjects import Formula
pandas2ri.activate()
import seaborn as sns
```

How to import R packages, we will see in next files.

# Github Repository Important Information
This repository contains several large files, requiring Git LFS support. 
Make sure that Git LFS is installed before cloning the repository.
To clone the repository use the "git lfs clone" command and not just "git clone".

# Space Archaeology

Space Archaeology is a bachelor thesis project which has as goal to detect burial mounds, also termed tumili, from LiDAR based Digital Terrain Models and settlement mounds from Synthetic Aperture Radar Sentinel-1 satellite data.

The application supports 4 different types of relief models:

- Slope

- SLRM - Simple Local Relief Model

- MSRM x1 - Multi-Scale Relief Model with a scaling factor of 1 

- MSRM x2 - Multi-Scale Relief Model with a scaling factor of 2 

The application takes in a png file of the LiDAR based DTM data for each of the respective relief models and scans for burial mounds.

For settlement mounds the application takes in a png file of the data and scans for SAR signatures which could be potential settlement mounds.


	
## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install all the required libraries:

```bash
pip install -r ./requirements.txt
```

Set up the database:

```bash
flask init-db
```

## Running

To run the project locally: 

```bash
flask run
```

## Use of App

```bash
to be added
```

## Available Test Data for App

```bash
The repository Dataset folder contains all data sets used for input to train models. 
The Burial Mound Data Norway and SAR Data Central Asia has data files for the test areas used in the thesis.
Each Test Area folder contains png files which can be used for testing the App. 
For SAR data there are two test areas. For burial mound data there is one test area with a png file for each type of relief model.
Ground truth Esri shapefiles for the burial and settlement mounds can also be found in the results and test area folders,
and can be used in ArcGIS Pro. 
(An ESRI shapefile is actually several different files, including the projection used for the shapes).

The App uses the coordinates for the top lef corner of each test png image to calculate result files with coordinates.
Test Area Coordinates to Use:

- Bukhara Test Area Coordinates - WGS1984:  West: 64.3206 North: 40.2453
- Kandahar Test Area Coordinates - WGS1984:  West: 65.188 North: 31.6807
- Klepp Test Area Coordinates - UTM32V: West: 304345 North: 6520226
```

##Creating ESRI Shape Files in ArcGIS Pro and QGIS

```bash
The repository contains python scripts for creating ESRI shapefiles in QGIS, and also
Jupyter notebooks for creating the ESRI shapefiles in ArcGIS Pro.
Each has two versions. 
There is one version for creating the shapefiles with a WGS1984 projection, used for settlement mounds.
The other version is for creating the shapefiles with a UTM32 projection, used for burial mounds. 

The result csv files from the App is the input for these scripts. 
Running the scripts will add the model result bounding boxes to ArcGIS Pro and QGIS display automatically.
In addition, the different shapefiles will be stored in the output folder defined. 

ArcGIS Pro:

- Place the Jupyter notebook in the ArcGIS Pro project.
- Open the Jupyter notebook from ArcGIS Pro Catalogue pane.
- Edit the input file and output file parameters. 
- Run the notebook. 

QGIS:

- Open the Python interface.
- Load the script file.
- Edit the input file and output file parameters.
- Run the script. 


```

## Google Earth Engine

```bash
This repository has a folder called "Google Earth Engine Scripts and Quick Guides", which contains several Javascripts for use in the Google Earth Engine Code Editor.
Each java script has descriptions on how to use them. All scripts create GeoTiff files which can be exported to Google Drive or Google Cloud.
Scripts requiring input rasters not available through Google Earth Engine must be uploaded. Should the size be above 10 GB, a Google Cloud acount is needed. 

A PDF called "Using Google Earth Engine to Create Multi-Band Sentinel-1 and 2 Composite" is available in this folder, which explains some of the details about using the code editor.
To create GeoTiff files of SAR data as used in this thesis, the "Sentinel-1_SAR_Multitemporal_Composite_Javascript_for_GEE" code should be used.
Scripts available:

-Multitemporal_14band_Sentinel_Composite_Javascript_for_GEE - Creates a 14 band composite of Sentinel-1 SAR data and Sentinel-2 multi-spectral data.
-Sentinel-1_SAR_Multitemporal_Composite_Javascript_for_GEE - Creates a 4-band composite of Sentinel-1 SAR data. VV and VH Polarization in both ascending and descending mode.
-Sentinel-2_Multispectral_Multitemporal_Composite_Javascript_for_GEE - Creates a 10 band composite of multi-spectral Sentinel-2 data.
-MSRM_Calculation_Javascript_for_GEE - Calculates Multi-Scale Relief Model GeoTiff from DTM Geotiff data. DTM data must be uploaded to GEE. See "Calculation of MSRM of DTM Data in GEE.pdf" for more details.
-Random_Forrest_SAR_Javascipt_for_GEE - Calculates a Random Forrest probability map GeoTiff from Sentinel-1 SAR data. User must specify geometries for features to look for and other features. 
```

##ArcGIS Pro Information and DTM Data Download

```bash
LiDAR based Digital Terrain Models used in this thesis was downloaded from Hoydedata.no.
The ArcGIS Info folder in this repository contains a PDF file called "Norwegian LiDAR DTM Data – Acquiring and Setting Up Data in ArcGIS Pro",
which describes how to download and add the DTM data to an ArcGIS Pro project. How to create a Slope display and Simple Local Relief Model display is also explained. 
```

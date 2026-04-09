---
title: "Creating a point layer of locations in ArcGIS Pro"
layout: "home"
description: "This is a beginner’s guide to creating a point layer in ArcGIS Pro using the latitude and longitude of the locations you wish to display. How to locate coordinates online will be discussed. The first part of this guide will walk you through creating an Excel file of coordinates found in decimal degrees that are set up and ready to be imported into ArcGIS. This guide will then walk you through bringing your data into ArcGIS and creating your point layer on top of a base layer of countries."
staff:
    - name: Nick Field
      link: https://library.utoronto.ca/staff/nick-field
maintainer:
    - name: Cole White 
      link: https://library.utoronto.ca/staff/cole-white
created_date: 2024-02-20
permalink: "/"  #! Remove this if not the homepage
---

# Creating a point layer of locations in ArcGIS Pro

This is a beginner’s guide to creating a point layer in ArcGIS Pro using the latitude and longitude of the locations you wish to display. How to locate coordinates online will be discussed. The first part of this guide will walk you through creating an Excel file of coordinates found in decimal degrees that are set up and ready to be imported into ArcGIS. This guide will then walk you through bringing your data into ArcGIS and creating your point layer on top of a base layer of countries.

For this guide we will be using an Excel table with information for places that would be great to visit around the world.

1. Open up a new document in Excel.

    Label your headings as the first row of your spreadsheet will contain the names of each column. In this guide, we have a **Locations** column to put the name of the place you have coordinates for. This column is followed by a **Latitude** and **Longitude** column that must have a **Number** format, unlike the **Locations** column. Columns will default to being in a **General** format, unless you change them.

    Once you have created your header row, you can input your data into the cells below. You can even create columns with other sorts of data that you may want to have accessible to you in ArcGIS.

    <img src='{{ '/assets/images/1.png' | relative_url }}' alt='Excel grid showing our end result fully filled in. columns are: Location, Latitude, Longitude, and Attractions.' title='' width='467' height='173' />
2. Finding coordinates for sites of interest has never been so easy! Go to Wikipedia, type in the city or area of interest. For the majority of articles about places in Wikipedia the coordinates listed in the top right hand side of the screen with a small globe beside it. Click on the particular coordinates for the site (the word “Coordinates” and the globe will bring you to different places) and you will be linked to GeoHack.

    <img src='{{ '/assets/images/2.png' | relative_url }}' alt='A red box surrounding the coordinates section of the webpage ' title='' width='285' height='54' />

    GeoHack has all of the pertinent spatial data for your site that you will need.

    <img src='{{ '/assets/images/3.png' | relative_url }}' alt='Red highlighter over the coordinates in Decimal system' title='' width='465' height='228' />

    We are interested in the second set of coordinates, highlighted in the screenshot above (labeled Decimal).

    To fill up the Excel table we will be taking the Decimal Degree data, highlighted in red in the image above from GeoHack, from a range of destinations the world over. The first coordinates to the left of the Decimal Degree data represent **Latitude** and the coordinates on the right represent **Longitude**. Copy and paste the data from GeoHack into your columns in Excel and don’t forget to include any negative signs as they are a crucial component of your coordinates.

    The Excel file created for this exercise is composed of destinations that we would love to visit with columns for location data, latitude, longitude, and a brief description of what makes the location special.
3. Save and close your Excel file as a **.csv** when it is completed and the columns are formatted. Once your Excel table is complete you can move to working in ArcGIS. This guide is designed to complement version ArcGIS Pro 3.2.

    <img src='{{ '/assets/images/1a.png' | relative_url }}' alt='overview of making sure that the cell C2's (column longitude) is set to the Number data type' title='' width='835' height='456' />
4. For a base map, this guide will be using the free-to-download **Countries** vector layers (highlighted red in the image below) from the Natural Earth website: [http://www.naturalearthdata.com/downloads/110m-cultural-vectors/](http://www.naturalearthdata.com/downloads/110m-cultural-vectors/)

    Download the Countries data. The data is compressed, so before you can use it you will need to unzip it. If you don’t have any software to unzip files, 7-zip is a great free program that is easy to install. You can find it here: [http://www.7-zip.org/](http://www.7-zip.org/).

    [<img src='{{ '/assets/images/5_3.png' | relative_url }}' alt='Screenshot highlighting where to download the countries vector layers from the Natural Earth website.' title='' width='984' height='670' />](http://www.naturalearthdata.com/downloads/110m-cultural-vectors/)
5. Open a new, blank map and then go to **Project** and **Save Project As**, and then give your map a name to save it. We called ours **ExcelToPoint**. Saving your map right away is good practice as you should consistently save your work as you go along in ArcGIS.

    It is also incredibly important that you NEVER save work with names that have a space in them or in folders that have names with spaces in them. Keep names to one word or indicate spaces by using an underscore ( \_ ).
6. Add to your map the Countries data that was retrieved from Natural Earth. To do this go to the **Add Data** button at the top of the screen on the toolbar that is highlighted in red in the image below. Add the Natural Earth unzipped shapefile data; it will have a .shp extension.
7. <img src='{{ '/assets/images/image_4.png' | relative_url }}' alt='Adding of the map' title='' width='864' height='356' />

    Add your Excel file the same way as you added the Countries data – you will have to select the Excel file and the Sheet that your data is on. For this exercise our data is on the first sheet and the default name given to it is **Sheet1**.
8. Once you have added your data you should note that the excel file we just added is under Standalone Tables and is not drawn on the map.

    <img src='{{ '/assets/images/image_5.png' | relative_url }}' alt='Downloaded and now inserted map is shown, additionally the PointMap.csv file is there below the tab "Standalone Tables"' title='' width='328' height='331' />
9. In order to have your Excel data become spatial data in your map you will go to, **Add Data**, **Add XY Point Data**, and from the dropdown menu select the Excel sheet that you have added to ArcGIS already with your data in it. (If the fields do not automatically fill in), select the column labeled **Longitude** to be the **X Field** and that **Latitude** is selected from the dropdown menu for the **Y Field**. The **Z Field** is for Z Values representing elevation or height data that can be used to make three dimensional data. But we won’t worry about that here and we’ll just leave it as **blank**.

    <img src='{{ '/assets/images/image_7.png' | relative_url }}' alt='GUI popup of the XY Point Data option after pressing on Add Data' title='' width='303' height='321' />

    <img src='{{ '/assets/images/image_8.png' | relative_url }}' alt='Showing the XY Table to Point GUI and the features input' title='' width='423' height='362' />
10. ArcGIS will automatically set a **Geographic Coordinate System** and **Projection** for your new layer. This information is based on the coordinate system and projection of your map.

    The Coordinate System and Projection of your map is initially set by the first layer with spatial data added to it. This information for your map can be found in the window that pops up if you double click **Layers** (highlighted in the image below). The Coordinate system and projection can be changed for your map and/or for your layer in several different places. To change the coordinate system and projection just for your layer, you can easily do this at the **Add XY Data** window. But, we won’t need to do this in this example. If you would like more information on changing Coordinate Systems and Projections, please go to this link: [https://mdl.library.utoronto.ca/technology/tutorials/selecting-right-projection](https://mdl.library.utoronto.ca/technology/tutorials/selecting-right-projection).

    When you have specified the **X Field** (Longitude) and **Y Field** (Latitude) in the **Add XY Data** window, click **Run**. A warning will appear, just click **Run**.

    A new layer will appear in the Table of Contents with the name of your Excel layer followed by the word **XYTableToPoint** and your Excel information will have translated into points on the map. In our example, we left the title as the default name, so the new layer is called **PointMap_XYTableToPoint**.

    <img src='{{ '/assets/images/image_9.png' | relative_url }}' alt='Contents pane highlighting the output layer' title='' width='333' height='423' />
11. In order to save your new spatial data in ArcGIS and if you want to interact with your data (query, select, etc.) later on, there is one final step to undertake. Your new Events layer needs to be transformed into a shapefile or feature class.

    Export your Excel layer by right-clicking on the layer in the Table of Contents. Go to **Data**, **Export Data**. The **Export Data** window will pop up. Make sure the dropdown menu has **All Features** selected and the coordinate system will be **this layer’s source data**. In the **Output feature class** box select where you want to choose where to save your data and you can give it a new name as this process will save your work as a new layer. This new layer is an official point shapefile. For this exercise, we called the new layer **NewShapefile** (remember not to have any spaces in names). When this is done, hit **OK**.

    <img src='{{ '/assets/images/12_1.png' | relative_url }}' alt='UI showing the export features class selection highlighted' title='' width='507' height='604' />

    <img src='{{ '/assets/images/12a.png' | relative_url }}' alt='Export features tool with the inputs and outputs set' title='' width='356' height='530' />
12. A message box will pop up asking you if you want to add the exported data to the map as a layer and you will hit **Yes** and the new shapefile will appear in your **Table of Contents**. You can remove the **Events** layer by right clicking it and selecting **Remove**. The **Events** layer will not be of use to you for now on.

    <img src='{{ '/assets/images/13_1.png' | relative_url }}' alt='Removing the events layer' title='' width='328' height='280' />
13. If you right click on your new layer, **NewShapefile**, and click on **Attribute Table**, you will see that each destination that was in the original Excel file now has their own **FID** column. **FID** is a value that lets the GIS program work with and identify each point.

    <img src='{{ '/assets/images/14_0.png' | relative_url }}' alt='Checking the attribute table of the NewShapefile' title='' width='543' height='255' />
14. Save your work!

    And you are done transforming an Excel table into a shapefile in ArcGIS that can be reused and queried.

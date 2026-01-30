---
section: Workshop Sessions
nav_order: 2
title: Week 2. Working with Spatial Data
topics: Georeferencing; geocoding; data structures
---

## Learning Objectives

- Explore how to represent your data.
- Learn how to effectively structure data for visualization.
- Use OpenRefine to prepare data for visualization.
- Learn how to create raster data through georeferencing.
- Extract vector data from georeferenced map.

## Wrangling Data

Preparing your data for spatial visualization requires you to review, revise, and augment your data. At the very least, you will need to add coordinates so that a mapping platform can read your data and place it on a map. Usually, you will want to add additional geographic and non-geographic information that enables interpretation of your map and the argument you are trying to make with your map. You may also need to reorganize your data and address inconsistencies that may misrepresent what you are seeing in your research. This multistep and iterative process is often referred to as data wrangling.

### Structuring your Data

You can think of structuring your data as the process of organizing and gathering additional data. This is important for digital mapping because:

- It makes it possible/easier for mapping platforms to read and represent your data.
- It makes your data flexible and transferable.
- You can provide additional meaning that complements your data, like labels and other metadata.
- You will think critically about your data and what it does and does not say.

Here are some questions to help you think about your data and what you need to do:

- What do you want your map to display?
- What columns do you need to organize and add data?
- What data will be visible to the end user?
- Is your data consistent?
- How do you make your data mappable?

As you modify your spreadsheet (.csv file), it may help to think about your data as two different types of data: display data (for a human) and non-display data (for a computer):

*display data:*

- title
- subject
- description
- other interpretative data

*non-display data:*

- filenames
- coordinates
- source
- address

### Cleaning your Data

The idea of cleaning your data is a contested term, but many still find it useful to describe the process of addressing inconsistencies found in a dataset. Katie Rawson and Trevor Muñoz's ["Against Cleaning"](https://dhdebates.gc.cuny.edu/read/untitled-f2acf72c-a469-49d8-be35-67f9ac1e3a60/section/07154de9-4903-428e-9c61-7a92a6f22e51#ch23) explains the drawbacks of viewing your data as something that needs to be "cleaned." The article will also help you think more critically about how you gather and transform your research data. Whether you are cleaning or use "other terms that people use alongside “cleaning” (wrangling, munging, normalizing, casting)," you will come across some of the following issues in your data that are difficult to spot with the human eye and that may cause misleading maps or misrepresentations of your data:

- Misspellings
- White space
- Multiple spellings
- Inconsistent capitalization
- Blank cells

## Georectification/Georeference

Historical and scanned physical maps that are not associated with a coordinate grid will limit your ability use such a map in a digital mapping project. While some may work with an image altering platform like Adobe Photoshop to make meaning of these maps, such a project will not have transferable data nor be readable by a mapping platform. A solution is to use a georectification or georeferencing tool to bind your image to a coordinate system. We will use the tool [MapWarper](https://mapwarper.net/) to georectify our map. This process will transform our static image into spatial data and create raster data that will allow us to further our mapping project. With this process you can:

- Create a basemap and then overlay other data.
- Extract additional historical vector data to further spatial analysis and interpretation.

### Some Core Concepts

- Georeferencing: Assign real-world coordinates to a scanned map or raster image.
- Georectification: Geometrically adjust to correct distortions and align with a spatial reference system.
- Ground Control Points: Identifiable locations used to align the source image with real-world geographic coordinates. They are used as “anchor” points.
- Transformations: Transformation algorithms mathematically adjust the image (by shifting, scaling, rotating, and warping it) so that its GCPs match their corresponding points on a modern map.

### Georeference with MapWarper

#### Step 1: Sign in to MapWarper

If you have not created an account, please do so [here](https://mapwarper.net/u/sign_up).

#### Step 2: Search for Your Map

Always check to see if your map has already been georeferenced. This could save you a lot of time or at least give you a starting point for more accurate rectification.

#### Step 3: Upload Your Map

Add your map to the MapWarper site. But sure to include as much identifying metadata as possible. This will both give proper credit to the origins of your map and it will allow others to find it and potentially use it in their own research.

#### Step 4: Mask the Map (optional)

Masking allows you to exclude irrelevant areas from your image. This may improve warping later and therefore prevent excessive distortion or limit your image hiding useable areas from another map layer. 

#### Step 5: Rectify the Map

1. Select a basemap. MapWarper's default is [OpenStreetMap](https://www.openstreetmap.org/).
2. If you choose a custom map:

    - use this URL: https://api.maptiler.com/maps/streets/{z}/{x}/{y}.png?key=N5eIWK6rP0DevdaIjRSn **OR**
    - Visit https://www.maptiler.com/ > Create an account > Get your API key > Export in xyz format the map of your preference

3. Lock the two map windows. This ensures they pan and zoom together.
4. Add ground control points between the historical and modern map.
5. Move or delete control points as needed to refine accuracy.
6. Test different transformation methods.
7. Warp the map.
8. Overlay the warped map to inspect results.
9. Refine and repeat until satisfied.

#### Step 6: Export

1.	Export as KLM
2.	Tiles url: export yours and then compare with: https://mapwarper.net/maps/tile/93674/{z}/{x}/{y}.png

## Geocoding

Latitude and longitude coordinates are an essential addition to your textual data to ensure you can represent your text with points on a map. Often, digital map makers will add separate latitude and longitude columns to their spreadsheet. 

If you are manually copying or entering coordinates, be careful not to transpose numbers or leave out a minus sign. This may place your location on the other side of the globe.

### Getting Coordinates

Geocoding: a computational process of transforming a description of a location, such as an address or place name, into geographic coordinates. 

Coordinate format: You will want your coordinates in decimals rather than degrees. Below are examples for Firestone Library:

- Decimals: 40.34972638362372, -74.6574238318438
- Degrees: 40°20'59.013", -74°39'26.7264"

### Geocoding Workflow

#### Step 1: Open Google Earth

Access the [Google Earth web tool](https://earth.google.com/web). If you are having trouble with the web tool, you can download [Google Earth desktop pro](https://earth.google.com/intl/earth/versions/#earth-pro) as an alternative.

#### Step 2: Upload Basemap

1. Copy `tiles url` (under map services) in MapWarper.
2. In Google Earth, click `+` and then select `tile overlay`.
3. In the left popup box:
    - Copy and past MapWarper url to `overlay URL pattern`.
    - Add a title for your map.
    - Click `view`.
4. Zoom in to area to make sure map is properly displaying.

#### Step 3: View Troubleshooting

If your georeferenced map is not showing properly, review possible default view settings in Google Earth that may obscure your map.

1. Click `view` in top navigation.
2. Click `layers`.
3. Toggle different features and make sure different 3D objects are off.

#### Step 4: Find Coordinates

Because we are dealing with a historic map of a neighborhood that no longer exists, we cannot use addresses and therefore cannot use a geocoding tool to automate the collection of coordinates for our research objects.

1. At the left navigation window of Google Earth, click the folder icon.
2. Name the folder `object points` and then exit the popup.
3. Find and click `add placemark` button.
4. Click the point on the georeferenced map that you would like to add to the map.
5. Title the new placemark. If you are following along, add the placemark number from the original map.
6. Repeat until you have marked all research objects on the georeferenced map.

#### Step 5: Download and Review KML File

1. Download KML file from Google Earth. Click `File` in the navigation and then click `export as KML file`.
2. Open VS Code, then click `Open File` and find the downloaded KML file. It should be in your download folder.
3. The KML file is more generally an XML file which follows a tree-like structure. This is all the data from Google Earth. We're just interested in points so scroll down to the `folder` element which looks like `<folder>` and then find `<placemark>`.

#### Step 6: Extract Coordinates from KML File

1. Find the title of your first object under `<placemark>` and within the `<name></name>` element.
2. Then, within that same `<placemark>` element, find the `<latitude>` and `<longitude>` elements. Copy the corresponding latitude and longitude to the corresponding columns in your spreadsheet. Avoid copying unnecessary white space.
3. Repeat for each object. Be mindful of which element nesting you are in so that you copy the correct coordinates.

While we are doing this manually, you can perform this programmatically by writing a short script to find each lat and long in the KML file and extract and write the coordinates into a csv. This is more advanced and beyond the scope of this series.

#### Step 7: Review CSV

1. Upload your updated CSV to OpenRefine
2. Facet your coordinate columns to see if there are any

## Before Next Session

1. If you have not already, create a [GitHub](https://github.com/) account.
2. Complete addition of coordinates to your dataset.
3. Complete further wrangling of your data to ensure it will be useable in a mapping platform.
4. Attend office hours if you would like. These will be held September 29 and October 1 from 10:30am-noon. This is a great opportunity to bring questions or co-work on your project with other participants.
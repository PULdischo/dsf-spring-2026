---
section_id: Workshop Sessions
nav_order: 3
title: Week 1. An Introduction to Mapping and Spatial Data
topics: Text editors; file types; spatial data 
---

## Learning Objectives

- Introduce the benefits and challenges of digital mapping
- Identify key technical and methodological concepts of digital mapping
- Review different file and data types
- Become comfortable with a text editor
- Discuss the relationship between data and visualization

## Thinking Spatially

### Why Digital Mapping

Digital maps enable:

- Spatial analysis
- Representation or illustration of evidence or arguments
- Storytelling

### Some Guiding Questions

- How can we think about and engage with space?
- How do we address the tension between the supposed precision of mapping and the ambiguity and uncertainty of our research?
- What tools will help us create maps that further our research agenda?

### What to Ask About Your Research

- What in your research can be represented on a map?
- What do you have already? And what do you need?
- How can you structure you research as spatial data?

### Digital Map Makers Toolkit

- plain text files
- text editor
- geocoder
- visualization platform
- publishing mechanism

### Geographic Information

GIS stands for Geographic Information System, but what is geographic information? What kind of files store geographic information? And what kind of tools or platforms can read those files and the information contained within?

We will answer these questions today and in more detail each week

Geographic information is often referred to as vector data and raster data.

### Raster Data

**Definition:** A matrix of pixels or cells.

**Purpose:** To show imagery or continuous fields or surfaces.

**Examples:** elevation; precipitation; temperature

**Our use for this course:** We will georeference a map and therefore create raster data.

Raster data is often the map you are putting things on.

### Vector Data

**Definition:** The things you put on a map.

**Purpose:** To represent information in a finite way and to highlight attributes and/or interpretive information.

**Examples:**

- Points
- Lines: rivers; paths; borders
- Polygons: neighborhoods; states; lakes

**Our use for this course:** We will create vector data that demonstrates where our research objects are and what attributes about our objects we want to highlight or make easier to interpret.

### Data Structures and their File Types

To create digital maps, you may need to familiarize yourself with data structures and file types that you do not use regularly or have not encountered before. Throughout this series we will engage with three main structures:

- *tabular*: Tabular data is probably what you are most comfortable with. If you have ever worked with a spreadsheet, you have worked with tabular data.
- *key-value*: Linked data items that establish constants (the key) and variables (the value).
- *tree-like*: Nested data that branches out from nodes to maintain hierarchical relationships of data. Think of how a family tree begins and then branches out each generation.

We will also work with a number of file types: 

- *.csv*: Comma-Separated Values (tabular)
- *.json*: JavaScript Object Notation (key-value)
- *.kml*: Keyhole Markup Language (tree-like)

#### Another Type: Shapefile

Digital mapping may require more complex file types that are actually a series of files. The initial file is related to additional files so that a mapping tool can read and properly represent the included data. One example if a shapefile:

- .shp: shapefile contains vector data (feature geometry) and requires at least two other files: .shx (index of feature geometry) and .dbf (attribute information)

There are other file types that can be used in digital mapping projects and we will come across them. It particularly important to understand which file types are useable my multiple platforms and tools, and which file types are proprietary (can only be used by specific platforms). This will have implications for the sustainability of your project.

### Early Mapping Platform Considerations

Each platform or tool will have specific requirements that may or may not limit the future direction of your project.

Reading documentation is essential as your prepare your data:

- What are its file requirements?
- Do we need to change our data structure?
- Do we need to add anything to our dataset?

## Getting to Know Your Text Editor

A text editor will allow us to more easily explore the many file types we will need to build a successful project.

While any text editor is welcome, we recommend [Visual Studio Code](https://code.visualstudio.com/) for this workshop series. VS code is commonly used and has a lower barrier to entry. Plus its free! If you haven't already, please [download VS Code](https://code.visualstudio.com/Download).

Text editors allow you to easily read and edit plain text files like the ones we will use to build a digital map in this course. We will hold a live demo to explore the basics of VS Code and continue using the text editor throughout our series.

### VS Code Extensions

The following [VS Code extensions](https://code.visualstudio.com/docs/configure/extensions/extension-marketplace) will expand the capabilities of VS code and make it easier for you to work with our course materials:

- [Rainbow CSV](https://marketplace.visualstudio.com/items?itemName=mechatroner.rainbow-csv)
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [Edit CSV](https://marketplace.visualstudio.com/items?itemName=janisdd.vscode-edit-csv)
- [Code Spell Checker(https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)]

## Viewing your Research as Data

While some may be comfortable viewing their research as data, others may not have been trained to think this way. For digital mapping, its helpful to think of your research in terms of types of data. This will encourage you to ask different and additional questions of your research.

### Provided Research Materials

If you do not have your own research data to work with for this series, you can follow along and work with the collection I will be using during our demonstrations. At times, you may even want to work with these materials to complete some of our hands-on tasks.

This hands-on workshop uses objects from the [Messinesi Photographs Collection](https://collections.visualresources.princeton.edu/Detail/collections/155) which is part of the [Homer A. Thompson Collection](https://collections.visualresources.princeton.edu/Detail/collections/58) house in [Visual Resources Collections](https://collections.visualresources.princeton.edu/) of Princeton University's Department of Art and Archaeology.

**materials:**

- [Vrysaki map](https://collections.visualresources.princeton.edu/Detail/objects/49422)
- [Messinesi photographs](https://collections.visualresources.princeton.edu/Detail/collections/155)
- [Photograph metadata](https://docs.google.com/spreadsheets/d/1vz_CAGkI6uHUDs2A5U6auAzxxVls_ulbuRFXydKnxeM/edit?usp=sharing)

### Questions to Ask About your Data

- What data do you have?
- What data might you need?
- What is the most important data you want to show?
- How do you want your data to relate to each other?

### Questions to Ask About Visualization

- How will others interact/engage with your project?
- How are others going to interpret your visualizations/maps?
- Are there any maps or visualizations out there you like?
- Are there any you don't like?

## Next Session

If you haven't already, download [OpenRefine] (https://openrefine.org/download) and ensure you have set up a [GitHub](https://github.com/) and downloaded the [GitHub Desktop client](https://github.com/apps/desktop).

Identify what spatial data is missing from our dataset and/or your project.
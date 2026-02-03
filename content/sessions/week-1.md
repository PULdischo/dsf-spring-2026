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

## Getting to Know Your Text Editor

A text editor will allow us to more easily explore the many file types we will need to build a successful project.

While any text editor is welcome, we recommend [Visual Studio Code](https://code.visualstudio.com/) for this workshop series. VS code is commonly used and has a lower barrier to entry. Plus its free! If you haven't already, please [download VS Code](https://code.visualstudio.com/Download).

Text editors allow you to easily read and edit plain text files like the ones we will use to build a digital map in this course. We will hold a live demo to explore the basics of VS Code and continue using the text editor throughout our series.

### VS Code Extensions

The following [VS Code extensions](https://code.visualstudio.com/docs/configure/extensions/extension-marketplace) will expand the capabilities of VS code and make it easier for you to work with our course materials:

- [Rainbow CSV](https://marketplace.visualstudio.com/items?itemName=mechatroner.rainbow-csv)
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [Edit CSV](https://marketplace.visualstudio.com/items?itemName=janisdd.vscode-edit-csv)
- [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)

### Viewing a CSV in its Natural Habitat

CSV (comma-separated values) files are a tabular data structure much like an Excel workbook or Google sheet. The important difference is that it is a plain text file and is often a file type that is compatible with mapping platforms. Download [our metadata](https://docs.google.com/spreadsheets/d/1IrL6s7HLRZyPgi3KbdlECVYfE2YcMg9cPdNkvKRopSU/edit?usp=sharing) so we can view the file in VS Code and begin to wade into the world of plain text.

## Viewing your Research as Data

While some may be comfortable viewing their research as data, others may not have been trained to think this way. For digital mapping, its helpful to think of your research in terms of types of data. This will encourage you to ask different and additional questions of your research.

### Questions to Ask About your Data

- What data do you have?
- What data might you need?
- What is the most important data you want to show?
- How do you want your data to relate to each other?

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

### Provided Research Materials

If you do not have your own research data to work with for this series, you can follow along and work with the collection I will be using during our demonstrations. At times, you may even want to work with these materials to complete some of our hands-on tasks.

This hands-on workshop uses objects from the [Messinesi Photographs Collection](https://collections.visualresources.princeton.edu/Detail/collections/SR-000072) which is part of the [Homer A. Thompson Collection](https://collections.visualresources.princeton.edu/Detail/collections/C-000008) house in [Visual Resources Collections](https://collections.visualresources.princeton.edu/) of Princeton University's Department of Art and Archaeology.

- [Messinesi's Vrysaki map](https://drive.google.com/file/d/1Bh7Ce8NsIrNY8noPEelaaDpmlvPqzZ7t/view?usp=sharing)
- [Messinesi photographs](https://collections.visualresources.princeton.edu/Detail/collections/SR-000072)
- [Photograph metadata](https://docs.google.com/spreadsheets/d/1IrL6s7HLRZyPgi3KbdlECVYfE2YcMg9cPdNkvKRopSU/edit?usp=sharing)

To reconstruct Vrysaki, we must associate our current research data with spatial data. We will work through the phases, methods, and tools of a mapping project throughout the rest of our sessions. Even though this process will be presented in a linear order, you should always iterate over common questions and concerns as you develop and improve your project.

## Transforming Our Data

Preparing your data for spatial visualization requires you to review, revise, and augment your data. At the very least, you will need to add coordinates so that a mapping platform can read your data and place it on a map.

### OpenRefine

[OpenRefine](https://openrefine.org/download) is a powerful free, open source tool for working with messy data. It helps minimize human error as you edit your data. It also allows you to explore patterns that may be challenging to find without the assistance of the computer. 

The remainder of today's session will make us comfortable with the basic functions of OpenRefine.

## Next Session

Identify what spatial data is missing from our dataset and/or your project.

If you haven't already, ensure you have set up a [GitHub](https://github.com/) and try downloading the [GitHub Desktop client](https://github.com/apps/desktop). If you have trouble, we will address this at another session
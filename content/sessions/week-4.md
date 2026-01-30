---
section: Workshop Sessions
nav_order: 4
title: Week 4. Code Templates and Customization
topics: Customization; leaflet; web publishing
---

## Learning Objectives

Learn how to fork and clone repositories with GitHub.
Read a code template.
Explore building blocks of the web.
Develop code locally using JavaScript and Leaflet.js.
Generate a basic website locally and/or publicly using Jekyll.

## Cloning

Cloning downloads a complete copy of the code and history from your GitHub repository and stores it in a folder on your local computer. This clone of the repository is automatically configured to be connected to the version on GitHub.

Cloning allows you to work locally to help you work effectively and efficiently.

We'll first model managing the remote and local relationship with GitHub Desktop. We will eventually use VS Code to manage the relationship between our remote and local repositories.

### Step 1: Install GitHub Desktop

1. Navigate to [GitHub Desktop](https://github.com/apps/desktop) and download the appropriate version of GitHub Desktop for your operating system. 
2. Follow the prompts to complete the installation. For more information, see [Installing GitHub Desktop](https://docs.github.com/en/desktop/installing-and-authenticating-to-github-desktop/setting-up-github-desktop).
    1. Sign in to your Github.com account via the GitHub Desktop prompt.
    2. Select `authorize` after reviewing access prompt.
    3. When viewing `configure git` prompt, select `use my GitHub account name and email address`.
    4. Click `finish`
3. Arrive at `Let's get started` prompt.

### Step 2: Configure a Default Text Editor

1. In the menu bar, select `GitHub Desktop`, then click `Settings`.
2. In the Settings window, select `Integrations`.
3. Under "External Editor", use the dropdown menu to select Visual Studio Code to to set as your default text editor.
4. Click `Save`.

### Step 3: Clone Your Repository Using GitHub Desktop

1. Using your browser, go to your GitHub dashboard or repository list and find the repository we created in the previous module. If you followed along, it will be titled `dsf-maps`.
2. On your repository landing page, find the green button titled `< > Code` and click to open a drop down menu.
3. Under the `local` tab, select `Open with GitHub Desktop`.
4. GitHub Desktop will open and show your respository url and a suggested local path. If these look accurate and/or are acceptable, click `clone`. 

### Step 4: Explore GitHub Desktop and its Functionality

1. Explore navigation bar:
    - Current repository dropdown menu
    - Current branch dropdown menu
    - Suggested action:
        - Fetch
        - Pull
        - Push
2. Explore commit viewer:
    - Changes
    - History
    - Commit message
3. Explore main viewer:
    - Open the repository in your external editor
    - View the files of your repository in Finder/Windows Explorer
    - Open the repository page on GitHub in your browser

## Leaflet, Code Templates, and Local Development

### Leaflet

Leaflet ([leaflet.js](https://leafletjs.com/)) is a common JavaScript library that allows you to create lightweight, interactive maps. A library is a term used in programming that refers to a collection of pre-written code. So by using leaflet, you’re using pre-written functions and controls already prepared by a programmer and packaged as a JavaScript library rather than writing your own functions and beginning from the basics of JavaScript. You can then refer to  [leaflet's documentation](https://leafletjs.com/reference.html) to further customize code to create an interactive map that meets your project needs.

### Code Templates

To expedite our use of leaflet, we will also build from a coding template. Some developers have been kind enough to create and promote their code as templates for starting your own project. We will work with the ["leaflet maps with csv" template](https://handsondataviz.org/leaflet-maps-with-csv.html) from the online version of [Hands-On Data Visualization](https://handsondataviz.org/) by Jack Dougherty and Ilya Ilyankou.

Hands-on Data Visualization has a numbers of lessons and starting points, including the following templates:

- [Simple Leaflet Map](https://github.com/HandsOnDataViz/leaflet-map-simple)
- [Leaflet Heat Map](https://github.com/HandsOnDataViz/leaflet-heatmap)

Another great template resource is [Grzegorz Tomicki's leaflet examples](https://tomickigrzegorz.github.io/leaflet-examples/) where you can find over 70 templates and different options for viewing the code.

With any template or code you find on GitHub, be sure to look for comments that explain a line of code or even instruct you how to use that code.

```
/* Display a point marker with pop-up text */
L.marker([41.77, -72.69]).addTo(map) // EDIT marker coordinates
.bindPopup("Insert pop-up text here"); // EDIT pop-up text message
```

The code block above signals a comment within `/* */` and explains what the following two lines of code will do: `Display a point marker with pop-up text`. Then those two lines have explanatory comments following `//`.

Also, when using other people's code, be sure to give proper credit. Use GitHub's `fork` or `use this template` buttons to fork a repository to provide proper attribution.

### Interpreting an HTML Document

Our template is written as an HTML document. HTML is one of the three buildings blocks of the web. This document also includes references to the two other building blocks: CSS (Cascading Style Sheets) and JS (JavaScript). While best practices encourage you to separate your HTML, CSS, and JS, it will be easier to first learn from a document that combines these elements. Below are the three main components of the file that allow it to be rendered in a browser. These components include subparts that further define your map.

#### Part 1: Document Declaration

An HTML document requires a document declaration that tells the browser what type of code it is looking at. Find `<!DOCTYPE html>` at the top of our document.

#### Part 2: The Header

The HTML element `<head></head>` defines the header of the document. Here you'll find references to CSS stylesheets and JS libraries that the document is then linked to. These allow the file and therefore the browser to pull in and render additional code that provides additional styling.

Our header contains CSS from leaflet; the leaflet library, and jquery, an external JS library to stylize our map.

#### Part 3: The Body

The body is the content of your page and is marked with the HTML element `<body></body>`. Within this element is a range of content and references to additional files like images or scripts elsewhere in your repository.

Our HTML body contains:

- a division that establishes where the map is on the page: `<div id="map"></div>`
- leaflet functions that set the parameters of the map, such as:
    - `L.map()`: establish map and basic parameters like center and zoom level
    - `control.Layer`: creates switch that then allows you to switch between layers 
    - `L.tileLayer()`: brings in raster layers (pixel based images) like a default basemap or your georeferenced map.
    - `L.marker()`: create markers on your map

## Customizing a Leaflet Map

### Step 1: Open Repository in VS Code

1. Use GitHub Desktop to open your repository in VS Code.
2. Review files in repository:
    - `data.csv`: Further refined metadata csv that we will use to generate our map. We will write code later that will loop through the column titles to populate our map with additional data. This will be more efficient than individually hardcoding each marker with the information we want to share.
    - `index.html`: Map template. We will need to change the name because we want a separate homepage that frames our map.

### Step 2: Change Map File Name

1. Right click (or `control` + click) the `index.html` file.
2. Click `rename`.
3. Change file name to `my-map.html`.

### Step 3: Set Map Initialization

1. Go to [Google Maps](https://maps.google.com/) and find a location that is roughly the center of your map.
2. Click that point on the map. You will see latitude and longitude coordinates in the URL and in a small pop up. Copy the coordinates from one of those locations.
3. Find the `center` attribute (line 33) in the `map` variable (line 32). The code will look like this:

    ```
    var map = L.map('map', {
        center: [41.57, -72.69],
        zoom: 9,
        scrollWheelZoom: false,
        tap: false
    });
    ```

4. Paste the coordinates you would like as your map center into the `[ ]` that follows the `center` attribute. This will establish a new center of your map.
5. Change the `zoom` attribute value (line 34) to `16` so we can see all our objects at a higher zoom level. The higher the number (up to 18) the higher the zoom level.

### Step 4: Add Georeferenced Map as a Layer

1. Find the `terrain` variable (line 52). The code looks like this:

    ```
    var terrain = L.tileLayer('https://stamen-tiles.a.ssl.fastly.net/terrain/{z}/{x}/{y}.png', {
        attribution: 'Map tiles by <a href="http://stamen.com">Stamen Design</a>, under <a href="http://creativecommons.org/licenses/by/3.0">CC BY 3.0</a>. Data by <a href="http://openstreetmap.org">OpenStreetMap</a>, under <a href="http://www.openstreetmap.org/copyright">ODbL</a>.'
    });
    controlLayers.addBaseLayer(terrain, 'Stamen Terrain basemap');
    ```

2. Change the URL within the parentheses of the `L.tileLayer()` to `'https://mapwarper.net/maps/tile/93674/{z}/{x}/{y}.png'`. Be sure that you do not erase the `' '` that enclose the URL. This will make our georeferenced map one of the options for our map layers.
3. Edit the map attribution to `'Map tiles by <a href="https://mapwarper.net">MapWarper</a>'`.
4. Change the title of your variable from `terrain` to `messinesi`.
5. Change the variable call and button title within `controlLayers.addBaseLayer()`:
    - new variable call: `messinesi`. Notice how this call and the name of your variable are the same.
    - new button title: `Messinesi Map`.
6. Your completed code should look like this:

    ```
    var messinesi = L.tileLayer('https://mapwarper.net/maps/tile/93674/{z}/{x}/{y}.png', {
        attribution: 'Map tiles by <a href="https://mapwarper.net">MapWarper</a>'
    });
  controlLayers.addBaseLayer(messinesi, 'Messinesi Map');
    ```

### Step 5: Add More Information to the Popup

We want our popup to include information about our images and the image itself. We will use dot notation (`.`) to call on columns from our dataset and then the specific value associate with the object that intersects with that column. Then we will use HTML to describe the called data in our popup.

1. Find `.bindPopup(row.Title)`. This currently calls the "Title" value for each row.
2. Add the code below within the parenthesis of `.bindPopup()`. This will provide additional information and call on our metadata to populate our popup with descriptive information and the corresponding image:

    ```
    `"<b>Item Number:</b>" + row.Title + "</br>" + "<b>Section:</b>" + row.Section + "</br>" + "<b>Description:</b>" + row.Description + "</br>" + "<b>Lot:</b>" + row.Lot + "</br>" + row.Photo`
    ```
3. This code is saying look in `data.csv`, then look at each `row`. As you move along each `row` find the value of any column called on by `.`. We're calling on the columns `Title`, `Section`, `Description`, `Lot`, and `Photo` and asking for each individual value to be placed in the pop up associated with the coordinates in our csv.

## Publishing with GitHub Pages

Using a mapping platform or writing code that creates a map does not guarantee that your project will be publicly accessible. You may need to pay a platform to host your project or set up your own hosting environment and then build a website around your map. Luckily GitHub has a service that can generate a website quickly and easily called GitHub Pages.

[GitHub Pages](http://pages.github.com/) is a free static web hosting service available as part of every GitHub repository. It uses the static website generator [Jekyll](https://jekyllrb.com/) to iterate over over a series of configuration files, content files (mostly written in [Markdown](https://www.markdownguide.org/)), layout and feature templates (mostly written in HTML), and data files to create a website.

### Step 1: Launch your GitHub Pages Site

1. If you would like your site to be accessible on the web, navigate to your remote repository for your project on GitHub.
2. On your repository homepage, click the `Settings` tab in the top right and then click `Pages` in the left side menu.
3. Under Source leave the dropdown option as `deploy from a branch`.
4. Use the dropdown to change from `none` to `main` (leave the folder option as `/root`). Then click the `Save` button. It will take a few minutes for your site to go live. You will see a message that your site is currently being built.
5. After waiting a bit, refresh the page. If the build is successful, an alert will appear providing the URL to your live site. The URL will follow the pattern: `https://username.github.io/repository-name`.
6. At this point, we will not have a viewable site because we have not created a homepage.

### Step 2: Create index.md File

1. In the left navigation in VS Code, click `+ file` icon to create a new file.
2. Name the file `index.md`. When Github Pages and therefore Jekyll generates our site, it will look for an index.md file to generate as an index.html file, which will be our homepage.

### Step 3: Add Content to Your Homepage

Since this is a webpage, we want some explanatory text to help our visitors. Add the following text to your index.md file:

```
# Project Title

This is a map prototype I built in Digital Scholarship Foundations Fall 2025
```

### Step 4: Add iframe Code

An iframe is an embedding element in HTML. It is used to add code from elsewhere and embed the result on your page. It is signified with the `<iframe></iframe>` element. Ours will include the following attributes:

- `src`: URL source of the page or file you wish to embed.
- `height`: Sets height of frame in CSS pixels.
- `width`: Sets width of frame in CSS pixels.

1. Skip a line after your last line of text.
2. Add the code below to your new line:

    ```
    <iframe src="my-map.html" height="500" width="750"></iframe>
    ```
3. This code will tell the browser to insert a frame on the page. Then to look for the my-map.html file and insert it within that frame. Finally it will set the height and width of the frame at our parameters.

### Step 5: Test Your Code

1. Save your markdown file.
2. Open the command pallette of VS Code with `cmd` + `shift` + `p`.
3. Type "Live Server" in the command pallette and select `Live Server: Open With Live Server`.
4. This should open your default browser and display your homepage with your text and the map. If this does not happen review your code to see if it is broken anywhere. You may need to check your `index.md` and your `my-map.html`.

### Step 6: Commit and Push Changes

1. If you made any changes. Save again.
2. Stage your commit using source control in VS Code. (If you are only using GitHub Desktop, you can skip staging as GitHub Desktop automatically stages your commits)
3. Write a commit message and then commit changes.
4. Sync/Push those changes to your GitHub remote repository.

### Step 7: Preview Your Live Site

1. Use GitHub Desktop or your browser to navigate to your GitHub remote repository. If you are using GitHub Desktop to navigate, click `view on GitHub` in the main window. If you do not see that option, you still need to commit and/or push your changes.
2. Once on your remote repository homepage, you should see your most recent commit message and a brown dot next to your message. This signifies that GitHub is processing your changes and building your website. Anytime you commit changes to your remote repository, GitHub has to rebuild your site. Your site is built once the brown dot changes to a green check.
3. While you wait, go to the gear icon next to `About` towards the right of the page. If you click the gear icon, it will create a settings popup for your repository homepage.
4. Find the URL box and beneath it, click `Use your GitHub Pages website`.
5. Then click the `save changes` green button at the bottom of the popup.
6. Your website URL should now appear in the `About` section. Click the link to see your live website.

#### Congrats! You now have a working website to show off your cool new map!
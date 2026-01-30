---
section: Workshop Sessions
nav_order: 3
title: Week 3. Prototyping and Version Control
topics: Version control; mapping tools; spatial stories
---

## Learning Objectives

- Continue data wrangling to prepare for mapping
- Identify crosswalks between platforms and data types
- Survey mapping platforms
- Create prototype map
- Learn about version control and GitHub

## Continuing From Last Week

We will review and continue our data wranling process from last week:

- Reading a KML file and identifying data to extract.
- Adding coordinate data to our dataset.
- Using OpenRefine to complete the structuring and standardization of the first iteration of our dataset.

## Surveying Mapping Tools

Selecting a platform for your mapping project requires you to address a range of considerations. Many of the factors we will discuss can be applied to any digital tool or project. They include

- Open-source vs proprietary software: Open-source software is free and lends itself to interoperability (though this is not guaranteed), while proprietary software usually requires you to pay for a license and it may limit how you can use that software's output.
- Skill: You should consider what technical skills you already have, what you are willing (or have the time) to learn, and what skills others on your project team may need to have for you to use a certain tool or method.
- Interactivity: Do you expect others to interact with your data and outputs? Or are static representations of your project acceptable:
- Output: What kind of product do you hope to have after the first iteration of your project? What do you hope to have at the time of publication?

### Mapping Specific Questions to Ask Yourself?

- Is your map for public consumption?
- Is this a static map? Or is it interactive?
- Will the map standalone? Or be part of a website?
- Will the map be put in print?
- Will the map need to be portable?

### Approaching Mapping Platforms

Each platform has its own requirements and limitations. You should always review documentation before experimenting with a tool. Again, these considerations can apply to other tools and projects:

- What are the file requirements for the platform?
- Do you need to change your data structure?
- Do you need to add anything to your dataset?

## Using Palladio to Iterate and Prototype

[Palladio](https://hdlab.stanford.edu/palladio/) is a suite of visualization and analysis tools designed by scholars to ask and answer research questions. We will utilize its mapping feature and in that process learn about specific file and data requirements, how to navigate documentation, and how iteration and prototyping resembles the drafting process of writing.

### Step 1: Identifying Requirements with Documentation

Palladio uses a [help page](https://hdlab.stanford.edu/palladio/help/) as its documentation. While less dense than other documentation you may encounter and structured more like an FAQ, it is still good practice to review any documentation before beginning to work with a tool. Palladio's identify a few parameters we should consider:

- Encourage the use of .csv files (great because so does DiScho!) for you data file type.
- Delimiters (how you separate values) can only be commas, semicolons, or tabs.
- Data files must have headers before importing the file.
- Coordinates (latitude and longitude) must be contained within one column and separated by a column. This is why we used OpenRefine early to programmatically combine our latitude and longitude values into one cell in a new column labeled "Coordinates".

If your data does not meet all of the requirements, you should conform as needed. If you cannot alter your data to meet these requirements, then you will need to search for a new tool!

### Step 2: Load Data

1. Download our [completed dataset](https://drive.google.com/file/d/15Pkkc98hWyVEIws0idDW9jlQMqIJE9qN/view?usp=sharing) with the required "Coordinates" column.
2. Drag and drop your .csv file into the Palladio window. Palladio also provides two other options: Copy and paste your data directly from your spreadsheet or enter a URL that points to your data or repository.

### Step 3: Verify Data

Any categories/column headers with a red dot must be verified or validated. Palladio is flagging these values because it wants to make sure it is reading your data properly. Often, Palladio is checking to see if a special character or a common delimiter should be read as it appears or as a delimiter. To verify:

1. Select category
2. Confirm that characters on right are special characters and not delimiters. This helps Palladio identify if there are multiple values in one cell.
3. After completing the review for each row with a red dot, confirm that Palladio is properly reading your coordinates. Your coordinates column should have the data type set as ‘Latlong.’ If your coordinates are not listed as the correct data type, select the category name and then find the data type drop down menu. In this window, the correct data type will be ‘coordinates.’

### Step 4: Create a Vector Data Layer

1. Select ‘map’ in the navigation bar.
2. If the map layers window does not pop up automatically, click the three horizontal bars in the upper right corner of the map.
3. Within the popup window, select `New layer`.

### Step 5: Customize Your Map

1.	Data tab
- Name: Create a recognizable layer name.
- Map type: 
    - Select ‘points’ if you are not relating points to each other.
    - Select ‘point to point’ if you would like to connect points with lines. This will require you to select source and target destinations to properly relate points like a network visualization. 
- Places: Select the name of your coordinates column.
- Tooltip label: Select the column name that is human readable and adequately labels your data point on the map.
- Color: Change the color of your points.
- Size points: Select if you have another column that denotes frequency or another value that will allow Palladio to alter the size of your points based on occurrence/frequency.

2.	Tiles tab
- Select a tile for your basemap tile.
- Palladio provides 5 choices and also allows for you to add a custom map tile.
- Use Tiles scheme to add your base map.

3.	Shapes tab
- If you have corresponding geoJSON data, you can add circles and other shapes to draw attention to points on your map.

### Step 6: Edit/Revise Map

- If you have an issue with your initial layer, select the blue pencil to the right of your layer title to revise further.
- You can also hide your layer by selecting the eye.
- For more advanced mapping: You can add new layers if you have additional data or want to represent certain attributes of your data.

### Step 7: Share Map
There are two options for sharing your map:
1. Take screen shots to extract a static map.
2. Export .svg file
    - Select ‘Export’ under ‘Data/Shapes’ bar in ‘Map layers’ pop-up window.
    - .svg files will only contain the points, lines, and shapes, not the basemap layer.

## Version Control: GitHub

GitHub is a popular version control platform that will allow us to more effectively share materials and collaborate. It is also a great way for digital scholarship practitioners to use code templates and accurately source where their code originated. But first, some definitions:

[Git](https://git-scm.com/) is a popular free, distributed version control system–i.e. a piece of software used to track the history of changes in a folder of files. Git can be used on your personal computer, or by online services to track the development of a project.

[GitHub](https://github.com/), a popular web platform for hosting Git repositories–i.e. a place to store and sync your project files online. Think of it as Google Drive for code with super robust "track changes" baked in. Built around the powerful version control of Git, it provides a handy web interface for managing, editing, and collaborating on repositories.

### Some GitHub Key Terms

Infrastructure:

- Repository: A collection of folders and files.
- Branch: A parallel version of a repository. Allows for editing and experimentation without effecting the main branch or your project site.
- Main: The default branch that will store the source code that generates your site.
- readme: A file to provide information to the visitors of the repository such as who made it, what it does, and other basic information.

Actions:
- Clone: Copy your project to your very own computer.
- Fork: Copy another user's repository to your account.
- Commit: A Snapshot of your repository. The git equivalent of saving.

## Using GitHub

The workflow below has been adapted from [Learn Static's Introduction to GitHub](https://github.com/learn-static/foundations-0-github) and [Evan Will's go-go gh-pages](https://evanwill.github.io/go-go-ghpages-b/).

### Step 1: Create a GitHub account

1. Open [GitHub](https://github.com) in a new tab.
2. Click the "Sign up" button.
3. Enter your email and create a username and password to complete the sign up process.

### Step 2: Fork a Repository

1. Visit the [dsf-f25-maps](https://github.com/PULdischo/dsf-f25-maps) repository. It uses the ["leaflet maps with csv" template](https://handsondataviz.org/leaflet-maps-with-csv.html) from the online version of [Hands-On Data Visualization](https://handsondataviz.org/) by Jack Dougherty and Ilya Ilyankou.
2. Click the green `Use this yemplate` button (appears on the right side above the code area). This is also known as forking the repository.
3. This brings you to a "Create a new repository" form. Follow these steps:
    1. In the **Repository name** text box, give your repository a name. Be sure to use a lowercase name without spaces or odd characters. Dashes (`-`) or underscores (`_`) are okay. If you are not sure what to name your repository, use the following: `dsf-maps`.
    2. In the **Description** text box, give a tagline or add `a map prototype`.
    3. Select the option for "**Public**" repository. You can select "**Private**" if you prefer, but you will be unable to generate a GitHub Pages site via GitHub and therefore you will only be able to view your site locally.
    4. Leave the "Include all branches" option **Unchecked**!
    5. Click on the green button "**Create repository from template**". This will take you to your new repository.

### Step 3: Explore the interface and repository

1. Explore your repository:
    - gray bar: most recent activity; commit history
    - repo list: files and folders, looks like directory
    - readme preview
    - about: click and describe this repository

2. Explore navigation bar:
    - code: brings us back to main repo page
    - issues/pull requests/etc.: more advanced
    - settings: modify repo, initiate github pages

### Step 4: Edit README file

1. Click on the `README.md` link. This will open your README file.

    The README file is a place to describe your repository.
    By default, GitHub displays the README on the repository home page, so it is often the first place visitors will look for information about your project.

2. In the top right corner of the README file, locate and click on the pencil icon.

    You are now in GitHub's editing mode.

3. Delete this line of text and instead type `# My Project`.
4. Add text below your title to describe your project. For example, you can add `A place to learn digital mapping`

### Step 5: Make a Commit

When you make a commit, Git takes a snapshot of the changes you made and permanently stores it in your repository's history.
Your "commit message" is a short description of what the changes do or why you made them--this is a required note to your future self and your collaborators to help everyone understand the code and history.

1. To commit the changes you just made to your README file, scroll to the bottom of the page where you made your README edits. You'll see a box titled "Commit changes."
2. In the text box directly underneath "Commit changes," type `update project title`, or a brief message of your choosing that indicates what changes you made to this file.
3. Skip the option to add an extended description to the commit, and keep the box checked next to "Commit directly to the main branch". (Note that you can add an extended description of your changes if you need to, but usually a brief commit message will work just fine).
4. Click on the green "Commit changes" button. This will save your changes and take you back to your repository's home page.
5. Scroll down to the bottom of your repository to view the new title you added to the README file.

You can view recent commits on your repository's home page.
Commit messages and their timestamps are located to the right of the repository files.

### Step 6: View the Changes

Let's take a closer look at the changes you've made to the README file:

1. On your repository's home page, scroll back up and locate the README.md file link. To the right of the link, you should see the commit message you just created (it should say `update project title`).
2. Click on this commit message (*not* on the filename).

    When you click the commit message, GitHub will show you the changes made and the files edited during that commit. 
    Deletions will display in red while additions to a file will display in green. 

3. Click your repository's name (located in the top left of the window) to return to the repository's home page.

## Remote to Local

While GitHub's interface allows for editing, developing, and launching a website, working locally will help you work effectively and efficiently. This section will introduce you to the concept of remote and local repositories through the use of GitHub Desktop.

### Step 1: Install GitHub Desktop

1. Navigate to [GitHub Desktop](https://github.com/apps/desktop) and download the appropriate version of GitHub Desktop for your operating system. 
2. Follow the prompts to complete the installation. For more information, see [Installing GitHub Desktop](https://docs.github.com/en/desktop/installing-and-authenticating-to-github-desktop/setting-up-github-desktop).
    1. Sign in to your Github.com account via the GitHub Desktop prompt.
    2. Select `authorize` after reviewing access prompt.
    3. When viewing `configure git` prompt, select `use my GitHub account name and email address`.
    4. Click `finish`
3. Arrive at `Let's get started.` prompt.

### Step 2: Configure a Default Text Editor

1. In the menu bar, select `GitHub Desktop`, then click `Settings`.
2. In the Settings window, select `Integrations`.
3. Under "External Editor", use the dropdown menu to select Visual Studio Code t to set as your default text editor.
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

## Next Session

If you had difficulty using GitHub Desktop or completing your integration, review and complete the following:

- [Authenticating GitHub in GitHub Desktop](https://docs.github.com/en/desktop/installing-and-authenticating-to-github-desktop/authenticating-to-github-in-github-desktop)
- [Configure a default editor in GitHub Desktop](https://docs.github.com/en/desktop/configuring-and-customizing-github-desktop/configuring-a-default-editor-in-github-desktop#configuring-a-default-editor)

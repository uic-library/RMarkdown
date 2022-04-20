---
layout: page
title: Customizing Your Workshop's Website
permalink: /customization/index.html
---

## Table of Content

* TOC
{:toc}

## Introduction

The following instructions walk through the set up steps to create a new workshop for the Digital Scholarship Hub using GitHub Pages. This workshop template is most appropriate for workshops teaching coding as the template contains styling elements for different coding languages including R, Python, BASH, SQL etc. 

### Necessary Tools

#### GitHub Account

You need to have a GitHub account. Create a GitHub account at [github.com](github.com). Send an email to lib-sys@uic.edu to be added to the `uic-library` organization and the `hub2` team. 

#### Git installation on local computer

There are several editing options explained further in the `How to edit GitHub Pages` section. Mac computers will already have git installed by default. Windows users should install `Git for Windows` if they want to work on their local computer. 

## Basics of GitHub Pages

It's recommended to review the following for working in GitHub Pages:

* Version Control with Git
* Using GitHub 
* Markdown
* Relative paths
* More on GitHub Pages (if you're curious)

## How to edit GitHub Pages

There are two ways of customizing your website. You can either:

- edit the files directly in GitHub using your web browser
- clone the repository on your computer and update the files locally

### Updating the files on GitHub in your web browser

1.  Go into your newly-created repository, ensure you are on the gh-pages branch by clicking on the branch under the drop
    down in the menu bar (see the note below):

    ![screenshot of this repository's GitHub page showing the "Branch" dropdown menu expanded with the "gh-pages" branch selected](../fig/select-gh-pages-branch.png?raw=true)
2. Use the pencil icon to go into editing mode and make your edits:
    ![screenshot showing the edit icon in GitHub Pages](../fig/edit-index-file-menu-bar.png)

\*Note working on your workshop online is prone to losing edits due to internet outages. Either save very frequently, or edit locally.

### Working locally

#### Command Line

If you are already familiar with Git, you can clone the repository to your desktop, edit your workshop locally, and push your changes back to the repository.

```shell
git clone https://github.com/uic-library/workshop-repo-name/
```

In order to view your changes once you are done editing, if you have bundler installed (see the
[installation instructions](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll), you can preview your site locally with:

```shell
make serve
```
for Macs or 

```shell
bundle exec jekyll serve
```
for Windows

and go to <http://localhost:4000> to preview your site.

If there are any issues with the edits you made, you will get an error message from jekyll. [See common jekyll error messages here](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/troubleshooting-jekyll-build-errors-for-github-pages-sites#file-does-not-exist-in-includes-directory) to help with troubleshooting.  

Once you are satisfied with the edits to your site, commit and push the changes to your repository.
A few minutes later, you can go to the GitHub Pages URL for your workshop site and view it. 

#### GitHub Desktop App

Alternatively, you can [download and install the GitHub Desktop application](https://desktop.github.com/), though you won't be able to preview edits as you would with the command line. 

\* Highly recommend becoming comfortable using Git in command line at least for adding, commiting, previewing, and pushing changes. It can take a long time for a push to load on GitHub oneline and to be able to see the change to the website.  


## GitHub Pages Workshop Website Setup

### Using the workshop template

1.  Log in to GitHub.
    You must be logged in for the remaining steps to work.

2.  On this page (<https://github.com/uic-library/workshop-template>),
    click on the green "Use this template" button (top right). **Please _do not fork this repository directly on GitHub._**

3.  Choose UIC Libray as the owner for the repository UNLESS you are just
    practicing or practicing with the repository (Only Admins can delete       repository's in the UIC Library's organization)

4. Always edit or merge edits into the `gh-pages` branch. This is the branch 
   that will be rendered as a live website

### Repository Configurations

GitHub Pages sites are formatted as `https://GITHUB_USERNAME.github.io/REPOSITORY_NAME`.
For example, if the URL for your repository is `https://github.com/uic-library/Introduction-Digital-Scholarship`,
the URL for its website will be `http://uic-library.github.io/Introduction-Digital-Scholarship`.

* [ ] Set the site url: Your new website will be rendered at `https://uic-library.github.io/<workshop-repo-name>`. *To set the URL on GitHub, click the gear wheel button next to About on the right of the repository landing page. You will have to manually enter the url even though a repository at https://github.com/uic-library/workshop-repo-name/ will render automatically at the URL https://uic-library.github.io/<workshop-repo-name>.
* [ ] Add a description of the workshop
* [ ] [Add relevant topic tags to your lesson repository][cdh-topic-tags].

FIXME add image of this section

### Sharing & Visibility for Hub team

share with hub2 and whoever is administrator

### Make the Website Public

Make GitHub Pages Public
Make sure url is set according to above instructions
Go into settings > Pages > and choose "Public"

until then, will render at random url

Error - you may get a 404 error when you go to the site after setting it as public. That is an issue with your browser cache, will resolve within a few days. Force reset of browser cache OR open in incognito window. 

### Files to edit to build workshop website

FIXME add picture of the files to edit


## Configuration File `_config.yml`

You should edit the `_config.yml` configuration file in the root directory of your workshop to
configure some site-wide variables and make the site function correctly:

* `title` - overall title for the workshop. If set (i.e., different from "Workshop Title" or empty),
  it will appear in the "jumbotron" (the gray box at the top of the page). This variable is also
  used for the title of the extra pages. The README contains [more information about extra pages](https://github.com/carpentries/workshop-template#creating-extra-pages).

* `life-cycle` - The current development state of the workshop. 
 Possible values: "pre-alpha", "alpha", "beta", "stable"
 "pre-alpha" for the beginning stages of designing a workshop
 "alpha" after content has been added, but needs to be reviewed or tested 
 "beta" ready to teach for the first time, editing stage after first taught
 "stable" workshop has been taught and modifications made if necessary, little
 to no editing required at this stage.

You should not need to modify any of the other variable values in `_config.yml`.

## Home Page (`index.md`)

Your workshop's home page lives in `index.md`,
which must define the values below in its header.

* [ ] add a description to the home page

* [ ] add the workshop goals to the home page

* [ ] List the pre-requisites on the home page. either workshops that students  should attend first, or concepts they should know before attending.

* [ ] add the workshop recording by navigating to where it's located in Box, copy the ID from the video sharelink (see image below) and paste into the BoxId field in the yaml in index.md
![Copy ID from Box Share Link for Recordings](fig/sharelink-boxId.PNG)
  * Alternatively, if there is no recording ready to post, comment out the recording section with `{% comment %}` and `{% endcomment %}` until there is a recording to add.

* [ ] update the survey link each semester. Check to make sure the correct survey is linked

* [ ] add related workshops to "Next up" section. Link related workshops that students can take next with a link []():
i.e. [Next Workshop](https://uic-library.github.io/next-workshop)

*Note workshop content will display automatically from the titles of the workshop pages, estimated times, and objectives.

## Setup Page (`setup.md`)

* [ ] add installation instructions

1. If you need to add tools:

 If you need to add installation instructions for other tools,
 you can use the `{% raw %}{% include %}{% endraw %}` statements for the tools located in `_includes/install_instructions/` folder. in the format:

 `{% raw %}{% include install_instructions/<install-file-name.html>%}{% endraw %}`

 If you need to add installation instructions for tools that do not currently have installation instructions, you will need to write your own in html in the `install_instructions` folder. You can use installation instructions
 for other tools located in the `_includes/install_instructions/` folder
 as examples.

2.  If you need to remove tools:

 If you need to remove any of the instructions for the default set of tools,
 you can delete lines that include these instructions in
 the `setup.md` file.

 for example, delete:

 `{% raw %}{% include install_instructions/r.html%}{% endraw %}`

* [ ] link data files, script files, or other supporting documentation

* [ ] if applicable, add a description of the data being used in the workshop so that students have context of what you will be teaching with.

## Workshop Content Pages `_episodes/`

* [ ] make copies to match the number of parts your workshop will have by creating
  copies of `\_episodes/01-introduction.md`. Files should be named according to 
  convention: `0X-short-title.md`.
* [ ] add content to "episode" pages, and style with markdown (see [Carpentries Lesson Example](https://carpentries.github.io/lesson-example/) for styling this template
* [ ] add images for your workshop content to the `fig` folder. Good convention
  is naming each image according to the episode file it's located in `0X-short-description.png`
    \*Note: you can use png and jpeg files, but they are case sensitive, so if your file is .PNG 
    make sure to use .PNG in the markdown image link. 
* [ ] add other workshop files to the `files` folder (i.e. data files, script files) \*large data files will need to be zipped or linked to outside source, file size limit is 25 MB.

## Images `_fig/`

* [ ] add images for your workshop content to the `fig` folder. Good convention
  is naming each image according to the episode file it's located in `0X-short-description.png`
    \*Note: you can use png and jpeg files, but they are case sensitive, so if your file is .PNG 
    make sure to use .PNG in the markdown image link. 

## Files `files/`

* [ ] add other workshop files to the `files` folder (i.e. data files, script files) \*large data files will need to be zipped or linked to outside source, file size limit is 25 MB. 

## Additional Resources `more-resources.md`

## References `reference.md`

## Troubleshooting -- FIXME if transferring to UIC Library gets messed up

If for some reason,
such as the installation instructions having become disconnected
with the current lesson material,
you need to get changes from this repository
into the clone of it with your workshop page,
please follow the steps bellow:

1. Add the workshop-template repository as upstream:
    ~~~
    $ git remote add upstream https://github.com/carpentries/workshop-template.git
    ~~~
    {: .language-bash}

2. Fetch the data from upstream repository (also know as the workshop-template
    repository):
    ~~~
    $ git pull upstream
    ~~~
    {: .language-bash}

3. Address possible merge conflicts, and
    ~~~
    $ git commit -a
    ~~~
    {: .language-bash}

4. Push the changes to your repository on GitHub:
    ~~~
    $ git push origin gh-pages
    ~~~
    {: .language-bash}




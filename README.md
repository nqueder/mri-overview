# Neurohackademy 2020 MRI Overview Project

Welcome to the mri overview in flowcharts project. Our goal: Bring newcomers together (maybe with some experienced coders!) to develop some flowcharts and/or overview materials that will increase our understanding of the start-to-finish MRI/fMRI/DTI analysis process by collaborating on interactive flowcharts, which we hope can be shared more broadly to help others similarly understand how these processes flow at a macro level. 


## Project Files
* [The site](https://mri-overview.github.io/mri-overview/) is now availible on github pages! 
* [The content compilation](https://docs.google.com/document/d/1d2YIGNcBgyLPSA3bIh_4ykLT1ixNjU6LHuPns6krSRg/edit#) is the original and more extensive collection of resources. If you want to add new content, please instead edit the [streamlined content for flowchart intergration](https://docs.google.com/spreadsheets/d/1OS48G1jEBcArDIN76jh5PFHGoJSeqfGSTE23ve7lfjk/edit?usp=sharing)
* [The HackMD Page](https://hackmd.io/GtFGl3pWTe6kymhDzASpZQ?both) contains most of our oringal set up in MD format.
* [Jitsi Room]( https://meet.jit.si/Hello-mri-overview) for quick and easy project meetings. 
* [The Vocab Sheet](https://docs.google.com/spreadsheets/d/1U3Qi4Ns4POn9R8m0SEua6zU0cO5jjseMq3WrctPEtyo/edit?usp=sharing) of MRI terms! 
* [The Streamlined Content for Flowchart](https://docs.google.com/spreadsheets/d/1OS48G1jEBcArDIN76jh5PFHGoJSeqfGSTE23ve7lfjk/edit?usp=sharing) is what will actually be populated into the website.
* Content editing tutorial is located below.
* List of tasks as well as what has been completed can be found in the [projects page](https://github.com/MRI-Overview/mri-overview/projects/1)


## Core Project Team:
* [Annalysa Lovos](https://github.com/annalysa)
* [Nazek Queder](https://github.com/nqueder)
* [Stepheni Uh](https://github.com/stephuh2)
* [Allison Londeree](https://github.com/londeree4)
* [Amelia Miramonti](https://github.com/amelia-m)
* [Jinyi Hung](https://github.com/jinyihung)
* [Tuba Sahin](https://github.com/tubapona)
* [Hulya Aldemir](https://github.com/hulyaald)
* [Dara Ghahremani](https://github.com/daraucla)
* [Neha Sara John](https://github.com/NSJohn)
* [Ginnie Kim](https://github.com/ginniekim)

## How to Edit this Site!

### Prerequisites
- Have a [Github account](https://github.com/join) 
- Get added as a member to the [MRI Overview Github Organization](https://github.com/MRI-Overview) - feel free to just email any member of this project team.
- Install [Git](https://git-scm.com/downloads) 
- Install [RStudio](https://rstudio.com/products/rstudio/download/) installed
    - Required packages can be installed by running the first code chunk (commented out by default - more on this below)


### Cloning the Repository
Once you have these things installed open RStudio.
    - If you already opened RStudio you will need to restart it.
    
Under "File" Select New Project. From the create project window select "Version Control" then "Git" 

On the Clone Git Repository window, input:
- repository URL as https://github.com/MRI-Overview/mri-overview 
- Project directory name as mri-overview (may auto-populate)
- And enter the sub directory as wherever you would like things on your computer

Congratulations!  You have sucessfully cloned the repository! 
You can open this project again by opening the `mri-overview.Rproj` file in the future.

### Examining the File Structure

Welcome to the local directory - you can view all of the site files in the "Files" pane of Rstudio!

There's really only two files you might want to edit: `index.Rmd` and `README.md`. Most of the other files are generated by R and some are not human readable -unless you have your HTML goggles on. 

The `README.md` is displayed on the GitHub repository page, but doesn't show up on the [site](https://mri-overview.github.io/mri-overview/).

The `index.rmd` is the only page on the website! If you want to add additional pages or make changes the site theme, you can edit the `_site.yml` file. Everything in this file is be written in Markdown, HTML, or R script, but you probably won't need to edit any of the HTML (in the index file).

Flowchart and vocab sections are pulling information from the following Google docs:
- [Flowchart](https://docs.google.com/spreadsheets/d/1OS48G1jEBcArDIN76jh5PFHGoJSeqfGSTE23ve7lfjk/edit?usp=sharing)
- [Vocab](https://docs.google.com/spreadsheets/d/1U3Qi4Ns4POn9R8m0SEua6zU0cO5jjseMq3WrctPEtyo/edit?usp=slack&ts=5f24816f)

### Updating the site with a change made to the Google doc (without editing the site code)

There are really only two steps to this:
1. Rendering the site
2. Getting the new version of the site onto GitHub

**Rendering the site**

To render the site you will need to go to the console tab of RStudio and type in `rmarkdown::render_site()`
What this does is re-run all of the code in the site, and generate the site output in HTML in the "docs" directory which is where the site is accessed by GitHub Pages. This will pull the most current version of the Google docs and update all flowcharts and tables that rely on it! 

If you are doing this for the first time, you may need to install some packages to get the code to run.  To do this you can either uncomment and run the following line in the first codechunk in the index.Rmd file `install.packages("dplyr","collapsibleTree","gsheet","DT","readr","prettydoc")
`
OR sometimes there is a banner at the top of the gui that will allow you to install packages. Which ever you prefer! 

**Communicating with Github**

Next, we need to get this new beautiful version onto GitHub! Switch over to the terminal tab in RStudio

To make sure git is working type `git status` This should yield some information about what changes have been made, and if you need to `pull` a more recent repo. If you are a version behind, use `git pull` to get up to date. It's a good idea to do this any time you want to make a change. 

Use `git add .` to add all of the changes made to the commit queue.
 

Commit message should describe the changes made, e.g., "rendering site with updated Google doc content"
`git commit -m "[your commit message]"`

Finally we want to push our most recent version onto GitHub with the new commits we just made using  `git push`. The first time you do this you may be prompted to sign into github. This may take a minute to update. 

Once you have pushed, you can check the project repository to see your new commit! You can also view [the site](https://mri-overview.github.io/mri-overview/) with your new change! 

Woot Woot! You made it!

### To update site including code changes

Say you want to edit the actual structure of the index.Rmd. Please feel free to by following the same steps as above! One additional thing you may want to do before commiting changes to github is just double checking the code by knitting and looking at the HTML to make sure your changes look correct!

A new branch has also been created to help with larger changes.

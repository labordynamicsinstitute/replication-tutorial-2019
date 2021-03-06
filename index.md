Replication and Reproducibility in Social Sciences and Statistics: Overview and Practice
========================================================
author: Lars Vilhuber
date: 2019-10-01
autosize: true
width: 1200

Cornell University





Overview
========================================================

- High-level overview (60:00)
- A very concrete example (remainder)

Replication and Reproducibility in Social Sciences and Statistics: Context, Concerns, and Concrete Measures
========================================================


[![Paris presentation](images/Vilhuber-Presentation2019-Paris-2019-03-28-title.png)](https://github.com/labordynamicsinstitute/replicability-presentation2019/raw/v20190328b/Vilhuber-Presentation2019-Paris-2019-03-28.pdf) ([alt](https://github.com/labordynamicsinstitute/replicability-presentation2019))



[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.2621959.svg)](https://doi.org/10.5281/zenodo.2621959)



Goals of this tutorial
==================

- Goal 1: Identify all the elements of a fully reproducible analysis
- Goal 2: Be able to curate the data and code necessary for reproducible analysis
- Goal 3: Robustness and automation - getting close to push-button reproducibility
- Goal 4: Correctly document reproducible research





Requirements 
============

## Requirements
- web browser
- some R knowledge (not much)

***
## Sub goals
- show you enough of the toolkit to have you explore more
- recognize (some) of the limitations
- NOT make you a master of this today





Let's get started
=================
type: section

Details: Goal 1: Elements of a fully reproducible analysis
===============
Consider the AEA's suggested README and the Social Science Data Editors' guidance for verification:

- [Template README](https://aeadataeditor.github.io/aea-de-guidance/template-README.html)
- [Verification guidance](https://social-science-data-editors.github.io/guidance/Verification_guidance.html)

***

[![Verification guidance](images/Screenshot_2019-04-23 Verification guidance.png)](https://social-science-data-editors.github.io/guidance/Verification_guidance.html)

Details: Goal 1
===============

### Elements

- Data (where possible)
- Data provenance
- Instructions
- Code (always*)
- Expected results
- Persistence


Goal 1: Elements: Data (where possible)
=================

- Old method: send the journal a ZIP file

- Source: Your laptop

- Destination: random file on a journal website

***

Questions/ What-ifs:

-  the data is not on your laptop?
  - too big
  - on server
  - a database
- the data is not yours to send
  - confidentiality
  - proprietary
  - other licensing issues
  
Goal 1: Elements: Data (where possible)
=================

- Old method: send the journal a ZIP file

- **Source: Your laptop**

- Destination: random file on a journal website

***

Questions/ What-ifs:

- how did the data get to your laptop?
- how did the data get generated?

These are **provenance** questions.


Goal 1: Elements: Data (where possible)
=================

- Old method: send the journal a ZIP file

- Source: Your laptop

- **Destination: random file on a journal website**

***

Questions/ What-ifs:

- is the ZIP file complete?
- are the ZIP file contents curated (preserved)?
- can the data be re-used?
- can the data be properly attributed to the creator?
- can the data be found independently of the article?


These are **FAIR** questions

FAIR Data Principles
===================

- **F**indable
- **A**ccessible
- **I**nteroperable
- **R**e-Usable

***

![FAIR Data Principles](images/Screenshot_2019-09-30_The_FAIR_Data_Principles.png)

The Example
===========

The Census Bureau put out a blog post with data.

- I attempted to replicate it
- The replication itself should be replicable
- Focus here: *my replication* of the blog post

***
http://researchmatters.blogs.census.gov/2016/12/01/how-much-do-startups-impact-employment-growth-in-the-u-s/

![original page](images/Selection_463.png)

The Context
===========

the original page: 

[![url](images/url-small.png)](http://researchmatters.blogs.census.gov/2016/12/01/how-much-do-startups-impact-employment-growth-in-the-u-s/)

![original page](images/Selection_463.png)
***
the replication project page: https://larsvilhuber.github.io/jobcreationblog/README.html

![replicated page](images/Screenshot_2019-04-23-Replication_for_how_much.png)

We are going to focus on 1 figure
=================================
Original

![original](images/bds1.jpg)
***
Replicated

![replicated](images/figure1-1.png)

Let's start
===========
type: section

<div style="text-align: center;">
<img src="images/giphy_scan.gif" width="50%" alt="scan" />
</div>



Elements of Goal 1
===============

### Elements

- Data (where possible)
- Data provenance
- Instructions
- Code (always*)
- Expected results
- Persistence

***

### Here:

- Data is small (< 75k) - ✔️
- Data provenance - URL ✔️
- Instructions - RMarkdown file ✔️
- Code - Within Rmd ✔️
- Expected results - Copy of Figure ✔️
- Persistence - Github ✔️


Hold on
===========
type: section




<div style="text-align: center;">
<img src="images/stop-1013732_640.jpg" width="50%" alt="scan" />
</div>

Elements of Goal 1
===============

### Elements

- Data (where possible)
- Data provenance
- Instructions
- Code (always*)
- Expected results
- Persistence

***

### Here:

- Data is small (< 75k) - ✔️
- **Data provenance - URL ??**
- Instructions - RMarkdown file
- Code - Within Rmd
- Expected results - Copy of Figure
- **Persistence - Github ??**



Data provenance
===============
"Data" in this project:
- the blog post
- the underlying data

***
Where available:
- URL
- URL








First problem
=============
incremental: true

the original page: http://researchmatters.blogs.census.gov/2016/12/01/how-much-do-startups-impact-employment-growth-in-the-u-s/

![oops](images/Server_Not_Found.png)



Safeguarding scientific output
==============================
The role of journals is to provide a **permanent record**
of scientific knowledge.

- how reliable is that record?
- where are journals stored?
- what if the information is not in a journal?

***
![old library](images/antique-library-picture-id495747679-730x438.jpg)

Safeguarding scientific output
==============================

- journals disappear, as do websites
- **paper** journals are stored in libraries
- **e-journals** in a system called LOCKSS = *Lots of Copies Keep Stuff Safe*
- **data** should be stored in repositories

***
![stacks](images/Archives-Stacks-1.jpg)

<!-- ![tree in library](images/8520ec257e8022dbf450a989e87b9ccb.jpg) -->

These are still fallible
========================

<div style="text-align: center;">
<img src="images/d814ae2e0c47c399afcd93f6e232fb09.jpg" width="50%" alt="scan" />
</div>


What is NOT safeguarded
=============================
- random URLs
- Github repositories


***
![Github not found](images/Page_not_found_GitHub_Pages.png)




Solving the first snag
======================
We use the [Internet Archive](https://www.archive.org) 

- <small>[http://researchmatters.blogs.](http://researchmatters.blogs.census.gov/2016/12/01/how-much-do-startups-impact-employment-growth-in-the-u-s/)[census.gov/](http://researchmatters.blogs.census.gov/2016/12/01/how-much-do-startups-impact-employment-growth-in-the-u-s/)[2016/12/01/how-much-do-startups-](http://researchmatters.blogs.census.gov/2016/12/01/how-much-do-startups-impact-employment-growth-in-the-u-s/)[impact-employment-growth-](http://researchmatters.blogs.census.gov/2016/12/01/how-much-do-startups-impact-employment-growth-in-the-u-s/)[in-the-u-s/](http://researchmatters.blogs.census.gov/2016/12/01/how-much-do-startups-impact-employment-growth-in-the-u-s/)</small>
![original page](images/Selection_463.png)


Solving the first snag
======================
to archive websites:


- <small>https://web.archive.org/web/20161229210623/http://researchmatters.blogs.census.gov/2016/12/01/how-much-do-startups-impact-employment-growth-in-the-u-s/</small>
![archived page](images/blog_page_internet_archive.png)

Exercise
========
type: alert

- Pick a random website
  - Stephen Fienberg - http://www.stat.cmu.edu/~fienberg/
  - CIQSS - https://www.ciqss.org/a-propos
  - etc.
- Figure out if there is a Web Archive copy of it
  - Useful: [WayBack Machine Firefox Plugin](https://addons.mozilla.org/en-CA/firefox/addon/wayback-machine_new/)
- If not, get the Web Archive (aka WayBack Machine) to create a copy
- Cite the Web Archive version of the page

Do it now
==========
type: section

<div style="text-align: center;">
<img src="images/giphy_scan.gif" width="50%" alt="scan" />
</div>

Result
======

> Goal 2: Be able to curate the data and code necessary for reproducible analysis

<div style="text-align: center;">
<img src="images/partway-768567_640.jpg" width="50%" alt="scan" />
</div>
















Let's start... again
===========
type: section



The replication of the original 
=======================
the [project page](https://larsvilhuber.github.io/jobcreationblog/README.html): 

![replicated page](images/Screenshot_2019-04-23-Replication_for_how_much.png)

***
the code behind it: <small>https://github.com/larsvilhuber/jobcreationblog </small>

![Github](images/Screenshot_2019-04-23_larsvilhuber_jobcreationblog.png)

What is Github?
==============
incremental: true


`git`

Distributed version control system, created by Linus Torvalds in 2005
![branching system](images/branch-per-task.png)

***
Github.com

> At a high level, GitHub is a website and cloud-based service that helps developers store and manage their code, as well as track and control changes to their code.
[[1](https://kinsta.com/knowledgebase/what-is-github/)]

Also a **collaboration tool** when multiple people (developers, researchers) collaborate in a structured fashion on text/code/programs/etc.


Gitlab? Github? Git? What's up with that?
=========================================
type: warning

<img alt="Gitlab logo" width="45%" style="vertical-align: middle;" src="images/gitlab-logo-gray-rgb.png"/>
<img alt="Gitlab logo" width="10%" style="vertical-align: middle;" src="images/GitHub-Mark-120px-plus.png"/>
<img alt="Gitlab logo" width="25%" style="vertical-align: middle;" src="images/GitHub_Logo.png"/>

> Both GitLab (and GitLab.com) and GitHub (and GitHub.com) are products providing Git repository hosting service. [[1](https://www.quora.com/What-are-the-differences-between-GitHub-GitLab)]

***

Also:
- Bitbucket.com (despite no Git in the name)
- All of these have free plans for 
  - private (non-public) repositories
  - public repositories
  
at least for academics.

Training for Git
================

Many training opportunities and tutorials out there

- [my own short training](https://github.com/labordynamicsinstitute/replicability-training/blob/master/Fall%202019/Basics_of_Git.md)
- [10 minute read Git Handbook](https://guides.github.com/introduction/git-handbook/)

What Github, Gitlab, etc. are NOT
=================
incremental: true

While these sites make it really easy to publish your code/website/etc.

***

They are **NOT** archives.
![Github not found](images/Page_not_found_GitHub_Pages.png)

Github etc. are transitory
=============================
incremental: true

Github pages, much as private websites, can be unpublished at any time:

![Github unpublish](images/UnpublishingGitHubHelp.png)

***
In fact, the entire code repository can be deleted at any time:

![Github delete](images/Deleting_a_repositoryGitHubHelp.png)


Git(hub,lab) as a tool for reproducible research
================
> Goal 3: Robustness and automation - getting close to push-button reproducibility

(Advanced features of Git(hub,lab) allows us to implement and test that)

***
> Goal 4: Correctly document reproducible research

- Git(hub,lab) allow us to freeze consistent versions of input data, code, and output as "*releases*", "versions", etc., thus making it easy to **document your code** 

Git(hub,lab) as a tool for reproducible research
================
> Goal 3: Robustness and automation - getting close to push-button reproducibility

(Advanced features of Git(hub,lab) allows us to implement and test that)

***
> Goal 4: Correctly document reproducible research


- (also respond to thesis advisor, referree, editor, curious journalist asking the question "what has changed") 

![changes](images/releases-github.png)
















Getting our hands dirty
=======================
Rather than squint on code on the screen, let's ... replicate my replication. Online. Now.

We will

- Make a copy of the code repository
- Verify that the original code runs, and make any changes necessary
- Make a (permanent) copy of the code
- Address any issues on the way

***
Requirements:
- Rstudio.cloud account (alt: Google, Github)
- Git*** account
  - alt Gitlab: Google/ Twitter/ Github / Bitbucket
  - alt Github: none
- Zenodo account (alt: Github, ORCID)

You can delete all online materials at the end of the class.

Getting our hands dirty
=======================
Rather than squint on code on the screen, let's ... replicate my replication. Online. Now.

- Go to <a href="https://rstudio.cloud" target="_blank">https://rstudio.cloud</a>

***
<a href="https://rstudio.cloud" target="_blank"><img alt="Rstudio.cloud" src="images/Screenshot_2019-04-23_RStudio_Cloud.png" /></a>





First task: Make a copy
=====================

Source: <small>https://github.com/larsvilhuber/jobcreationblog </small>

![Github](images/Screenshot_2019-04-23_larsvilhuber_jobcreationblog.png)

***

Destination: 

<a href="https://gitlab.com"><img alt="Gitlab logo" width="45%" style="vertical-align: middle;" src="images/gitlab-logo-gray-rgb.png"/>
<img alt="Gitlab logo" width="10%" style="vertical-align: middle;" src="images/GitHub-Mark-120px-plus.png"/></a>
<a href="https://github.com"><img alt="Gitlab logo" width="25%" style="vertical-align: middle;" src="images/GitHub_Logo.png"/></a>


Using Gitlab: Two options
=========================
incremental: true

**Import** project from Git

![gitlab import project](images/gitlab-import-project.png)

***

**Fork** an existing Gitlab project: 

**GITLAB**<small>.com/larsvilhuber/jobcreationblog </small>

![gitlab fork project](images/gitlab-fork-project.png)


Your own Gitlab "jobcreationblog" repo
=====================================
incremental: true

> Goal 2: Be able to curate the data and code necessary for reproducible analysis

<div style="text-align: center;">
<img src="images/giphy_success.gif" width="60%" alt="scan" />
</div>

Next step: Rstudio.cloud
============
type: alert



<div style="text-align: center;">
<img alt="Rstudio.cloud" src="images/Screenshot_2019-04-23_RStudio_Cloud.png" width="60%"/>
</div>



Logging on to the Rstudio.cloud server
=======================
incremental: true

![Rstudio.cloud login](images/Screenshot_2019-04-23_RStudio_Cloud_2.png)

***

![Rstudio.cloud workspace](images/Screenshot_2019-04-23_RStudio_Cloud_3.png)


While you do that
=================
Other cloud-based compute environments:

## [Rstudio.cloud](https://rstudio.cloud)
  - R-focused
  
## [MyBinder.org](https://mybinder.org)
  - Origins with Jupyter
  - Julia, Python, and R
  - different approach
  
***

## https://codeocean.com
  - Software-agnostic
    - R
    - Python
    - Stata !
    - Matlab !
    - others
  - but always scripted
  - integrated versioning of the entire compute capsule

Creating a new project
=======================
incremental: true

![Rstudio.cloud workspace](images/Screenshot_2019-04-23_RStudio_Cloud_3.png)
***
![Rstudio.cloud new project](images/Screenshot_2019-04-23_RStudio_Cloud_4.png)


![Rstudio.cloud new project from Github](images/Screenshot_2019-04-23_RStudio_Cloud_5.png)

Creating a new project from Gitlab
==================================

## https://gitlab.com/larsvilhuber/jobcreationblog 

![Github](images/Screenshot_2019-04-23_larsvilhuber_jobcreationblog.png)

(replace "**larsvilhuber**" with your own Gitlab name space, or your Github clone URL)

![Gitlab clone button](images/gitlab-clone-project.png)

***
![Rstudio.cloud new project from Gitlab](images/Screenshot_2019-04-23_RStudio_Cloud_7.png)


Creating a new project from Gitlab
==================================

<div style="text-align: center;">
<img src="images/RStudio_Cloud_457.png" width="80%" alt="scan" />
</div>

Creating a new project from Gitlab
==================================

<div style="text-align: center;">
<img src="images/RStudio_Cloud_458.png" width="80%" alt="scan" />
</div>

Notes 
=====
## You could have done the same thing on your laptop
  - you might not have (the same version of) **[Rstudio](https://www.rstudio.com)** installed (free)
  - you might not have (the same version of) **[R](https://www.r-project.org/)** installed (free)
  - you might have a Mac/ Windows/ **Linux**/ old / brand new machine
  
***
## All of these are issues affecting computational reproducibility

However, they do not solve everything...

Open the README document
========================

<div style="text-align: center;">
<img src="images/RStudio_Cloud_459.png" width="60%" alt="scan" />
</div>

A (solved) problem of dependencies
==================================

<div style="text-align: center;">
<img src="images/RStudio_Cloud_460.png" width="80%" alt="scan" />
</div>

Issues of dependencies (new)
=======================

## You could have done the same thing on your laptop
  - you might not have (the same version of) **[Rstudio](https://www.rstudio.com)** installed (free)
  - you might not have (the same version of) **[R](https://www.r-project.org/)** installed (free)
  - you might have a Mac/ Windows/ **Linux**/ old / brand new machine
  - <span style="color: red;">you might not have (the same version of) **packages** installed</span>

Rstudio solves that for you
==================================

<div style="text-align: center;">
<h2>Go ahead, click on "install"</h2>
<img src="images/RStudio_Cloud_460.png" width="80%" alt="scan" />
</div>

Solving dependencies
====================
The problem is not just in R:
- SSC or Stata Journal packages in Stata
- libraries or compilers in Fortran
- Modules (paid!) in SPSS or SAS
- packages in Python (and versions of Python!)

***
[![XKCD 1987](images/xkcd-dependency-hell.png)](https://xkcd.com/1987/)

Solving dependencies (R)
====================

- use `packrat` or `checkpoint` functionality
- declare dependencies explicitly [[1](https://gist.github.com/larsvilhuber/85026976027b58714c00420d75f04281)]
<small>

```r
####################################
# global libraries used everywhere #
####################################
# Package lock in - optional
MRAN.snapshot <- "2019-01-01"
options(repos = c(CRAN = paste0("https://mran.revolutionanalytics.com/snapshot/",MRAN.snapshot)))
pkgTest <- function(x)
{
        if (!require(x,character.only = TRUE))
        {
                install.packages(x,dep=TRUE)
                if(!require(x,character.only = TRUE)) stop("Package not found")
        }
        return("OK")
}
global.libraries <- c("dplyr","devtools","rprojroot","tictoc")
results <- sapply(as.list(global.libraries), pkgTest)
```
</small>

Solving dependencies (Stata)
===========================
- install packages locally [[1](https://gist.github.com/larsvilhuber/8ead0ba85119e4085e71ab3062760190)]
- commit as part of the repository
<small>

```stata
// Make a path local to the project
// Also see my related config.do at 
//   https://gist.github.com/larsvilhuber/6bcf4ff820285a1f1b9cfff2c81ca02b

local pwd "/c/path/to/project" 
capture mkdir `pwd'/ado

sysdir set PERSONAL `pwd'/ado/personal
sysdir set PLUS     `pwd'/ado/plus
sysdir set SITE `pwd'/ado/site

/* Now install them */
/*--- SSC packages ---*/
foreach pkg in outreg esttab someprog {
  ssc install `pkg'
}
```
</small>

Result
======
type: alert

> Goal 3: Robustness and automation - getting close to push-button reproducibility

By solving dependencies explicitly, robustness is improved.

By doing so with a dynamic function, automation is possible.

***

> Goal 4: Correctly document reproducible research

Documenting dependencies is a critical part of reproducible research.


Packages installed?
==================
incremental: true

Add text to the document:


```r
# hidden dependency, will install packages that are needed
source("global-config.R",echo=FALSE)
```

and adjust `global-config.R` to also list `knitcitations`

***

## Click on "Knit"

![rendering errors](images/RStudio_Cloud_464.png)

Dependencies again
=================

<div style="text-align: center;">
<img src="images/RStudio_Cloud_464.png" width="60%" alt="scan" />
</div>


And another problem (maybe)
=======================
Enable popups for this site:

<div style="text-align: center;">
<img src="images/popup-blocker.png" width="60%" alt="scan" />
</div>


Problem solved NOW?
===================
## You should have seen a pop-up window with the compiled text
- do the graphs look the same?
- does the text look the same?

***
![Success!](images/giphy_success.gif)

Question:
========
type: prompt
incremental: true

## Are we done?

***
## Not quite...

### Important 
- record any changes (**Goal 4**)
- how permanent is the data we are using? (**Goal 2**)
- how permanent is my document? (**Goal 2**)

### Useful 
- how can others easily see my latest version? (**Goal 3**)





Next steps
==========


## Recording and documenting changes
- using Git**b!

## Making the data permanent
- using Zenodo again


***
## Making the page more permanent

- Using [Zenodo](zenodo.html)

## Making the page more accessible

- [on Github](github-pages.html)
- on Gitlab








Recording changes
=================
type: section

Your almost there
=================
Because we used Git**b, we have the changes already under control:

<div style="text-align: center;">
<img alt="Rstudio top right" src="images/RStudio_Cloud_top_right.png" width="60%"  />
</div>


Commit all the changes
===================

<div style="text-align: center;">
<img alt="Rstudio git" src="images/RStudio_Cloud_git.png" width="60%"  />
</div>

Commit all the changes
===================

<div style="text-align: center;">
<img alt="Rstudio git boxes checked" src="images/RStudio_Cloud_git_checked.png" width="60%"  />
</div>

Review the changes
==================
<div style="text-align: center;">
<img alt="Rstudio review" src="images/RStudio_Cloud_git_review_changes.png" width="60%"  />
</div>

Push back to repository
======================

<div style="text-align: center;">
<img alt="Rstudio git push" src="images/RStudio_Cloud_git_push.png" width="60%"  />
</div>


















Compare the changes: Version Control
===================
Since we used Gitlab, you can compare the changes: <small>https://gitlab.com/larsvilhuber/jobcreationblog/compare/v1.0...master?view=parallel</small>

<div style="text-align: center;">
<img src="images/gitlab-diff.png" width="80%" alt="scan" />
</div>

This is one way to recover changes, and then verbosely describe them to the editor/thesis advisor/etc.!





Lessons learned
===============


##  Goal 1: Identify all the elements of a fully reproducible analysis

Data, source document, dependencies

## Goal 2: Be able to curate the data and code necessary for reproducible analysis

Today:
- source document
- Gitlab

Tomorrow:
- input data
- output document

***

## Goal 3: Robustness and automation - getting close to push-button reproducibility
- Rmarkdown document has code, text, and figures 
- Dependencies identified, addressed

## Goal 4: Correctly document reproducible research
- Gitlab version control to document changes
- Documenting dependencies for clarity









Thank you for today
==========
type: section

Presentation: https://labordynamicsinstitute.github.io/replication-tutorial-2019

Source: https://github.com/labordynamicsinstitute/replication-tutorial-2019

Next day: [here](day2.html)

![CC-BY-4.0](images/cc-by-nc.png) <small>[Creative Commons Attribution-NonCommercial 4.0 International Public License](LICENSE.html)</small>




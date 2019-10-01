Replication Tutorial
========================================================
author: Lars Vilhuber
date: August 2019
autosize: true
width: 1200

Cornell University




When we stopped
==========

## Making the page more permanent

- Using [Zenodo](zenodo.html)

## Making the page more accessible

- [on Github](github-pages.html)
- on Gitlab

***

## Recording and documenting changes
- using Git**b! ✔️

## Making the data permanent
- using Zenodo again







How permanent is the data?
=========================
type: section

The data is obtained from a Census Bureau website.
- The website http://www2.census.gov/ces/bds/ might be re-organized and disappear
- The data format might change
- The API might change
- We only need two small chunks of code

Making the data more permanent
=============================

## Multiple options
  -  [Dryad Digital Repository](http://datadryad.org/)
  -  [figshare](http://figshare.com/)
  -  [Harvard Dataverse Network](http://thedata.harvard.edu/dvn/)
  -  [ICPSR](https://www.icpsr.umich.edu/icpsrweb/) and [OPENICPSR](https://www.openicpsr.org/openicpsr/)
  -  [Open Science Framework](http://osf.io/)
  -  [Zenodo](http://zenodo.org/)
  
***
We used Zenodo again, but all the others are just as good!
- We uploaded manually

[![zenodo](images/Screenshot_2019-04-23 Zenodo - Research Shared.png)](https://zenodo.org)

Using the permanent data
========================

<div style="text-align: center;">
<img src="images/Screenshot_2019-04-23 Replication Data for Replication for How Much Do Startups Impact Employment Growth in the U S.png" width="80%" alt="scan" />
</div>

Making code changes cautiously (branching)
========================
## If we want to incorporate the Zenodo data
We could
- make all the changes right away
- possibly mess up the live site/ latest version of the paper?
- maybe annoy our co-authors?

***
## But we used a version control system with **branching**!
We instead
- created a new branch `zenodo`
- made all the changes there
- can compare the changes to the `main` branch
- consult with our co-authors before pulling the changes back into the main branch
- our live site/paper remains valid the entire time

Compare the changes: Version Control
===================
Since we used Gitlab, you can compare the changes: <small>https://gitlab.com/larsvilhuber/jobcreationblog/compare/master...zenodo?view=parallel</small>

<div style="text-align: center;">
<img src="images/Screenshot_2019-04-29 larsvilhuber jobcreationblog gitlab diff.png" width="80%" alt="scan" />
</div>

Compare the changes: Version Control
===================

We could then proceed to incorporate (**pull** or **merge**) the changes into the `main` repository:

<div style="text-align: center;">
<img src="images/Screenshot_2019-04-29 larsvilhuber jobcreationblog gitlab merge request.png" width="50%" alt="scan" />
</div>

Read more about it at https://help.github.com/en/articles/about-pull-requests and https://docs.gitlab.com/ee/gitlab-basics/add-merge-request.html 

Final result
============
The final result would

- pull data from Zenodo
- reliably reproduce the graph as presented today
- use citable data (`DOI = 10.5281/zenodo.2649598`)
- be citable itself (`DOI = 10.5281/zenodo.400356`)

Conclusion
==========
type: section

Conclusion
==========
## Replication can be a lot of work
We've touched on
- Replication per se
- Replicable documents
- Possible pitfalls of software dependencies
- Cloud computing platforms
- Permanence of source material (website, data) and how to solve it

***

![project](images/Screenshot_2019-04-23-Replication_for_how_much.png)

Conclusion
==========

## We have not covered everything
... because there can be a lot more
- HP computing <small>(length, quantity, throughput)</small>
- Issues with commercial (paid) software <small>(access, permanence)</small>
- Data that is not public-use
- Data in a locked room

***
![SafePODS](images/SafePODS.png)

Thank you
==========
type: section

Presentation: https://labordynamicsinstitute.github.io/replication-tutorial-2019

Source: https://github.com/labordynamicsinstitute/replication-tutorial-2019
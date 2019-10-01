Building a replicable document
========================================================
author: Lars Vilhuber
date: 2019-09-30
autosize: true
width: 1200


Building a replicable document
==============================
incremental: true


## Why would you do this

- lay out all the steps as "literate programming"
- can serve as the "README"!
- ideally runs automatically

***

## Why would you not do this

- in general, support for citations is weak/ tricky
- in general, not suggested when running counter to other best practices
  - becomes tricky when long-running computing is involved
  - runs counter to "short, focussed programs doing one thing" rule


Tools for a replicable document
===============================
incremental: true

## a place to store it
  - Dropbox? 
  - *Github? Gitlab? Bitbucket?*
  
## a place to compute it
  - your laptop?
  - my laptop?
  - a university server?
  - a cloud server?
  - all of the above?
  
***
## a programming language
  - R
  - Stata
  - Python
  - SPSS
  
## a format for the text
  - Word?
  - $\LaTeX$
  - Markdown? 


Tools for a replicable document
===============================
incremental: false

## a place to store it
  - Dropbox? 
  - **Github!** **Gitlab!** *Bitbucket?*
  
## a place to compute it
  - your laptop?
  - my laptop?
  - a university server?
  - **a cloud server!**
  - **all of the above!**
  
***
## a programming language
  - **R** (but don't worry!)
  - *Stata*
  - *Python*
  - SPSS
  
## a format for the text
  - Word?
  - $\LaTeX$
  - **Markdown!**

Aside: Markdown
===============
type: sub-section

## a format for the text
  - Word?
  - $\LaTeX$
  - **Markdown**
  - $\overline{x} = \frac{1}{N}\sum_{i=1}^N x_i$
  
***
## Looks like this
```
## a format for the text
 - Word?
  - $\LaTeX$
  - **Markdown**
  - $\overline{x} = \frac{1}{N}\sum_{i=1}^N x_i$
```

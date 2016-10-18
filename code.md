---
layout: page
title: Code
permalink: /code/
---

## The choice for R

The codebase of the PolMine project is written in the statistical programming language R. The drawbacks of R notwithstanding (see The R inferno), we decided to move to R throughout:
* R offers an incredible breadth of packages for statistical analysis
* R has a reputation to be great for visualisations
* RStudio is a great and freely available IDE
* interfacing to Perl, Python, Java and C (i.e. the great tools available) is not too difficult
* R is already widely accepted among social scientists

PolMine strives to make a contribution to social science research, and wrapping code into R packages is how we think that can be achieved best. The publication of the code on GitHub ensures the availability of latest development version of the packages.

## The CWB backend: polmineR

Why yet another tool for corpus analysis? None of the existing tools appeared to be in line with the research process envisaged (to facilitate inspecting the original text) and with the performance needs to cope with corpora that encompass tens of millions of words.

The polmineR-package follows the design principle of a three-tier architecture. The Open Corpus Workbench (CWB) serves as an engine for indexing corpora and for retrieving information. The syntax of Corpus Query Processor (CQP) provides powerful abilities to formulate complex queries. The polmineR-package uses the rcqp-package, mostly a wrapper around the Corpus Library (CL) written in C  to interface to the corpora indexed by the CWB.  The software architecture is flexible, portable and fast.

The polmineR may be considered the core of a set of expanding packages. The object oriented style of the implementation (technically speaking, the use of the S4 class system) facilitates the development of functions and packages expanding the functionality of polmineR.

## A corpus toolkit: ctk

The combination of the CWB with R/polmineR was developed to facilitate the research with corpora of plenary protocols. It may be useful for any other CWB-indexed corpus you have. To make corpus preparation easier, we use the corpus toolkit (ctk), a companion package to the polmineR package. The ctk package provides a set of R wrappers for standard tools for natural language processing such as the TreeTagger (for linguistic annotation), stanfordNLP or openNLP.

A core feature of ctk is the ability to speed up corpus preparation through parallelization. The core function is “dirApply”, to manage the parallel execution of a function for all files in a directory while showing progress information. The package is available at GitHub. Admittedly, the documentation needs to be improved.

Just as polmineR, ctk requires a MacOS, or Linux operation system. Windows users may use a virtual linux system. An alternative that works nicely is the installation of all components on a (Linux) server, and using the server edition of RStudio.

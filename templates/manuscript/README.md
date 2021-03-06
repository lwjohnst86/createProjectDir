---
title: Introduction
author: ((author))
date: ((date))
geometry: margin=1in
fontsize: 12pt
papersize: letterpaper

---

* Project title: ((project))
* Data used: ((data))

This README details how this research directory is structured, how
files should be run and what the different files do.

The files created by
[`prodigen.sh`](http://github.com/lwjohnst86/prodigen) use the
following programs:

* [GNU Make](http://www.gnu.org/software/make/) (automating executing
  file scripts)
* [\LaTeX ](http://www.latex-project.org/) (\TeX Live, Mik\TeX, etc.;
  generates `.pdf` files)
* [Pandoc](http://johnmacfarlane.net/pandoc/) (for Markdown (`.md` or
  `.Rmd`) conversion)
* [R](http://www.r-project.org) (stats)
    * Package: [knitr](http://yihui.name/knitr/) (reproducibility)
* [Git](http://git-scm.com/) (version control system)
* Shell script (e.g. [Bash](http://www.gnu.org/software/bash/); to use
  most of the above programs)

To open up some files, the programs
[Inkscape](https://inkscape.org/en/) (`.svg` files),
[Docear](http://www.docear.org/) (`.mm` files) and
[VUE](http://vue.tufts.edu/) (the files in the `diagrams` and `dag`
folder) will also need to be installed.

Directory structure and explanation
===================================

The project directory is generally structured with `data`,
`scripts`, `output`, `lit`, and `report` folders, as well as a version
control `.git` folder.  As a caveat, there may be folders other than
the below that were created for an ad hoc purpose.

`data` folder:
--------------

The `data` folder contains the analysis-specific dataset.  Meaning
this dataset may be a subset of an original dataset, keeping the data
relevant to the research question.

`lit` folder
------------

The `lit` folder contains files relevant to the literature and for
understanding the causal pathways.  There are a few folders within the
parent `lit` folder:

* `mindmap` --- Contains mindmaps that are used to help organize the
  articles that were read, the information and findings from the
  articles, and to help structure writing up the report.  The `.mm`
  file within uses [Docear](www.docear.org).
* `diagrams` --- Contains conceptual diagrams to better understand the
  biology underlying the research question and to understand the
  findings of the literature.
	  * `dag` --- Contains directed acyclic graphs (DAG) to represent
         the underlying causal and confounding pathways.  DAGs are
         used to help guide which covariates to include when building
         predictive models that test the relationship between the
         exposure and the outcome.
* `bib-db` --- After the manuscript has been accepted and submitted to
  a journal, the .aux file generated by
  [\LaTeX ](http://www.latex-project.org/) can be used to subset the
  master `.bib` file into only those references used (maybe not... I
  still need to think about this one).  This subsetted `.bib` file
  should be copied into this folder for future reference and to
  maintain the modular nature of each research project folder.

`scripts` folder
----------------

The `scripts` folder contains the scripts which runs the analyses and
figure generations, outputting them into the output folder.  There are
various `.R` files that achieve different purposes, for example, the
`fetchData.R` file subsets the original dataset and creates relevant
variables while the `analysis.sas` file will run the analyses and
output the results that can also be used in the generation of the
report.  This folder also contains another folder:

* `opt` --- Contains the options files for the analyses, as well as
  the file to generate HTML documentation of the `scripts` files.
* `templates` --- Contains template `.R` files to copy whenever a new
  `.R` file is needed.

`output` folder
---------------

The `output` folder (with the internal `figs` folder) will contain all
the output files generated from the R scripts which are necessary for
the analysis and the report.  The idea behind the output folder is
that you should be able to delete all the files, run the scripts
again, and generate all the necessary result files.  In fact, in the
parent directory of the project folder (i.e. `./`), the command `make
clean` should be run in the terminal to delete all output files to
make sure that the script files are generating all the needed output
files.  This folder also contains the `figs` folder to store all the
figures generated by R.

`report` folder
---------------

The `report` folder contains the files to create the final report for
the research project.  The hope is that all the results within the
report can be reproducible and replicable easily (using knitr) so that
if the analysis changes, all numbers change automagically as well.
This process is known as "reproducible research" and should be
actively adhered to, to be as scientifically responsible and rigorous
as possible.  In order to generate the document, type the command
`make report` into the terminal in the parent directory to generate
the document in pdf format.  At this time, I am not sure how effective
the Markdown to Doc conversion will be.  I will test it and update
this README when I know how it works.


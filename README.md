# Brief summary of script #

Note: This program is still in development.

This is a <b>pro</b>ject <b>di</b>rectory <b>gen</b>erator (prodigen) that will create a project directory structure with template files necessary for managing and analyzing data, as well as writing up a manuscript.  This allows for a standardized approach to having modular research projects.  This program can be found at [github.com/lwjohnst86/prodigen](https://github.com/lwjohnst86/prodigen).

# Installation and Usage #

Install by forking or cloning this repo.

To use `prodigen`, place a symlink of the `prodigen.sh` file somewhere where your PATH can find it (maybe in `~/bin`; see [here](http://unix.stackexchange.com/a/26059) for an explanation of how to add to the PATH).  Make the script executable (`chmod 766 prodigen.sh`).  Confirm that the shell can find it (`which prodigen.sh`).  If the shell shows a path, then the shell can find it.  Run the script by typing `prodigen.sh` in the shell.  And that is it!

*Note*: This so far only works in Linux.  It is not tested for Windows or Mac.

# Dependencies #

## --- Running the program ##

* Bash, or any shell program
* Make

## --- For using the generated files/scripts ##

* R --- scripts containing analysis
* Make --- running commands to generate results output and the manuscript
* LaTeX --- creating manuscript
* VUE --- making concept maps and directed acyclic graphs
* Docear --- organizing literature and notes

# Purpose of script #

I created this program/script to make creating a folder structure and template files easier when I start a new research/analysis project.  My aim was to have the research project directory contain all the files necessary for a manuscript.  This way, it is entirely self-contained and modular, so that if other researchers ask how the results were obtained or for the code, I can easily send it to them.  The reason I put it up on GitHub is to share partly this program, but mostly the idea of having some way to standardize the creation of a research project.

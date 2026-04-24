# Demo VQA external project-specific scripts directory

## Introduction

This repository a demo of a confidential source code repository used to keep custom, client-specific project and parameter scripts confidential by keeping them outside the main (public) VQA source code directory. As a demo, this repository is public. However, for a real world VQA application, this repository would be private, and you would main multiple private confidential source code repositor——one for each distinct client or projects. Note, however, that you can keep scripts from muliple projects belonging to the same owner or client in the same repository.

This confidential source code repository contains a params.pa.R file, two project-specific parameters files (in subdirectory `params/`) and two project-specific import files (in subdirectory `imports/`). These customs scripts are for the two VQA demos `vqa-demo1` and `vqa-demo2`. You will find the raw data for these demos inside directory `data/vqa-demo1/raw/` and 'data/vqa-demo2/raw/` in the demo `data/` directory in the main code repo. For an actual VQA application, you would keep your date in a separate external data directory *outside* the main code repo directory, and reset data directory path parameters to point to the new location. Ideally, you would also keep all you project-specific scripts outside the main repo, in one or more confidential source code repositories like this one.

## Installation

Clone this repo to a location immediately above (i.e., at the same directory level as) the main VQA source code directory. For this example, let’s name the base directory to `src_conf_demo` (you can call it whatever you want, but let’s use this name for the demo). 

####To use these files:  
* Set PROJ and ASSESS (in script `params.pa.R` in this directory) to the code of the project and assessment you wish to analyze
* Make sure you follow VQA name conventions by embedding the project code in the name of the project-specific parameters file (`params.<PROJ>.R`) and the project-specific import file (`import.<PROJ>.R`).
* Make sure your project data directory is also named for the project code (i.e., `data/<PROJ>/`) and the assessment data directory (inside the project data directory) is the same as the assessment code (i.e., `data/<PROJ>/<ASSESS>/`).
* Make sure your data directory is also at the same level as the main source code directory and the confidential source code directory.
* In section `# Set base directories` of the general parameters file (`params.R`) inside the main source code directory, set the following parameters as shown below:

```
LOC_DATA_DIR <- "out"
LOC_PSFILES_DIR <- "out"
SRCDIR_CONF <- "src_conf_demo/"
```
Assuming your other parameters are all good, you are now set to VQA away!
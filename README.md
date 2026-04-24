# VQA confidential scripts directory demo

## Introduction

This repository is a demo of an external confidential source code repository used to keep custom, client-specific project and parameter scripts confidential by keeping them outside the main (public) VQA source code directory. Although this repository is public, other repositories of project-specific scripts would be private. Ideally you would maintain several, one for each client. You can keep scripts for different projects in the same repository, as long as they belong to the same owner.

This demo confidential source code repository contains a params.pa.R file, two project-specific parameters files (in subdirectory `params/`) and two project-specific import files (in subdirectory `imports/`). The scripts are for two VQA demos: `vqa-demo1` and `vqa-demo2`. 

You will find raw data for these demos inside directory `data/vqa-demo1/raw/` and 'data/vqa-demo2/raw/` in the demo `data/` directory of the main code repo. For an actual VQA application, you would also keep your data in a separate external data directory *outside* the main code repo directory, and reset data directory path parameters to point to the new location. 

## Installation & setup

1. Clone this repo to a location immediately above (i.e., at the same directory level as) the main VQA source code directory. For this example, let’s name the base directory to `src_conf_demo` (you can call it whatever you want, but let’s use this name for the demo). 
2. Set PROJ and ASSESS (in script `params.pa.R` in this directory) to the code of the project and assessment you wish to analyze
3. Make sure you follow VQA name conventions by embedding the project code in the name of the project-specific parameters file (`params.<PROJ>.R`) and the project-specific import file (`import.<PROJ>.R`).
4. Make sure your project data directory is also named for the project code (i.e., `data/<PROJ>/`) and the assessment data directory (inside the project data directory) is the same as the assessment code (i.e., `data/<PROJ>/<ASSESS>/`).
5. Make sure your data directory is also at the same level as the main source code directory and the confidential source code directory.
6. In section `# Set base directories` of the general parameters file (`params.R`) inside the main source code directory, set the following parameters as shown below:

```
LOC_DATA_DIR <- "out"
LOC_PSFILES_DIR <- "out"
SRCDIR_CONF <- "src_conf_demo/"
```
Assuming your other parameters are all good, you are now set to VQA away!
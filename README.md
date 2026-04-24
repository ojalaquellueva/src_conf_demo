# VQA Project-Specific Scripts Directory Demo

## Introduction

This repository is a template of an external project-specific scripts directory (PSSD) used to keep custom VQA parameter and import scripts confidential by storing them outside the main (public) VQA source code directory. Although this template repository is public,  repositories of project-specific scripts would normally be private and accessible only to project administrators and developers. In practice, you would maintain several PSSDs, one for each project. However, you may also keep scripts for different projects in the same PSSD, as long as they belong to the same owner(s). 

The main purpose of the PSSD is to keep project-specific scripts outside the main source code directory. This arrangement allows us to keep VQA code public and open source (as required by VQA’s GPL 3 license) while enabling users to restrict access to a bare minimum of confidential code specific to their own projects. There is no obligation to version-control the PSSD nor to to establish a remote repository; however, versioning is strongly recommended given the critical importance of project-specific scripts to VQA functionality, and a remote repository provides numerous benefits such as collaborative development and automated distribution of application updates. 

# Directory structure and contents

The demo PSSD contains a project & assessment parameters file (`params.pa.R`), two project-specific parameters files (`params.vqa-demo1.R` and `params.vqa-demo2.R`, in subdirectory `params/`) and two project-specific import files (`import.vqa-demo1.R` and `import.vqa-demo2.R`, in subdirectory `imports/`).

You will find raw data for these demos in directories `data/vqa-demo1/raw/` and `data/vqa-demo2/raw/` in the main VQA code repo. For actual VQA applications, you should also keep the data directory *outside* the main code repo directory, and reset data directory path parameters to point to the new location. Keeping data outside the repo avoids filling the public repository with confidential, versioned data. There are other options for versioning data if that is a concern.

## Installation & setup

1. Clone this repo to a location immediately above (i.e., at the same level as) the main VQA source code directory. For this example, make sure the base directory is named `src_conf_demo`. You can call a PSSD whatever you want, but use this name for the demo. 
2. Set PROJ and ASSESS (in script `params.pa.R` in this directory) to the codes of the project and assessment you wish to analyze.
3. Follow VQA naming conventions by including the project code in the name of the project-specific parameters file (`params.<PROJ>.R`) and the project-specific import file (`import.<PROJ>.R`).
4. Follow VQA naming conventions by ensuring project data directory is also named for the project code (i.e., `data/<PROJ>/`) and the assessment data directory (inside the project data directory) is the same as the assessment code (i.e., `data/<PROJ>/<ASSESS>/`).
5. Make sure your data directory is also at the same level as the main VQA source code directory and the PSSD.
6. In section `# Set base directories` of the general parameters file (`params.R`) in the main VQA source code directory, set the following parameters as shown below:

```
LOC_DATA_DIR <- "out"
LOC_PSFILES_DIR <- "out"
SRCDIR_CONF <- "src_conf_demo/"
```
Assuming your other parameters are all good, you are now set to VQA away!
# SeCaPr - Sequence Capture Processor
A computational pipeline for processing Illumina sequence capture data [![downloads](https://anaconda.org/bioconda/secapr/badges/downloads.svg)](http://bioconda.github.io/recipes/secapr/README.html)

***

## Documentation
The documentation, including an empirical data tutorial, is divided into the following steps (click on the links):
- [Cleaning and adapter trimming](subdocs/cleaning_trimming.ipynb)
- [De-novo contig assembly](subdocs/contig_assembly.ipynb)
- [Extract target contigs](subdocs/extract_contigs.ipynb)
- [Align contigs](subdocs/align_contigs.ipynb)
- [Reference-based assembly](subdocs/reference_assembly.ipynb)
- [Locus selection](subdocs/locus_selection.ipynb)
- [Phasing alleles](subdocs/phasing.ipynb)
- [Phylogeny estimation](subdocs/phylogeny_msc.ipynb)


***

## Installation & Setup
SECAPR is available as a conda package on the bioconda channel. This makes installation very simple. Follow the instructions on this page to get the SECAPR pipeline set up and ready to use:

<div class="alert alert-block alert-info">

| INFO: All commands in this tutorial have to be executed from a bash-command line terminal. |
| --- |



</div>

___
### 1. Install conda

Download the **Python2.7 version** of [Miniconda](https://conda.io/miniconda.html) and install it by executing the downloaded sh-file (see commands below). Conda is a software and environment manager, that makes installation of new software and of required dependencies very simple and straightforward.

*Download conda (MacOS 64bit):*
<div class="alert alert-block alert-info">
wget https://repo.continuum.io/miniconda/Miniconda2-latest-MacOSX-x86_64.sh
</div>

*Download conda (Linux 64bit):*
<div class="alert alert-block alert-info">
wget https://repo.continuum.io/miniconda/Miniconda2-latest-Linux-x86_64.sh
</div>

*Download conda (Linux 32bit):*
<div class="alert alert-block alert-info">
wget https://repo.continuum.io/miniconda/Miniconda2-latest-Linux-x86.sh
</div>

*Install conda:*
<div class="alert alert-block alert-info">
sh Miniconda2-latest-*.sh
</div>

*Add Bioconda channels (containing bioinformatics software):*
<div class="alert alert-block alert-info">
conda config --add channels defaults; conda config --add channels conda-forge; conda config --add channels bioconda; conda config --add channels https://conda.anaconda.org/faircloth-lab     
</div>


***

### 2. Install the SECAPR environment
Conda automatically downloads and installs all necessary software dependencies. We strongly recommend to **install SECAPR and all it's dependencies in a separate virtual environment**, in order to not interfer with potentially already installed verisons of the software dependencies.

*Install SECAPR in virtual environment (here named `secapr_env`):*

<div class="alert alert-block alert-info">

conda create -n secapr_env secapr

</div>

Alternatively you can also just plainly install the software on your computer (without creating an environment) by clicking on the icon below and following the instructions (**not recommended!**):

[![install with bioconda](https://img.shields.io/badge/install%20with-bioconda-brightgreen.svg?style=flat-square)](http://bioconda.github.io/recipes/secapr/README.html)

***

### 3. Activate the environment
To activate the newly created environment, type:

*Activate environment*:
<div class="alert alert-block alert-info">
source activate secapr_env
</div>

When the environment is activated, all the necessary software dependencies will be available in the standarad path, e.g. when you type `samtools` the samtools version required for SECAPR will be executed. After you are done using secapr, you can deactivate the environment to switch back to your standard environment with this command:

*De-activate environment*:

<div class="alert alert-block alert-info">

source deactivate

</div>

***

### 4. Check active environment
Check if you are connected to the correct environment (there should eb a star in front of secapr_env in the output of this command):

*Check active environment*:

<div class="alert alert-block alert-info">

conda info --envs

</div>


<div class="alert alert-block alert-warning">

IMPORTANT : When you are using the SECAPR pipeline, make sure the secapr_env is activated. Activate with **source activate secapr_env**

</div>

***

### 5. Install SECAPR development version

The development version of SECAPR is stored on this GitHub page and contains the newest updates, which might not yet be available through the conda version. However you need to install the SECAPR environment with conda first by following the steps above. Once the environment is installed, you can update SECAPR to the development version by following these steps:

1. Connect to your secapr environment (`source activate secapr_env`)
2. Remove the current secapr installation (`conda remove secapr`)
3. Download the new version from github (`wget https://github.com/AntonelliLab/seqcap_processor/archive/master.zip`)
4. Unzip the downloaded file (`unzip master.zip`)
5. Move the unzipped directory to a safe location on your computer, i.e. not on your Desktop or Download folder. This will be the path where secapr will be executed from in the future
6. Enter the unzipped secapr directory (`cd seqcap_processor-master`)
7. Install secapr from the folder (`python -m pip install -e .`)
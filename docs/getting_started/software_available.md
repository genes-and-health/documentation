## Linux command line software

A very comprehensive set of genomics/genetics software is available to run from the linux Terminal command line. See also Appendix for example scripts.

Some software has very good multithreading e.g. plink2 or regenie. If you run these on the 64 core ivm (please test on the cheap 2 core machine first) you can get performance quite close to high performance compute (HPC) for some medium sized applications, and you don't have to learn WDL scripts. Alternatively, true cloud HPC is available using WDL Pipelines (see below).

## Scripting languages

There are a number of different languages available on the TRE including Python, R and Bash. 

### Python

It is worth noting that Python does not have the normal virtual environment setup that you might be used to. It is not possible to install packages using `pip install` as you would on your local machine as the TRE does not have internet access, and therefore cannot connect to the Python Package Index (PyPI), or a specific GitHub repository. Packages are installed by the Sanger Institute and are available to all users. 

## Instructions for specific software

### Integrated Genome Viewer (IGV)

We have installed IGV to run from the linux Terminal command line (not the web browser version). Make sure you are using the right genome fasta for your cram files, otherwise you will get an 'md5 error' (e.g. the default hg19 will not work with Wellcome Sanger Institute crams).

Example for the 5236 Wellcome Sanger Institute low depth exomes:

`/usr/local/bin/IGV\_Linux\_2.12.3/igv.sh --genome /genesandhealth/library-red/genesandhealth/exome\_seq/2019\_11\_\_5236\_GNHonly/crams/hs38DH.fa /genesandhealth/library-red/genesandhealth/exome\_seq/2019\_11\_\_5236\_GNHonly/crams/sc\_autozygELGH6823965.cram`

The default set of (hg19) files for IGV are found here

`/genesandhealth/library-green/sanger/igv/`

### Jupyter notebooks

Jupyter is available in Applications menu as graphical user interface and can be run from the linux command line, by running `jupyter notebook` in the terminal. 

## VS Code

The VS Code editor is available in Applications menu as graphical user interface (not from linux command line). It does not have plugins available unless they are specifically requested and installed by the Sanger Institute.

Any commands or scripts that rely on outside software will not work in the VS Code terminal unless the software is installed in the linux command line. For example, Github Co-pilot will not work in the VS Code terminal.

### RStudio

RStudio is available in Applications menu as graphical user interface (not from linux command line).

### LibreOffice

LibreOffice provides equivalents for Microsoft Excel, Powerpoint, Word etc and is available in Applications menu as graphical user interface (not from linux command line).

### Git

Git available from the linux command line for single user use and has some limited integration with RStudio and Jupyter Notebooks. However given the fact that the TRE does not have internet access and everyone is signed in as the same user, the use of Git is limited. This may change in the future.

## File browser shortcuts

The file browser for Xfce is called 'Thunar'. Settings and defaults _should_ persist between sessions but don't always.

- Detailed view [ctrl + 2]
- New tab [ctrl + t] (only works if the TRE is in fullscreen mode - Chrome will create a new tab otherwise)

## About Me

I develop quantitative microscopy workflows to investigate neural development
in the HHMI lab of Chris Q. Doe. My work spans experimental design, image
processing, statistical analysis, and multimodal data integration from imaging,
scRNAseq, and connectomics. I write robust and reproducible analysis pipelines
in Python and R to uncover the genetic control of synaptogenesis, and create
visualizations to communicate my results to the broader scientific community. I
build and publish open-source software that is used by other researchers to
process and quantify their imaging data. My work in data science and durable
software development transforms large-scale data into reproducible quantitative
measurements that reveal biologically meaningful patterns.

Below is a list of my software projects:

## Software intended for public use

These are the packages that were created with the intent of being used by
others.

### Napari-3D-Counter

https://github.com/pnewstein/napari-3d-counter

This is a plugin for the image viewer napari, that provides a user-friendly
interface for manually counting cells.

This project is well covered by unit tests that run in a CI environment prior
to publishing on PiPY, which has helped me keep up with occasional breaking
changes from napari.

Related is https://github.com/conda-forge/napari-3d-counter-feedstock which is
responsible for packaging Napari-3D-Counter for conda-forge.

It has been published in the Journal of Open Source Software (JOSS), and has
been used up by a few labs:
https://scholar.google.com/scholar?q=napari-3d-counter&btnG=Search

the JOSS article contains more infomation


### Auto-Filet

https://github.com/pnewstein/auto-filet

I study the body wall motor neurons of Drosophila embryos. These cells are
present in each segment and have somata in the ventral nerve cord, and project
axons through the body wall to the dorsal side of the animal. This cylindrical
morphology is not amenable to standard maximum intensity projections.
Therefore, I created this package which projects an image of a Drosophila
embryo into cylindrical coordinates. This simulates the filet prep, where the
dorsal side of the embryo is cut open, pulled apart, and laid flat so the
rightmost and leftmost side of the prep come from the dorsal side of the
animal, and the middle of the prep comes from the ventral side of the animal.
This package exposes Python classes that take napari objects and process the
data using SciPy.


### Template-6-ALH

https://github.com/pnewstein/template6alh

A package to create and align to template images of the 6 hour old larval
central nervous system. It uses a two-step approach of first aligning to a less
detailed NCad neuropil stain, then fine-tuning based on a more detailed FasII
stain. Uses a Python/SQLAlchemy system to manage the multi step process of
registration and alignment using CMTK.


## Software intended for personal use

I have found that the best way to practice software development is by doing
projects. I have found many of these projects to be useful. This is a list of
the projects I developed and regularly use.

### Embryo-VNC-Align

https://github.com/pnewstein/embryo-vnc-align

https://github.com/pnewstein/embryo-vnc-align-napari-frontend

https://github.com/pnewstein/qt-remote-commands-over-ssh-for-napari-plugins

I often acquire images of embryos in such a way that they are deposited on the
side in a random orientation. Therefore, I need to apply a rotation matrix to
the image to get it into the canonical orientation of anterior +y, dorsal +z,
right +x. This package solves that problem by taking in 4 coordinates
(Anterior-most point, posterior-most point, and a left and right point that
have the same dorsal-ventral position) and an estimated height of the VNC. The
package computes the correct coordinate system and uses CMTK to render the
image in that coordinate system.

I also have a repo that provides a GUI widget for napari to more easily provide
the inputs to the algorithm. This widget uses my package,
qt-remote-commands-over-ssh-for-napari-plugins to offload the processing to
another computer.  It uses napari background threads to await processed images,
allowing for a responsive GUI

### B-H1

https://github.com/pnewstein/b-h1

This is the work in progress scripts used to make figures for an in progress
publication. Here, in many cases, code quality and readability have been
sacrificed in the name of quickly generating figures for feedback. 

This repo includes code to generate sample images, do statistical analysis
(including permutation tests and some classifier prediction), and make plots

### napari-scripts

https://github.com/pnewstein/napari-scripts

These are helper scripts I use with napari. They range from loading images and
starting Napari-3D-Counter to image segmentation.

###  multi-species-homeodomain

https://github.com/pnewstein/multi-species-homeodomain

Analysis code I wrote for
https://www.biorxiv.org/content/10.1101/2024.09.27.615552v3.abstract. In
review at Nature

### Snapshot

https://github.com/pnewstein/snapshot

This code saves the state of a napari viewer along with the path to the image
data, rather than a copy of the image data

I use this package to reproducibly make sample images for figures

### slide viewer

https://github.com/pnewstein/ts-slides

Since 2023 I have been using custom software to present slides, which I make
using inkscape. The README in this repo describes the motivation and workflow.


### Quick Neurite Trace

https://github.com/pnewstein/quick-neurite-trace

Uses brightest_path_lib to trace neurons using napari as the UI.

I wrote this code since the napari-tracing plugin does not support modern
napari, and I needed simple traced neurites for a figure



## Old packages I haven't used in a while

These are packages that worked and served their purpose in their time, but I
have not had the need to use or maintain.

### GTF-FUZ

https://github.com/pnewstein/gtf-fuz

This tool helps you map the name you partially remember for a gene to the gene
name as it appears in a gtf file. 

### CZI-Scenes

https://github.com/pnewstein/czi-scenes

By default, Zeiss microscopes optimize the order of scenes that they image.
This tool tells you what scene numbers that you selected correspond to what
indicies in the CZI file. This is helpful if you took notes based on the scene
numbers you selected.

### Neuropil Template Creation

https://github.com/pnewstein/neuropil-template-creation

This code was used to create and align to a template image in the publication
https://doi.org/10.1371/journal.pbio.3002881

### neurotraceutils

https://github.com/pnewstein/neurotraceutils

extracts SWC files from filements in ims files


## peter-rotation3

https://github.com/pnewstein/peter-rotation3

Contains code to visualize SWC files, rna-sequencing data, and
electrophysiology traces. Uses python and R.


## Contributions to other projects

In addition to my own projects I have contributed to other open source projects

### napari

I sucessuly contributed code to napari which fixed a bug where the thick slicer
widget was not reused between activations.


### Navis

I sucessuly contributed code to navis which fixed a bug where connectors were
not plotted in the correct collor

### napari-czifile2

https://github.com/BodenmillerGroup/napari-czifile2/pull/13

I updated this package to support czifile 2026, though this code has not yet
been merged in. However, I maintain a fork with a branch that changes the way
that multi-scene files are loaded, which is used by Doe lab members.

### JOSS review of bm3dornl

I am in the process of reviewing
https://github.com/ornlneutronimaging/bm3dornl. I carefully reviewed the code
and documentation and  submitted some issues to the repo.

[STICS](https://www6.paca.inra.fr/stics_eng/) model example data
================================================================================================================================================================

Overview
------------

This repository contains a set of example input data used by the STICS model. It is mainly used as example data in the [sticRs](https://github.com/VEZY/sticRs) package vignettes.

Download
------------

To download the data, you can either

* Clone it from the [Github repository](https://github.com/VEZY/STICS_dummy):

  ```
  git clone https://github.com/VEZY/sticRs.git
  ```
* Or direct download the [zip file here](https://github.com/VEZY/sticRs/archive/master.zip).

* Or use the [git2r](https://github.com/ropensci/git2r) package from R:

 ``` r
 # install.packages("git2r")
 target_path= "path_where_to_download_folder"
 git2r::clone("https://github.com/VEZY/STICS_dummy", target_path)
 ```

Description
------------
STICS uses a minimum of ten input files that group parameters for soil, plants, site, climate etc...
It can use two more if used on intercrops (two per plants and two for technical parameters), and one (sole crop) or two (intercrop) more for observations used for model assessment. After making a run, STICS produce different outputs, depending on the inputs, but one (or two in intercrop) output is particularly useful above all : `mod_s*` (or `mod_sp*` and `mod_sa*` for principal and associated plants respectively in intercrop).

The data provided in this repository are only dummy data with randomized (but plausible) input values. This example set is a wheat in self-intercropping, *i.e.* a simulation of a sole crop of wheat in intercropping mode. This is used to evaluate the intercrop module of STICS, which should yield approximately the same outputs in sole crop and in intercrop mode.  
The example data folder contains sixteen different files:

* `climat.txt`: the input climate
* `ficini.txt`: the initialization file
* `ficplt1.txt`: the principal plant parameters
* `ficplt2.txt`: the associated plant parameters
* `fictec1.txt`: the technical parameters for the principal plant
* `fictec2.txt`: the technical parameters for the associated plant
* `mod_sadummy_simulation.sti`: the simulation output for the associated plant
* `mod_spdummy_simulation.sti`: the simulation output for the principal plant
* `new_travail.usm`: the simulation control file
* `param.sol`: the soil parameters
* `station.txt`: the station (*i.e.* plot) parameters
* `tempopar.sti`: further parameters
* `tempoparv6.sti`: further parameters that will be integrated in the next version
* `var.mod`: Control which simulated variables are written in the `mod_s*` files.
* `wheat_1.obs`: observation data for the principal plant
* `wheat_2.obs`: observation data for the associated plant  s

> In intercrop mode, the STICS model computes one plant after another. The principal plant is the first one to be computed, and the associated one comes second, making the principal plant dominant in the beginning, and the associated dominated. The principal and associated status remain the same over the simulation, however the dominance status can change any time according to plant height.

Code of conduct
---------------

Please note that this project has the only purpose to store example files for a STICS simulation, and to update them as the model is updated. Please update the input files from the master branch only in the case where STICS was modified, or create a new branch for your STICS version.

Authors and acknowledgments
---------------------------

The STICS (Simulateur mulTIdisciplinaire pour les Cultures Standard, or multidisciplinary simulator for standard crops) model is a dynamic, generic and robust model aiming to simulate the soil-crop-atmosphere system. It was first developed in 1996 by INRA -the French National Institute for Agricultural research- by Nadine Brisson and Dominique Ripoche. An overview of the model is available [here](https://www6.paca.inra.fr/stics_eng/About-us/Stics-model-overview).

The sticRs package was developed by [Rémi Vezy](https://remi-vezy.netlify.com/) and the [STICS group](https://www6.paca.inra.fr/stics_eng/) thanks to the European H2020 funded [ReMIX project](https://www.remix-intercrops.eu/).

![ReMIX logo](https://github.com/VEZY/sticRs/blob/master/man/figures/remix_logo.jpg?raw=true)
-----------------------------------------

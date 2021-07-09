# ASReview model switching
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5084912.svg)](https://doi.org/10.5281/zenodo.5084912)

Deep learning is often used in text classification tasks for its efficiency and proficiency in modelling nonlinear processes. However, using this type of machine learning takes more time and processing power than using shallow learning algorithms. This study aims to determine if a combination of shallow and deep learning techniques can be used in increasing the classification performance for automated systematic review software. Since deep learning networks excel at finding hard to find connections, this study aims to find situations in which they outperform shallow networks. To find these situations, simulations were run on a prepared dataset using different classifiers, switching from shallow to deep networks. 

This GitHub repository hosts information and code for research on model switching during simulations and active classification. [asreview-plugin-model-switcher](https://github.com/JTeijema/asreview-plugin-model-switcher) contains a plugin, for software called [ASReview](https://github.com/asreview) ![logo](https://raw.githubusercontent.com/asreview/asreview-artwork/e2e6e5ea58a22077b116b9c3d2a15bc3fea585c7/SVGicons/IconELAS/ELASeyes24px24px.svg "ASReview"). 

The DOI for this repository can be found at https://doi.org/10.5281/zenodo.5082962.


## Requirements

The scripts require the installation of [ASReview](https://asreview.nl/#!/quick-start), [asreview-visualization](https://github.com/asreview/asreview-visualization), the new [convolutional neural network](https://github.com/JTeijema/asreview-plugin-model-cnn-17-layer), and the custom [Model Switcher](https://github.com/JTeijema/asreview-plugin-model-switcher) plugin.

The study used Release v0.17 (2021-04-28) of ASReview.

The exploratory research following inital results require the simple wide_doc2vec to be used too. Found [here](https://github.com/JTeijema/asreview-plugin-wide-doc2vec).


## Usage

`RunThisScript.ipynb` reproduces all data necessary to recreate results for the "A comparison of performance between optimal neural networks and classical algorithms in active learning based text classification" study. A suggestion is either running all commands in parallel on Google Colab (directions are found in the study appendix) or only running those simulations relevant, as the simulations take a long time to run.

## Data
The data used for this repository is from the following study:

Brouwer, M. E., Williams, A. D., Kennis, M., Fu, Z., Klein, N. S., Cuijpers,
P., & Bockting, C. L. H. (2019). Psychological theories of depressive relapse
and recurrence: A systematic review and meta-analysis of prospective studies.
Clinical Psychology Review, 74, 101773. https://doi.org/10.1016/j.cpr.2019.101773

A repository for this data can be found [here](https://github.com/asreview/paper-depression-brouwer-simulation-scripts).

Output data can be found here: https://osf.io/8wa2n/. Download this data allows for running plot_only.ipynb


## Content

### data
This folder contains all input data.

`brouwer_2019.csv` - 
This folder contains data used for generating the right output.

### scripts
This folder contains a code to directly recreate results.

`RunThisScript.ipynb` - 
This jupyter notebook contains all commands and code to create the files in output.

`plot_only.ipynb` - 
This notebook can be run to produce all plots without running simulations. Data from https://osf.io/8wa2n/ needs to be downloaded to the output folder.

### output
This folder will contain data after running one of the scripts. It will contain produced h5 statefiles files, plot images, and if enabled, extracted data.

### postprocessing
This folder contains files used in processing the output data.

`h5 file processer.ipynb` - 
This script extracts labeled records from an h5 file, and writes them to train_idx.txt. In the study it was used to simulate model switching. It uses `NB_extract_classified_papers.h5` as input.

`Hijacked data processer.ipynb` - 
This script was used to explore fitting data hijacked during the classifier process. This fitting data was then used to train the CNN. Used only for exploration and has no output.

`Neural Network Optimizer.ipynb` - 
This script was used for optimizing the neural network. It can also be ignored for output as it is currently a bit messy, but kept for posterity.

## Results

`output/wide_prior_plot.png` shows resulting performance for the new CNN combined with model switching.

## License

This repository is openly published on GitHub, https://github.com/JTeijema/asreview-study-model-switching under MIT license. Therefore it is 'Open Access' and thus available for anyone. This repository will remain online for at least 10 years.

## Contact

Any questions about this repository can be send to `j.j.teijema@gmail.com`.

# Rapid protein stability prediction using deep learning representations

## Introduction
Scripts and data to repeat the analyses in Blaabjerg et al.:
[*"Rapid protein stability prediction using deep learning representations"*](https://www.biorxiv.org/content/10.1101/2022.07.14.500157v1).

## Code
Overview of files:<br>
`src/run_pipeline.py` - main script for repeating the analyses in paper.<br/>
`src/rasp_model.py` - classes for models and data.<br/>
`src/helpers.py` - various helper functions.<br/>
`src/visualization.py` - functions for plotting results.<br/>
`src/pdb_parser_scripts/` - scripts for parsing PDBs.<br/>

## Installation
Tested on Linux using Miniconda.

1. Clone this repository.

2. Install and activate conda environment with requirements:<br> 
`conda create --name rasp-model python=3.6`<br>
`conda activate rasp-model`<br>
`conda install pyyaml pandas scipy numpy=1.17.3 scikit-learn mpl-scatter-density pdbfixer=1.5 pytorch=1.2.0 cudatoolkit=10.0 biopython=1.72 openmm=7.3.1 matplotlib=3.1.1 seaborn ptitprince dssp vaex -c salilab -c omnia -c conda-forge -c anaconda -c defaults`

3. Install reduce in the right directory. This program is used by the parser to add missing hydrogens to the proteins.<br/>
`cd src/pdb_parser_scripts`<br/>
`git clone https://github.com/rlabduke/reduce.git` <br/>
`cd reduce/`<br/>
`make`; `make install` # This might give an error but provides the reduce executable in this directory.

4. Download the data file `df_rasp_gnomad_clinvar.csv` (latest version) from https://zenodo.org/record/6835878#.YtCFlC8RpQJ and add it to the directory `data/test/GnomAD_ClinVar/`.

## Execution
Execute the pipeline using `src/run_pipeline.py`.

## RaSPLab
The RaSP model can be used in [Colab](https://colab.research.google.com/) using this [link](https://colab.research.google.com/github/KULL-Centre/_2022_ML-ddG-Blaabjerg/blob/main/RaSPLab.ipynb).

## Acknowledgements
Parts of the code - specifically related to the 3D CNN model - was developed by Maher Kassem and Wouter Boomsma. We thank them for their contributions.

### Extra
#### License:

Source code and model weights are licensed under the Apache Licence, Version 2.0.

#### Bugs:

Please report any bugs or other issues using this repository [Github](https://github.com/KULL-Centre/_2022_ML-ddG-Blaabjerg) or contact one of the listed authors in the connected [manuscript](https://www.biorxiv.org/content/10.1101/2022.07.14.500157v1).

#### Citing this work:

*Lasse M. Blaabjerg, Maher M. Kassem, Lydia L. Good, Nicolas Jonsson, Matteo Cagiada, Kristoffer E. Johansson, Wouter Boomsma, Amelie Stein, Kresten Lindorff-Larsen (2022). Rapid protein stability prediction using deep learning representations. bioRxiv, 2022.07.*

```
@article {Blaabjerg2022.07.14.500157,
	author = {Lasse M. Blaabjerg and Maher M. Kassem and Lydia L. Good and Nicolas Jonsson and Matteo Cagiada and Kristoffer E. Johansson and Wouter Boomsma and Amelie Stein and Kresten Lindorff-Larsen},
	title = {Rapid protein stability prediction using deep learning representations},
	year = {2022},
	doi = {10.1101/2022.07.14.500157},
	URL = {https://www.biorxiv.org/content/early/2022/07/15/2022.07.14.500157},
	eprint = {https://www.biorxiv.org/content/early/2022/07/15/2022.07.14.500157.full.pdf},
	journal = {bioRxiv}
}
```
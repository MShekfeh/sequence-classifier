# Sequence Classifier — Open vs Closed Chromatin

## Biological question

Can a 1D CNN learn to distinguish open chromatin regulatory sequences
from closed chromatin regions using DNA sequence alone?

## Data

* Reference genome: hg38
* Positive sequences: 48,814 ENCODE DNase-seq peaks (open chromatin)
* Negative sequences: 48,814 random genomic regions (closed chromatin)
* Sequence length: 200bp centered on each peak

## Methods

* One-hot encoding: 4 x 200 matrix per sequence
* Model: 1D CNN (Week 4)
* Evaluation: AUROC, AUPR, saliency maps (Week 4)

## Results

*To be filled* 

## Setup

```bash
conda env create -f environment.yml
conda activate genomics-ml
```


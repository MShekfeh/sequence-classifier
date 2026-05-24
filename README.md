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
* Evaluation: AUROC, AUPR, saliency maps 

## Results

*Experiment                  AUROC  AUPR   Key finding* 



*Random negatives            0.69   0.66   Partial GC content signal*



*GC-matched negatives        0.68   0.68   Pure sequence signal*



*GC-matched + class weights 0.68    0.67   Ceiling confirmed at \~0.68*



*The biological conclusion: A local sequence model sees a ceiling at \~0.68 AUROC for chromatin accessibility.* 

*The missing signal comes from cellular context — TF availability and methylation state — that sequence alone cannot encode.* 



*A 3-layer 1D CNN trained on 200bp DNase-seq sequences achieves 0.68 AUROC for chromatin accessibility prediction. Performance is robust to negative set design (random vs GC-matched) and class weighting, suggesting the ceiling reflects fundamental limitations of local sequence context rather than training dynamics.* 



```bash
conda env create -f environment.yml
conda activate genomics-ml
```


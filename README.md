# Shotgun Metagenomics Analysis Pipeline

This project presents an end-to-end bioinformatics workflow for processing shotgun metagenomic sequencing data, from raw FASTQ files to taxonomic classification, statistical analysis, and visualization.

## 🧪 Workflow Summary

1. **Quality Control**
   - Performed with [FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)
   - Identified and removed low-quality reads and adapter contamination using [Trimmomatic](http://www.usadellab.org/cms/?page=trimmomatic)

2. **Host Read Removal**
   - Aligned to the human reference genome (hg38) using [BWA](http://bio-bwa.sourceforge.net/)
   - Unmapped reads extracted with [SAMtools](http://www.htslib.org/)

3. **Taxonomic Classification**
   - [Kraken2](https://ccb.jhu.edu/software/kraken2/) used to classify microbial reads
   - [Bracken](https://ccb.jhu.edu/software/bracken/) used to estimate abundance at species level

4. **Statistical Analysis & Visualization**
   - Python scripts used to:
     - Merge Bracken output
     - Calculate Shannon Index
     - Perform t-test for group comparisons
     - Visualize results using heatmaps and volcano plots

## 📂 Scripts

- `2_merge_abundance.py` — Combine Bracken species output
- `3_shanon_index.py` — Compute diversity indices
- `4_t-test.py` — Perform comparative analysis between groups
- `5_heatmap.py` — Plot heatmap of species abundance
- `6_volcano_plot.py` — Create volcano plot of differentially abundant taxa

## 📊 Outputs

- Species-level abundance tables
- Diversity index results
- Differential abundance plots
- Heatmap and volcano visualizations

## 💻 Tools & Technologies

- FastQC
- Trimmomatic
- BWA
- SAMtools
- Kraken2
- Bracken
- Python (pandas, matplotlib, seaborn)
- Bash

## 📎 Dataset

- Public SRA samples:
  - SRR3950487, SRR3950486
  - SRR5898915, SRR5898917

---

## 🤝 Acknowledgments

This project was developed as part of a metagenomics research study focused on microbial profiling from human-associated datasets.

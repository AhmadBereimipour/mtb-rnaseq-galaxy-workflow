# Galaxy-Based RNA-Seq Analysis Workflow for Mycobacterium tuberculosis

This repository provides reproducible materials for a Galaxy-based RNA-seq analysis workflow using the publicly available Mycobacterium tuberculosis H37Rv dataset GSE126286.

## Study design

The analysis compares three wild-type control samples with three RNase J mutant samples.

| Sample | GEO accession | Condition | Replicate |
|---|---|---|---|
| ctrl_1 | GSM3595703 | control | 1 |
| ctrl_2 | GSM3595704 | control | 2 |
| ctrl_3 | GSM3595705 | control | 3 |
| mutant_1 | GSM3595706 | mutant_RNJ | 1 |
| mutant_2 | GSM3595707 | mutant_RNJ | 2 |
| mutant_3 | GSM3595708 | mutant_RNJ | 3 |

## Workflow summary

The RNA-seq workflow was performed in Galaxy using the following steps:

1. Retrieve paired-end FASTQ files from EBI/ENA
2. Organize and verify R1/R2 paired-end files
3. Trim reads using Trimmomatic
4. Assess read quality using FastQC
5. Align reads to the Mycobacterium tuberculosis H37Rv reference genome using HISAT2
6. Upload the matching GFF/GTF annotation file from NCBI RefSeq
7. Quantify gene-level read counts using FeatureCounts
8. Perform differential expression analysis using DESeq2
9. Export normalized counts, statistical results, and plots

## Reference genome and annotation

Organism: Mycobacterium tuberculosis H37Rv  
Reference assembly: ASM19595v2  
Annotation source: NCBI RefSeq  
Annotation format: GFF/GTF  

## Data availability

Raw FASTQ files are not stored in this repository because they are large and publicly available through GEO/ENA/SRA under accession GSE126286. This repository contains sample metadata, accession information, workflow documentation, Galaxy workflow files, count tables, DESeq2 outputs, normalized count matrices, and visualization-ready files.

## Repository contents

- metadata/: sample metadata, accession list, and reference genome information
- workflow/: Galaxy workflow file and workflow documentation
- results/featurecounts/: FeatureCounts count and summary files
- results/deseq2/: DESeq2 result files and normalized/transformed count matrices
- results/figures/: workflow figure and analysis visualizations
- docs/: screenshots, FastQC reports, and additional notes

## Main outputs

- FeatureCounts raw count table
- FeatureCounts summary file
- DESeq2 differential expression result table
- DESeq2 normalized count matrix
- rLog- and VST-transformed count files
- DESeq2 plot outputs
- Workflow figure

## Reproducibility

The Galaxy workflow file can be imported into Galaxy and used to reproduce the analysis after retrieving the raw paired-end FASTQ files from public sequence repositories.

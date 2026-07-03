# Galaxy workflow steps

1. Retrieve paired-end FASTQ files from EBI/ENA using the selected GSE126286 samples.
2. Rename and organize R1/R2 files.
3. Run Trimmomatic using paired-end input.
4. Run FastQC on trimmed paired reads.
5. Align trimmed paired reads using HISAT2.
6. Upload the matching GFF/GTF annotation file.
7. Run FeatureCounts using HISAT2 BAM files and the uploaded annotation file.
8. Run DESeq2 using FeatureCounts count files.
9. Export DESeq2 result table, normalized counts, transformed counts, and plots.

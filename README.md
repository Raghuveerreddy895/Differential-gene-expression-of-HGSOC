🧬 Data Processing Overview
📥 Data Curation
RNA-Seq data was curated from the Gene Expression Omnibus (GEO) database. GEO accession IDs were used to retrieve corresponding SRA (Sequence Read Archive) entries. The raw FASTQ files were downloaded using the SRA Toolkit via ENA (European Nucleotide Archive) links.

🔬 Data Preprocessing
Quality Control
Raw sequencing reads were evaluated using FastQC to assess quality metrics, including base quality scores, GC content, and adapter contamination.

Trimming
Low-quality bases and adapter sequences were removed using Trimmomatic, a Java-based tool optimized for quality trimming of Illumina reads.

🧭 Read Alignment
High-quality reads were aligned to the human reference genome (GRCh38) using Bowtie2, a fast and memory-efficient aligner.

The resulting SAM files were converted into BAM format using SAMtools for downstream processing.

🧮 Gene Quantification
Gene-level read counts were generated from the BAM files using featureCounts, with the GENCODE v44 annotation file (gencode.v44.annotation.gtf) as the gene model reference.

⚖️ Data Normalization & Differential Expression
The raw count matrix was exported to a CSV file and loaded into DESeq2 in R.

DESeq2 was used to normalize the data and identify differentially expressed genes (DEGs).

📊 Visualization
Volcano plots and heatmaps were created to visualize the DEGs and expression patterns across samples.

📄 Reporting
The final results, including normalized counts and DEG statistics, were saved as CSV files for further interpretation and sharing.


📚 References
•	FastQC
Andrews, S. (2010). FastQC: a quality control tool for high throughput sequence data. http://www.bioinformatics.babraham.ac.uk/projects/fastqc/
•	Trimmomatic
Bolger, A. M., Lohse, M., & Usadel, B. (2014). Trimmomatic: a flexible trimmer for Illumina sequence data. Bioinformatics, 30(15), 2114–2120. https://doi.org/10.1093/bioinformatics/btu170
•	Bowtie2
Langmead, B., & Salzberg, S. L. (2012). Fast gapped-read alignment with Bowtie 2. Nature Methods, 9(4), 357–359. https://doi.org/10.1038/nmeth.1923
•	featureCounts
Liao, Y., Smyth, G. K., & Shi, W. (2014). featureCounts: an efficient general-purpose program for assigning sequence reads to genomic features. Bioinformatics, 30(7), 923–930. https://doi.org/10.1093/bioinformatics/btt656
•	DESeq2
Love, M. I., Huber, W., & Anders, S. (2014). Moderated estimation of fold change and dispersion for RNA-seq data with DESeq2. Genome Biology, 15(12), 550. https://doi.org/10.1186/s13059-014-0550-8


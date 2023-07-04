# Sample Data for RiboFlow

A complete set of sample files to test and try 
[RiboFlow](https://github.com/ribosomeprofiling/riboflow) pipeline. 

All files and references herein are coming from the human genome.

## Required and Optional Files

Not all files are required by RiboFlow. 

**Required File Types:**
* Fastq files from ribosome profiling experiments
* Annotation
* Transcriptome Reference
* Filter  

**Optional File Types:**
* Fastq files from RNA-Seq experiments
* Metadata
* Genome Reference
* Post-Genome Reference

## Fastq
Includes raw reads for ribosome profiling and RNA-Seq data.
Each sample has two fastq files. 
All fastq files are obtained by taking a subset of reads from
the publicly available data
([NCBI GEO accession number ](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE185732) published in  [Ozadam, Tonn, Han, et.al., ](https://www.nature.com/articles/s41586-023-06228-9)
and 
[NCBI GEO accession number GSE65778](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE65778) )
published in 
[Sidrauski et. al.](https://elifesciences.org/articles/05033).  

_Note that RNA-Seq data is optional for RiboFlow and .ribo files._  

## Annotation

The tsv file contains transcript lengths.
The bed file contains region boundaries; CDS, 5'UTR and 3'UTR.


## Metadata

Contains metadata for the ribo files in yaml format.  

_Metadata is optional for RiboFlow and ribo files._  

## Transcriptome Reference

Bowtie2 index files for the transcriptome.
The actual output of the RiboFlow pipeline, i.e., ribo files, is obtained using the reads that are mapped to the transcriptome reference.


## Filter

Bowtie2 index coming from the 
filter sequences which are mainly ribosomal and tRNAs.


## Genome

A mock Hisat2 reference in place of the entire genome. 
For actual data analysis, users should download 
the complete human genome such as hg38.
Links are avaialble at
[Hisat2 website](https://ccb.jhu.edu/software/hisat2/manual.shtml).

Note that this reference has **no effect on the output ribo files** since the reads are
mapped to the transcriptome to generate ribo files. The reads which aren't map to the 
transcriptome are mapped to genome. 

_Genomic Reference is an optional parameter for RiboFlow._

## Post-Genome

A sample bowtie2 reference file as post-genome reference.

Reads that are not mapped to the genome are mapped to post-genome reference.

_Similar to the case of genome, post-genome parameter is optional and it has **no effect
on the output ribo files**._



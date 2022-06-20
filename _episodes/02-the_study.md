---
title: "Our case-study"
teaching: 10
exercises: 0
questions:
- "What is the biological question?"
- "What is the experimental design?"
- "What is the data?"
- "RNA-Seq analysis"


objectives:
- "Discuss how to address a biological question using RNA-Seq"
keypoints:
- XXX
---


### The study
Knockout mouse model to study Williams-Beuren Syndrome (WBS)

<figure>
  <img src="{{ page.root }}/fig/the_study.png" style="margin:10px;height:150px"/>
  </figure><br>


### Williams-Beuren Syndrome (WBS)
It is a genetic disorder associated with multisystemic abnormalities such as 
- Facial dysmorphology
- Intellectual disability
- Cardiovascular abnormalities

WBS is caused by a hemizygous microdeletion involving up to 28 genes in chromosome 7q11.23. 
Two evolutionary-related transcription factors, GTF2I and GTF2IRD1 are implicated as prime candidates for the cause of the facial dysmorphology.


### Experimental design
To improve our understanding of this disease (WBS) ,[Corley et al. 2016](https://pubmed.ncbi.nlm.nih.gov/27295951/) created a Gtf2ird1 knockout mouse model of this disease.

<figure>
  <img src="{{ page.root }}/fig/experimental_design.png" style="margin:10px;height:150px"/>
 </figure><br>
 
- The group had 3 wildtype healthy mice, and 3 mice in which the Gtf2ird1 gene was knocked out 
 
### Experimental question
- Which genes are upregulated or downregulated between the two treatment groups (WT and knockout mice)?
- Do the regulated genes relate to the disease phenotype?
 

### Sequencing data 
- Sequencing was performed on the Illumina HiSeq2000 platform as 100 base pair reads.
- The raw sequence files are provided in the [FASTQ](https://www.drive5.com/usearch/manual7/fastq_files.html) format.
- The sequencing data  (sub-setted to chr 18 region) to ensure the jobs complete in an appropriate time for the course when doing part 1 of the analysis.


### The analysis 
<br>**Part-1: Demonstrate the use of nfcore-rnaseq pipeline** 
- This involves converting the sequencing data to count matrix. 
- The available virtual machine instances to be used for this purpose are of a fixed size (16 CPU and 64GB RAM).
- So, the data used in part 1 of today's workshop is a small sub-set of the full data.
- The sequence data has been reduced (subsetted) and it represents a very specific region of ** chromsome 18 ** of the mouse genome.
- We will use this subsetted files for a quick processing to generate a count-matrix (approx. 15 min processing time).


<br>**Part-2: Demonstrate the use of RStudio for downstream analysis**
- A pre-processed count matrix which represents the complete dataset (downloaded from the [original paper](https://pubmed.ncbi.nlm.nih.gov/27295951/)) will be used for downstream functional enrichment analysis.
  

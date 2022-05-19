---
title: "The study"
teaching: 10
exercises: 0
questions:
- "What is the biological question?"
- "What is the experimental design?"
- "What is the data? "


objectives:
- "Discuss how to address a biological question using RNA-Seq"
keypoints:
- XXX
---


## The study
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


## Experimental design
To improve our understanding of this disease (WBS) , [Corley et al. 2016](https://pubmed.ncbi.nlm.nih.gov/27295951/) created a Gtf2ird1 knockout mouse model of this disease.

<figure>
  <img src="{{ page.root }}/fig/experimental_design.png" style="margin:10px;height:150px"/>
 </figure><br>
 
## Experimental question
- Which genes are upregulated or downregulated in our knockout mice?
- Do the regulated genes relate to the disease phenotype?
 

## Sequencing data 
- As discussed, the raw sequence files are provided in the [FASTQ](https://www.drive5.com/usearch/manual7/fastq_files.html) format.

- **Analysis Part-1**: The available virtual machine instances are of a fixed size (16 CPU and 64GB RAM)
- The data used in today's workshop is a small sub-set of the full data.
- The sequences represents a very specific region of ** chromsome 18 ** of the mouse genome.
- We will use this subsetted files for quick processing to generate a count-matrix.


- **Analysis Part-2**: A pre-processed count matrix which represents the complete dataset (downloaded from the [original paper](https://pubmed.ncbi.nlm.nih.gov/27295951/)) will be used for downstream functional analysis.
  

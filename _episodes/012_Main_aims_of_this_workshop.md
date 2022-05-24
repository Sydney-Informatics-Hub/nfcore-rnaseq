---
title: "What are the main aims of this workshop?"
teaching: 10
exercises: 0
questions:
- "Why sequence RNA?"
- "How to do RNASeq analysis?"
- "Can tools such as Nextflow be used to efficient pipelining of RNASeq analysis ?"
- "How does 'nfcore-rnaseq' work?"
- "How to run 'nfcore-rnaseq' pipeline on a virtual machine?"
- "How to use R/RStudio for downstream data processing and visualisation?" 

objectives:
- "Executing nextflow pipeline 'nfcore-rnaseq' on a virtual machine (VM) instance"
keypoints:
- XXX
---

### RNASeq analysis
- Why sequence RNA?
- What is RNASeq analysis?
- How and where to easily run RNASeq analysis?

### Steps involved in RNASeq analysis
- Basic RNASeq analysis pipeline 
- Sequencing to read-count matrix using nfcore-rnaseq pipeline - How? 
- Read-count matrix to differential expression (DE) analysis using RStudio - How?

### STEP 1: Sequencing to read-count matrix
- What is a Fastq format?
- What is nextflow?
- What is nfcore-rnaseq?

### Pawsey-Nimbus virtual machine: A platform to run nfcore-rnaseq pipeline 
- What are the trainee VMs from Pawsey
- How to log on to a trainee VM?
 
### Run nfcore-rnaseq on 'Pawsey-Nimbus VM instance'
- What are basic steps involved?
- What is the input?
- What is the output ? A read-count matrix
- Where do we go from here? - Exporting the read-count matrix

### STEP2: Read-count matrix to differential expression (DE) analysis
- Why use 'R'  environment for differential expression analysis?
- A quick introduction to R and RStudio

### Identifying DE genes
- Importing the read-count matrix in R
- Pre-processing steps
- Multivariate analysis (PCA plots etc)
- Generate DE genes

### Functional enrichment anaylsis
- What is Gene ontology?
- What is enrichment analysis?
- How to perform enrichment analysis in R? 

___
**Notes**   
<sup id="f1">1[↩](#a1)</sup> Here is a list of ['nfcore pipelines'](https://nf-co.re/pipelines/).

___
<br>



{% include links.md %}
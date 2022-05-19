---
title: "Introduction to RNA-Seq"
teaching: 10
exercises: 0
questions:
- "What is RNA-Seq?"
- "RNA-Seq : Sample preparation, RNA library construction, and sequencing? "
- "RNA-Seq analysis : Basic workflow"
objectives:
- "Learn how to perform RNASeq analysis"
keypoints:
- XXX
---

This episode gives an overview of  **RNAS-seq** analysis . 

## Introduction to RNA-Seq

- RNA sequencing (RNA-Seq) is a revolutionary method used to study the transcriptome. 
- It is a highly sensitive and accurate tool for for simultaneously measuring and comparing the expression of tens of thousands of genes in multiple samples.
- It allows the researcher to interrogate the transcriptome under different disease states, in response to therapeutics, under different environmental conditions etc.

## RNA-sample to sequencer ... 

<figure>
  <img src="{{ page.root }}/fig/sample_to_sequencer.png" style="margin:10px;height:300px"/>
    <figcaption> Sample to sequencer </figcaption>
</figure><br>
  
- Identify the biological question.  
- Experiment design - e.g. 'Treated' versus 'Untreated' samples
- Isolating RNA, preparing RNA library (Single/Paired-end)
- Sequencing 

## How does RNA sequencing work?
  <figure>
<img src="{{ page.root }}/fig/chemistry.png" style="margin:10px;height:350px"/>
  <figcaption> RNA/DNA library construction </figcaption>
</figure><br> 

## Stranded vs Unstranded protocols
- There are two types of RNA sequencing sample preparation protocols: [stranded and unstranded](https://www.ecseq.com/support/ngs/how-do-strand-specific-sequencing-protocols-work). 
- It is important to know which you have in the downstream analysis.
- Stranded protocols retain strandedness information (whether your RNA was transcribed from the forward or reverse strand). 
- Unstranded protocols do not retain this information.

<figure>
<img src="{{ page.root }}/fig/Strand-Specific-Protocols-2.png" style="margin:10px;height:350px"/>
  <figcaption> Comparison of mapped reads from an unstranded/stranded library </figcaption>
</figure><br> 

## Experimental Design
- A **design** which provides statistically sound results and which can provide answers to the experimental questions.
- **Replicates**   : Technical vs Biological.
- **Data amount/type** : Read length, single vs paired end, 
                    stranded vs unstranded, desired depth of coverage.

<figure>
  <img src="{{ page.root }}/fig/Design.png" style="margin:10px;height:350px"/>
  <figcaption> RNA-Seq analysis workflow </figcaption>
</figure><br>


## RNA-Seq Analysis - basic workflow overview

<figure>
  <img src="{{ page.root }}/fig/rnaseq_workflow.png" style="margin:10px;height:350px"/>
  <figcaption> RNA-Seq analysis workflow </figcaption>
</figure><br>

- Multiple steps are involved in the analysis of RNA-Seq data. 
- The first step is sequencing reads (Output format - [FASTQ](https://www.drive5.com/usearch/manual7/fastq_files.html) files). 
- Pre-processing for quality control (QC).
- Aligning reads to a reference genome. 
- The number of reads mapped to each gene can then be counted. This results in a table of counts, which is what we perform statistical analyses on to determine differentially expressed genes and pathways.






{% include links.md %}

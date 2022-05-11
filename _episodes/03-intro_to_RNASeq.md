---
title: "Introduction to RNASeq"
teaching: 10
exercises: 10
questions:
- "What is RNASeq?"
- "What are the steps to check sequencing quality?"
- "How can we align the RNASeq read-data to the reference and visualise the alignments?"
- "How can we perform Differential Expression Analysis?"
objectives:
- "Learn how to perform RNASeq analysis"
keypoints:
- XXX
---

This episode gives an overview of  **RNAS-seq** analysis . 

## Introduction to RNA-Seq

- RNA sequencing (RNA-Seq) is revolutionizing the study of the transcriptome. 
- A highly sensitive and accurate tool for measuring expression across the transcriptome.
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

## RNA-Seq Analysis - basic workflow overview

<figure>
  <img src="{{ page.root }}/fig/rnaseq_workflow.png" style="margin:10px;height:350px"/>
  <figcaption> RNA-Seq analysis workflow </figcaption>
</figure><br>


## Differential Expression Analysis
- Obtaining the count data from nfcore-rnaseq.
- Differential expression analysis using DESeq2.
- How do we perform functional enrichment analysis using R/RStudio?






{% include links.md %}

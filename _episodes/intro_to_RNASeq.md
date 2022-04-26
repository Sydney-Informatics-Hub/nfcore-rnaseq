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

This episode is gives an overview to  **RNASeq** analysis . 

<figure>
  <img src="{{ page.root }}/fig/rnaseq_workflow.png" style="margin:10px;height:300px"/>
  <figcaption> A cartoon scheduler -- compute jobs will try to be resourced as efficiently as possible! </figcaption>
</figure><br>


## Introduction ?
- What is RNASeq?
- How is the transcriptome sequenced?
- Experimental design considerations
- Analysis workflow overview

## Nextflow nfcore-rnaseq
- What is nfcore-rnaseq?
- How does nfcore-rnaseq streamline the RNASeq analysis?
- Where can we run the nfcore-rnaseq pipeline?
- What are the computations requirements for nfcore-rnaseq?
- What is the output from nfcore-rnaseq?


## Differential Expression Analysis
- Obtaining the count data from nfcore-rnaseq.
- Differential expression analysis using DESeq2.
- How do we perform functional enrichment analysis using R/RStudio?






{% include links.md %}

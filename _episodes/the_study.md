---
title: "The study"
teaching: 10
exercises: 10
questions:
- "What is the biological question?"
- "Experimental design?"
- "What is the data? "


objectives:
- "Understand the biological question and how RNASeq is an appropriate tool for this analysis ..."
keypoints:
- XXX
---


## The study
Knockout mouse model to study Williams-Beuren Syndrome


<figure>
  <img src="{{ page.root }}/fig/the_study.png" style="margin:10px;height:200px"/>
  <figcaption> Central dogma of molecular biology </figcaption>
</figure><br>


(WBS), is a rare disease found in people
- distinctive facial features
- intellectual disability
- cardiovascular abnormalities


## Experimental design
To improve our understanding of this disease (WBS) , Corley et al. 2016 created a knockout mouse model of this disease.

<figure>
  <img src="{{ page.root }}/fig/experimental_design.png" style="margin:10px;height:300px"/>
  <figcaption> Central dogma of molecular biology </figcaption>
</figure><br>

## Sequencing data (subset)
- Raw sequence files are proivide in FASTQ format.
- The data used in today's workshop is a small subset of the full sequencing (fastq) files.
- The sequences represents a very specific region of ** chromsome 18 ** of the mouse genome.
- The virtual machine instances available for training are of limited size (16 CPU and 64GB RAM)
- We will use this subsetted files for quick processing.
- A pre-processed count matrix which represents the complete datasets (downloaded from the original paper) will be used for downstream functional analysis.
  

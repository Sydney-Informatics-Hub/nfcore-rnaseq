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

This episode gives an overview of  **RNA-Seq** analysis . 

### Introduction to RNA-Seq

- RNA sequencing (RNA-Seq) is a revolutionary method used to study the transcriptome. 
- It is a highly sensitive and accurate tool for for simultaneously measuring and comparing the expression of tens of thousands of genes in multiple samples.
- It allows the researcher to interrogate the transcriptome under different disease states, in response to therapeutics, under different environmental conditions etc.
- As sequencing costs have decreased, using RNA-Seq to simultaneously measure the expression of tens of thousands of genes for multiple samples has never been easier.


### RNA-sample to sequencer ... 

<figure>
  <img src="{{ page.root }}/fig/sample_to_sequencer.png" style="margin:10px;height:300px"/>
    <figcaption> Sample to sequencer </figcaption>
</figure><br>
  
- There are many steps involved in an RNA-Seq experiment.
- The first is to identify the biological question which can be interrogated using RNA-Seq analysis.  
- Identify the experiment design and the underlying conditions of interest e.g. 'Treated' versus 'Untreated' samples.
- Next step is to isolating the RNA and prepare the RNA library using either single-end or paired-end reads.
- Sequencing the samples.

### The Experimental Design
- Designing a RNA-Seq experiment is extremely crucial to the analysis.
- A **design** provides statistically sound results and  can provide answers to the experimental questions.
- **Replicates**   : Technical vs Biological.
- **Data amount/type** : Read length, single vs paired end, 
                         stranded vs unstranded, desired depth of coverage.
<figure>
  <img src="{{ page.root }}/fig/Design.png" style="margin:10px;height:350px"/>
  <figcaption> RNA-Seq analysis workflow </figcaption>
</figure><br>



### How does RNA sequencing work?
  <figure>
<img src="{{ page.root }}/fig/chemistry.png" style="margin:10px;height:350px"/>
  <figcaption> RNA/DNA library construction </figcaption>
</figure><br> 

### Stranded vs Unstranded protocols
- There are two types of RNA sequencing sample preparation protocols: [stranded and unstranded](https://www.ecseq.com/support/ngs/how-do-strand-specific-sequencing-protocols-work). 
- It is important to know whoch protocol was used in your experiment for your downstream analysis.
- Stranded protocols retain strandedness information (whether your RNA was transcribed from the forward or reverse strand). 
- Unstranded protocols do not retain this information.
- We will do a quick analysis to identify the strandedness 

<figure>
<img src="{{ page.root }}/fig/Strand-Specific-Protocols-2.png" style="margin:10px;height:350px"/>
  <figcaption> Comparison of mapped reads from an unstranded/stranded library </figcaption>
</figure><br> 











{% include links.md %}

---
title: "Welcome to Nextflow nfcore-rnaseq workshop"
teaching: 10
exercises: 0
questions:
- "Who are we : Australian BioCommons, Sydney Informatics Hub, Pawsey Supercomputing Center"
- "Why RNASeq analysis?"
- "What is Nextflow?"  
- "How to run 'nfcore-rnaseq'  pipeline on a 'Pawsey Nimbus VM instance'"
- "How to perform downstream data-analysis using R/RStudio?" 


objectives:
- "Executing nextflow pipeline 'nfcore-rnaseq' on a virtual machine (VM) instance"
keypoints:
- XXX
---

### Australian BioCommons
The Australian BioCommons is an ambitious new [digital infrastructure capability](https://www.biocommons.org.au/) that is enhancing Australian research in its ability to understand the molecular basis of life across environmental, agricultural and biomedical science.

<figure>
  <img src="{{ page.root }}/fig/Australian_Biocommons.png" style="margin:10px;height:350px"/>
  </figure><br>

### The Sydney Informatics Hub
The Sydney Informatics Hub (SIH) is a _[Core Research Facility](https://sydney.edu.au/research/facilities.html)_ of the University of Sydney. They provide support, training, and expertise in research data management, statistics, data science, software engineering, simulation, visualisation, bioinformatics, and research computing.

<figure>
  <img src="{{ page.root }}/fig/SIH.png" style="margin:10px;height:300px"/>
  </figure><br>


### Pawsey Supercomputing center

The [Pawsey Supercomputing Research Centre](https://pawsey.org.au/) is an unincorporated joint venture between CSIRO, Curtin University, Edith Cowan University, Murdoch University and The University of Western Australia.  It is supported by the Western Australian and Federal Governments. The Centre is one of two, Tier-1, High Performance Computing facilities in Australia, whose primary function is to accelerate scientific research for the benefit of the nation.

<figure>
  <img src="{{ page.root }}/fig/Pawsey_supercomputing_center.png" style="margin:10px;height:300px"/>
  </figure><br>


## RNASeq analysis
- Why sequence RNA?
- What is RNASeq analysis?


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

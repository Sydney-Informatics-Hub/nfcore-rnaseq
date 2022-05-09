---
title: "Introduction to nfcore-rnaseq"
teaching: 10
exercises: 10
questions:
- "What is nfcore-rnaseq"

objectives:
- "Introduction to nextflow and nfcore"
keypoints:
- XXX
---

This episode is gives an overview of the nfcore-rnaseq pipeline.

## nfcore-rnaseq

- What is nfcore-rnaseq?

~~~
nfcore-rnaseq is a bioinformatics pipeline that can be used to analyse RNA sequencing data obtained from organisms with a reference genome and annotation.
~~~



- The workflow in nfcore-rnaseq

<figure>
  <img src="{{ page.root }}/fig/nf-core-rnaseq_metro_map_grey.png" style="margin:10px;height:200px"/>
  <figcaption> nfcore-rnaseq pipeline summary </figcaption>
</figure><br>

~~~
The pipeline uses STAR, RSEM, HISAT2 or Salmon with gene/isoform counts and extensive quality control.
~~~

- Where can we run the nfcore-rnaseq pipeline?
~~~
Local machine ?
HPC (Usyd-Artemis, NCI-GADI)
VM (Pawsey Nimbus VM)
~~~

- What are the computations requirements for nfcore-rnaseq?
~~~



~~~

- What is the output from nfcore-rnaseq?
~~~
~~~

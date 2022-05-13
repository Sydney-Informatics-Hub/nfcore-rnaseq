---
title: "Run nfcore-rnaseq on a Nimbus instance"
teaching: 10
exercises: 0
questions:
- "Create/use a design samplesheet"
- "How to start a basic nfcore-rnaseq run!"
- "Usage options"

objectives:
- "Understanding how to run the nfcore-rnaseq on Nimbus"

keypoints:

---
This episode introduces the user to the basic excecution steps of the nfcore-rnaseq pipeline on the Nimbus instance


## Samplesheet (mandatory) input
You will need to create a [samplesheet](https://nf-co.re/rnaseq/3.7/usage#samplesheet-input) with information about the samples you would like to analyse before running the pipeline. Use this parameter to specify its location. It has to be a comma-separated file with 4 columns, and a header row as shown in the examples below. 

<figure>
  <img src="{{ page.root }}/fig/elaborate_samplesheet.png" style="margin:10px;height:300px"/>
</figure><br>


<figure>
  <img src="{{ page.root }}/fig/samplesheet_description.png" style="margin:10px;height:300px"/>
</figure><br>

The samplesheet required for today's analysis is a lot simpler. It is already created and placed in the folder XXX.


## Quick Start


Create a samplesheet
samplesheet_template

~~~
nextflow run nf-core/rnaseq \
    --input samplesheet.csv \
    --outdir <OUTDIR> --genome GRCh38 
    -profile <docker/singularity/podman/shifter/charliecloud/conda/institute>
~~~




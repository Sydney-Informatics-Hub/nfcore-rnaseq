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


## Step1: Samplesheet (mandatory) input
You will need to create a [samplesheet](https://nf-co.re/rnaseq/3.7/usage#samplesheet-input) with information about the samples you would like to analyse before running the pipeline. Use this parameter to specify its location. It has to be a comma-separated file with 4 columns, and a header row as shown in the examples below. 

<figure>
  <img src="{{ page.root }}/fig/elaborate_samplesheet.png" style="margin:10px;height:200px"/>
</figure><br>


<figure>
  <img src="{{ page.root }}/fig/samplesheet_description.png" style="margin:10px;height:200px"/>
</figure><br>

The samplesheet required for today's analysis is a lot simpler, as we are using single-end reads. 
This samplesheet is already created and placed in the folder XXX.


## Quick Start
~~~
nextflow run nf-core/rnaseq \
    --input samplesheet.csv \
    --outdir <OUTDIR> --genome GRCh38 
    -profile <docker/singularity/podman/shifter/charliecloud/conda/institute>
~~~

- Note that some form of configuration will be needed so that Nextflow knows how to fetch the required software. This is usually done in the form of a config profile. 
- The pipeline comes with config profiles called docker, singularity, podman, shifter, charliecloud and conda which instruct the pipeline to use the named tool for software management.
- Please check [nf-core/configs](https://github.com/nf-core/configs#documentation) to see if a custom config file to run nf-core pipelines already exists for your Institute. If so, you can simply use -profile <institute> in your command. This will enable either docker or singularity and set the appropriate execution settings for your local compute environment.

## Pre-download profiles
- We can select a specific profile such as **singularity**, and use the [nf-core](https://nf-co.re/tools/#downloading-pipelines-for-offline-use) download command to download images first, before running the pipeline. 
- Nextflow allows to store and re-use the images from a central location for future pipeline runs.

## Actual nfcore-rnaseq command

~~~
base_path=/SIH/nextflow_pipelines/nfcore/rnaseq/BioCommons_nfcoreRNASeq_workshop/resources

local_rnaseq_path=/SIH/tools_and_resources/installtions/nextflow_local

/SIH/tools_and_resources/installtions/nextflow_local/21.10.6.5660/nextflow run $local_rnaseq_path/rnaseq-3.7 \
        --input samplesheet.csv \
        --outdir results_maxcpu2 \
        --genome GRCm38 \
        -profile singularity \
        --fasta $base_path/Mouse_genomeFiles_from_sarek/genome.fa \
        --gtf $base_path/Mouse_genomeFiles_from_sarek/sarek_Mmus.gtf \
        --max_memory '64 GB' --max_cpus 2 \
        --star_index $base_path/Mouse_genomeFiles_from_sarek/STARIndex_sarekGenome/ \
        -with-report sarek_downloadedFullFastaGtf_excecution_report_maxcpu2.html \
        -with-timeline sarek_downloadedFullFastaGtf_timeline_report_maxcpu2.html -r 3.4
~~~
  
  


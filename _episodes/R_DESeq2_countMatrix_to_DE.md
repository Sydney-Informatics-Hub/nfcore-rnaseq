---
title: "Scripting with 'R' "
teaching: 10
exercises: 10
questions:
- "What is R?"
- "What is RStudio"
- "Experimental design?"

objectives:
- "use RStudio on Nimbus instance to process the count matrix from nfcore-rnaseq and geenrate list of differentially expressed genes."
keypoints:
- XXX
---

This episodes on a Nimbus instance. 

## Load R libraries
~~~
library("DESeq2")
library("edgeR")
library("limma")

library("RColorBrewer")
library("gplots")
library("ggplot2")
library("EnhancedVolcano")

library("devtools")
library("rstudioapi")

library("dplyr")
library("tibble")
library("tidyverse")

# Bioinformatics databases/formatting etc
library("biomaRt")
library("annotables")
library("org.Mm.eg.db")
library("biobroom")

# Functional analysis
library("clusterProfiler")
library("pathfindR")

#----------Set the current path as the current working directory------
current_path <- getActiveDocumentContext()$path 
setwd(dirname(current_path ))
print( getwd() )
~~~

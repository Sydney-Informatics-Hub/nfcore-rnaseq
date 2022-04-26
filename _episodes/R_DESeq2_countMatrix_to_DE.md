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


~~~
library("DESeq2")
library("RColorBrewer")
library("gplots")
library(edgeR)
library(limma)
library("devtools")
library(rstudioapi)
library("ggplot2")

library("dplyr")

library(biomaRt)
library(annotables)
library(tidyverse)
library(biobroom)
library(EnhancedVolcano)
library(clusterProfiler)
library(org.Mm.eg.db)

library("pathfindR")

library(tibble)

#----------Set the current path as the current working directory------
current_path <- getActiveDocumentContext()$path 
setwd(dirname(current_path ))
print( getwd() )
~~~

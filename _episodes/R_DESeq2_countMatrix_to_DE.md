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

## Read the combined count matrix - (Generated  using nfcore-rnaseq)
~~~
counttable<-read.delim("GSE81082_count_matrix_ENSIDs_symbols_nr.txt", header=T, row.names=1)
View(counttable)

# ENSG as identifier
subsetOfColumns <- c("WT1","WT2","WT3","KO1","KO2","KO3","Symbol")
counttable <- counttable[subsetOfColumns]
View(counttable)


# Gene Symbol as identifier
counttable<-counttable[,c("Symbol","WT1","WT2","WT3","KO1","KO2","KO3")]
row.names(counttable) <- NULL


#Column name (GeneSymbol to rowname)
rownames(counttable) <- counttable$Symbol
counttable<-counttable[,c("WT1","WT2","WT3","KO1","KO2","KO3")]
View(counttable)


## Filter to remove lowly expressed genes - Retian only those with more than 1 count-per-million in at least 4 (out of 6) samples  
keep <-rowSums(cpm(counttable)>1) >=4
data <-counttable[keep, ]
dim(data)

counttable<-data
~~~

## Use DeSeq2 for 'Differential Expression' analysis
~~~
meta <- data.frame(row.names=colnames(counttable),condition=c("Wild","Wild","Wild","KO","KO","KO"))
meta$condition ~ relevel(meta$condition, ref="Wild")

## Make design matrix
condition ~ relevel(factor(meta$condition), ref="Wild")
dds<-DESeqDataSetFromMatrix(countData=counttable,colData=meta,design=~condition)

dds <- estimateSizeFactors(dds)

# Transform for PCA
vsd <- vst(dds, blind=FALSE)
z<-plotPCA(vsd, intgroup=c("condition"))
z+ geom_text(aes_string(x = "PC1", y = "PC2", label = "name"),color = "black",size = 4)


# Writing normalised counts
normalised_counts<-counts(dds,normalized=TRUE)
write.table(normalised_counts, "normalised_counts_DeSeq2.tab", sep="\t", col.names=NA, quote=F)

~~~
<figure>
  <img src="{{ page.root }}/fig/PCA.png" style="margin:10px;height:200px"/>
  <figcaption> Central dogma of molecular biology </figcaption>
</figure><br>



## Generate a list of DE genes

~~~
###### WT2 vs KO2 ###### 
subsetOfColumns <- c("WT1","WT2","WT3","KO1","KO2","KO3")
counttable_comparison_Wild_vs_KO_FULLMatrix <- counttable[subsetOfColumns]
View(counttable_comparison_Wild_vs_KO_FULLMatrix)


meta_comparison_Wild_vs_KO_FULLMatrix <- data.frame(row.names=colnames(counttable_comparison_Wild_vs_KO_FULLMatrix),condition=c("Wild","Wild","Wild","KO","KO","KO"))
meta_comparison_Wild_vs_KO_FULLMatrix$condition ~ relevel(meta_comparison_Wild_vs_KO_FULLMatrix$condition, ref="Wild")

## Make design matrix
condition ~ relevel(factor(meta_comparison_Wild_vs_KO_FULLMatrix$condition), ref="Wild")
dds_comparison_Wild_vs_KO_FULLMatrix<-DESeqDataSetFromMatrix(countData=counttable_comparison_Wild_vs_KO_FULLMatrix,colData=meta_comparison_Wild_vs_KO_FULLMatrix,design=~condition)

dim(dds_comparison_Wild_vs_KO_FULLMatrix)
dds_comparison_Wild_vs_KO_FULLMatrix<-DESeq(dds_comparison_Wild_vs_KO_FULLMatrix)
res_comparison_Wild_vs_KO_FULLMatrix<-results(dds_comparison_Wild_vs_KO_FULLMatrix,alpha=0.05)
summary(res_comparison_Wild_vs_KO_FULLMatrix)




# Identify differentially expressed genes FDR cutoff 0.05
res05_comparison_Wild_vs_KO_FULLMatrix<-sum(res_comparison_Wild_vs_KO_FULLMatrix$padj<0.05,na.rm=TRUE)
resSig005_comparison_Wild_vs_KO_FULLMatrix<-subset(res_comparison_Wild_vs_KO_FULLMatrix, padj < 0.05)
dim(resSig005_comparison_Wild_vs_KO_FULLMatrix)
summary(resSig005_comparison_Wild_vs_KO_FULLMatrix)
write.table(resSig005_comparison_Wild_vs_KO_FULLMatrix, "res_DeSeq2_FDR0.05_comparison_Wild_vs_KO_FULL.tab", sep="\t", col.names=NA, quote=F)
~~~

## Plot dispersion estimates
~~~
plotDispEsts(dds_comparison_Wild_vs_KO_FULLMatrix, ylim = c(1e-6,1e3) )
~~~

<figure>
  <img src="{{ page.root }}/fig/Dispersion.png" style="margin:10px;height:200px"/>
  <figcaption> Central dogma of molecular biology </figcaption>
</figure><br>

## Plot histogram of p-values
~~~
#hist(res_comparison_Wild_vs_KO_FULLMatrix$pvalue, col = "lavender", main = title, xlab = "p-values")
~~~


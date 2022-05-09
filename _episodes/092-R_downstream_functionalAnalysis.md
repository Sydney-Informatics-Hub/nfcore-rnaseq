---
title: "Functional enrichment analysis ..."
teaching: 10
exercises: 10
questions:
- "How to perform enrichment analysis in R (RStudio)?"
- "How to visualise functionally enriched Gene ontologies (GO) / pathways as networks?"

objectives:
- "Perform Functional enrichment analysis of the DE genes in 'R'"
keypoints:
- XXX
---


## GO analysis 

```
# P adj < 0.05 
sig <- res_tidy.DE[res_tidy.DE$p.adjusted < 0.05, ]

# Upregulated: LFC > 1, remove NAs
sig.up <- sig[sig$estimate > 1, ]
sig.up <- na.omit(sig.up)
sig.up.LFC <- sig.up$estimate
names(sig.up.LFC) <- sig.up$gene
# Sort by LFC, decreasing
sig.up.LFC <- sort(sig.up.LFC, decreasing = TRUE)

# Downregulated: LFC < 1, remove NAs
sig.dn <- sig[sig$estimate < 1, ]
sig.dn <- na.omit(sig.dn)
sig.dn.LFC <- sig.dn$estimate
names(sig.dn.LFC) <- sig.dn$gene
# Sort by LFC, decreasing
sig.dn.LFC <- sort(sig.dn.LFC, decreasing = TRUE)
```


### Upregulated 

~~~
ego.up <- enrichGO(gene = names(sig.up.LFC),
                      OrgDb = org.Mm.eg.db, 
                      keyType = 'SYMBOL',
                      readable = FALSE,
                      ont = "ALL",
                      pAdjustMethod = "BH",
                      pvalueCutoff = 0.05, 
                      qvalueCutoff = 0.2)
~~~

### Dotplot
~~~
dotplot(ego.up, showCategory=20)
~~~

<figure>
  <img src="{{ page.root }}/fig/DotPlot_up.png" style="margin:10px;height:400px"/>
  <figcaption> A basic RNASeq analysis workflow </figcaption>
</figure><br>


### cnetplot
~~~
# Depicts the linkages of genes and biological concepts (e.g. GO terms or KEGG pathways) as a network.
cnetplot(ego.up, 
         categorySize="pvalue", 
         foldChange=sig.up.LFC,
         cex_label_gene = 0.5,
         showCategory = 5)
~~~

<figure>
  <img src="{{ page.root }}/fig/cnePlot_up.png" style="margin:10px;height:400px"/>
  <figcaption> A basic RNASeq analysis workflow </figcaption>
</figure><br>

### Downregulated
~~~
ego.dn <- enrichGO(gene = names(sig.dn.LFC),
                      OrgDb = org.Mm.eg.db, 
                      keyType = 'SYMBOL',
                      readable = FALSE,
                      ont = "ALL",
                      pAdjustMethod = "BH",
                      pvalueCutoff = 0.05, 
                      qvalueCutoff = 0.2)
~~~

### Dotplot
~~~
dotplot(ego.dn, showCategory=20)
~~~

<figure>
  <img src="{{ page.root }}/fig/DotPlot_down.png" style="margin:10px;height:400px"/>
  <figcaption> A basic RNASeq analysis workflow </figcaption>
</figure><br>

### cnetplot
~~~
cnetplot(ego.dn, 
         categorySize="pvalue", 
         foldChange=sig.dn.LFC,
         cex_label_gene = 0.5,
         showCategory = 5)
~~~

<figure>
  <img src="{{ page.root }}/fig/cnePlot_down.png" style="margin:10px;height:400px"/>
  <figcaption> A basic RNASeq analysis workflow </figcaption>
</figure><br>

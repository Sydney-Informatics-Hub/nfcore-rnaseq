---
title: "Enrichment analysis - R"
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
## clusterProfiler
- We will be using clusterProfiler to perform over-representation analysis on GO terms associated with our list of significant genes. 
- The tool takes as input a significant gene list and a background gene list and performs statistical enrichment analysis using hypergeometric testing.
- The basic arguments allow the user to select the appropriate organism and GO ontology (BP, CC, MF) to test.

> ## Get the lists of UP and DOWN -regulated genes 
> ```
> # P adj < 0.05 
> sig <- res_tidy.DE[res_tidy.DE$p.adjusted < 0.05, ]
> # Upregulated: LFC > 1, remove NAs
> sig.up <- sig[sig$estimate > 1, ]
> sig.up <- na.omit(sig.up)
> sig.up.LFC <- sig.up$estimate
> names(sig.up.LFC) <- sig.up$gene
> # Sort by LFC, decreasing
> sig.up.LFC <- sort(sig.up.LFC, decreasing = TRUE)
> # Downregulated: LFC < 1, remove NAs
> sig.dn <- sig[sig$estimate < 1, ]
> sig.dn <- na.omit(sig.dn)
> sig.dn.LFC <- sig.dn$estimate
> names(sig.dn.LFC) <- sig.dn$gene
> # Sort by LFC, decreasing
> sig.dn.LFC <- sort(sig.dn.LFC, decreasing = TRUE)
> ```
> {: .language-bash}
{: .solution}

## Upregulated genes
> ## Run enrichGO
> ~~~
> ego.up <- enrichGO(gene = names(sig.up.LFC),
>                       OrgDb = org.Mm.eg.db, 
>                       keyType = 'SYMBOL',
>                       readable = FALSE,
>                       ont = "ALL",
>                       pAdjustMethod = "BH",
>                       pvalueCutoff = 0.05, 
>                       qvalueCutoff = 0.2)
> ~~~
> {: .language-bash}
{: .solution}


> ## Generate Dotplot
> ~~~
> dotplot(ego.up, showCategory=20)
> ~~~
> <figure>
>   <img src="{{ page.root }}/fig/DotPlot_up.png" style="margin:10px;height:400px"/>
>   <figcaption> Visualise the enriched biological concepts (here Gene ontologies) </figcaption>
> </figure><br>
> {: .language-bash}
{: .solution}

> ## Generate cnetplot
> ~~~
> # Depicts the linkages of genes and biological concepts (e.g. GO terms or KEGG pathways) as a network.
> cnetplot(ego.up, 
>          categorySize="pvalue", 
>          foldChange=sig.up.LFC,
>          cex_label_gene = 0.5,
>          showCategory = 5)
> ~~~
> <figure>
>   <img src="{{ page.root }}/fig/cnePlot_up.png" style="margin:10px;height:400px"/>
>   <figcaption> Links genes to enriched biological concepts </figcaption>
> </figure><br>
> {: .language-bash}
{: .solution}

## Downregulated genes
> ## Run enrichGO
> ~~~
> ego.dn <- enrichGO(gene = names(sig.dn.LFC),
>                       OrgDb = org.Mm.eg.db, 
>                       keyType = 'SYMBOL',
>                       readable = FALSE,
>                       ont = "ALL",
>                       pAdjustMethod = "BH",
>                       pvalueCutoff = 0.05, 
>                       qvalueCutoff = 0.2)
> ~~~
> {: .language-bash}
{: .solution}

> ## Generate Dotplot
> ~~~
> dotplot(ego.dn, showCategory=20)
> ~~~
> <figure>
>   <img src="{{ page.root }}/fig/DotPlot_down.png" style="margin:10px;height:400px"/>
>   <figcaption> Visualise the enriched biological concepts (here Gene ontologies)  </figcaption>
> </figure><br>
> {: .language-bash}
{: .solution}


> ## Generate cnetplot
> A cnetplot() depicts the linkages of genes and biological concepts (e.g. GO terms or KEGG pathways) as a network.
> ~~~
> cnetplot(ego.dn, 
>          categorySize="pvalue", 
>          foldChange=sig.dn.LFC,
>          cex_label_gene = 0.5,
>          showCategory = 5)
>~~~
><figure>
>  <img src="{{ page.root }}/fig/cnePlot_down.png" style="margin:10px;height:400px"/>
>  <figcaption> Links genes to enriched biological concepts </figcaption>
></figure><br>
> {: .language-bash}
{: .solution}



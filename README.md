# 510 Final Project 
#### Kayley Wong

## Overview

This project is trying to identify and performed pathway analysis on differential expressed genes between early stage (stage ia & ib) and late stage (stage iiia) lung cancer. The model for differential expression analysis will control for factors that known to be contributing to variances in gene expression, such as sex, age, race, ethnicity and smoking history. Principle component analysis will be performed to evaluate what factors need to be adjusted for. This project is hoping to provide insights to which pathways and genes are differentially expressed when lung cancer progressed. 

## Objectives
The analysis will be preformed using workflow outlined by `RNA-seq analysis is easy as 1-2-3 with limma, Glimma and edgeR` vignette (https://www.bioconductor.org/packages/devel/workflows/vignettes/RNAseq123/inst/doc/limmaWorkflow.html#abstract). 

## Data
Data for this analysis is publicly available dataset obtain from National Cancer Institute GDC Data Portal (https://portal.gdc.cancer.gov/). The analysis will be performed on 75 lung cancer patients, which 35 of them have early stage (stage ia & ib) and 40 of them have late stage (stage iiia) lung cancer. This dataset is from the TCGA-LUSC project, all patients in this dataset were diagnosed with lung squamous cell carcinoma. 

## Milestone 1
Obtain RNA-Seq data from GDC Data Portal and reading them into RStudio. Pre-process the data according to the workflow from the vignette. 

11/3 Progress:   
The data has been downloaded from GDC portal. The raw count and metadata files were cleaned and formatted in Python before loading into R for analysis. DGEList-object has been produced and lowly expressed genes have been filtered. MDS plots and box plots were generated to visualized the effect of normalization. We agreed that adding a PCA plot may be a good idea.   

## Milestone 2
Building Design Matrix and preform differential gene expression analysis, generate graphs and perform downstream pathway analysis with the differential expression analysis results. 

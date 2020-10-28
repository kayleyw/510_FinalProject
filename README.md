# 510 Final Project 
#### Kayley Wong

## Overview

This project is trying to identify and performed pathway analysis on differential expressed genes between stage ia and stage iv lung cancer patients who received treatment. The model for differential expression analysis will control for factors that known to be contributing to variances in gene expression, such as sex, age, race, ethnicity and smoking history. Principle component analysis will be performed to evaluate what factors need to be adjusted for. 

## Objectives
The analysis will be preformed using workflow outlined by `RNA-seq analysis is easy as 1-2-3 with limma, Glimma and edgeR` vignette (https://www.bioconductor.org/packages/devel/workflows/vignettes/RNAseq123/inst/doc/limmaWorkflow.html#abstract). 

## Data
Data for this analysis is publicly available dataset obtain from National Cancer Institute GDC Data Portal (https://portal.gdc.cancer.gov/). The analysis will be performed on 55 lung cancer patients, which 38 of them have early stage (stage ia) and 17 of them have late stage (stage iv) lung cancer. 

## Milestone 1
Obtain RNA-Seq data from GDC Data Portal and reading them into RStudio. Pre-process the data according to the workflow from the vignette. 

## Milestone 2
Building Design Matrix and preform differential gene expression analysis, generate graphs and perform downstream pathway analysis with the differential expression analysis results. 

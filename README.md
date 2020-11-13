# 510 Final Project  

## Title   
RNA-Seq differential expression profiling of early-stage lung adenocarcinoma and squamous cell carcinoma

## Author  
Kayley Wong

## Overview
#### Updated on 11/13   

This project is trying to identify and performed pathway analysis on differential expressed genes between lung adenocarcinoma and lung squamous cell carcinoma in early stage (stage ia). The model for differential expression analysis will control for factors that known to be contributing to variances in gene expression, such as sex, age, race, ethnicity and smoking history. Unsupervised clustering  with MD plots will be performed to evaluate what factors need to be adjusted for. This project is hoping to provide insights to which pathways and genes are differentially expressed between different subtypes of lung cancer.  

## Objectives
The analysis will be preformed using workflow outlined by `RNA-seq analysis is easy as 1-2-3 with limma, Glimma and edgeR` vignette (https://www.bioconductor.org/packages/devel/workflows/vignettes/RNAseq123/inst/doc/limmaWorkflow.html#abstract). 

## Data
#### Updated on 11/13 
Data for this analysis is publicly available dataset obtain from National Cancer Institute GDC Data Portal (https://portal.gdc.cancer.gov/). The analysis will be performed on 40 stage IA lung cancer patients, which 20 of them are diagnosed with adenocarcinoma and 20 of them are diagnosed with squamous cell carcinoma. Tthe list of samples used in this analysis is in `gdc_manifest_20201110_063233.txt` file. 

## Milestone 1
Obtain RNA-Seq data from GDC Data Portal and reading them into RStudio. Pre-process the data according to the workflow from the vignette. 

11/3 Progress:   
The data has been downloaded from GDC portal. The raw count and metadata files were cleaned and formatted in Python before loading into R for analysis. DGEList-object has been produced and lowly expressed genes have been filtered. MDS plots and box plots were generated to visualiz the effect of normalization. We agreed that adding a PCA plot may be a good idea.   

11/10 Progress:  
Voom differential expression analysis was performed and no differential expressed genes were found from the analysis. Maybe there are not much difference between patients with early stage and late stage squamous cell carcinoma in term of gene expression. The results of this analysis can be found in `DE_Analysis.cancerstage.html`. Because no DEGs were identify between early and late stage lung cancer patients. I decided to look into whether differential expressed genes can be identified from early stage lung cancer patients who are diagnosed with adenocarcinoma and squamous cell carcinoma. The mutations causing these two subtypes of lung cancer are different, therefore it will be interesting to investigate the differential expressed genes and pathways of these two subtypes.  

I have selected a dataset of 40 patients, half of them are diagnosed with adenocarcinoma and the other half are diagnosed with squamous cell carcinoma. I have preprocessed the data and ran all neccessary normalization. With voom analysis, cclose to 400 DEGs are identified with LFC greater than 1. The results for this analysis can be found in `DE_Analysis_adenoVSsqu.nb.html` within the `adenocarcinoma_vs_squamous_cell_carcinoma` folder.. I am currently working on the gene set enrichment analysis with camera method.      



## Milestone 2
Building Design Matrix and preform differential gene expression analysis, generate graphs and perform downstream pathway analysis with the differential expression analysis results.

11/13 Progress: 
I have finished running camera gene set enrichment analysis after comparing transcriptiome profiling of lung adenocarcinoma vs lung squamous cell carcinoma in early stage. The results and description for each step are up-to-date in the `scripts/DE_Analysis_adenoVSsqu.nb.html` file. I will descript how did I obtain the data from GDC data protal and pre-process them in python script before loading them into R in the session below.    

## Getting started
### Step 1: Downloading data from GDC data portal    
After selecting the data set I want to work with, I downloaded the manifest text file so that I can easily obtain all the file within that dataset. I used the `GDC RNASeq Tool` (https://github.com/cpreid2/gdc-rnaseq-tool) mentioned in the GDC data portal (https://gdc.cancer.gov/content/gdc-rnaseq-tool) to obtain a merged count matrix file. I also downloaded all the clinical metadata from the GDC data portal. Before using the tool, I downloaded a python script `gdc-rnaseq-tool.py` from the `GDC RNASeq Tool` github repository. Merged count matrix can be downloaded with the following command:    
`$ python3 gdc-rnaseq-tool.py gdc_manifest_20201110_063233.txt`      
The merged count matrix is in a folder `Merged_RNASeq_20201110-000008` as `Merged_Counts.tsv`    
    
### Step 2: Process count matrix and metadata files with python script     
After downloading and unzipping all the metadata file and merged count data matrix, I pre-process the data by selecting variables in clinical metadata that I need for analysis and removing formating issues in the files in the pyhton script `MergedCount_processing_adeno.ipynb`.    
    
### Step 3: Downloading all other necessary files for analysis     
For gene annotation mapping from ensembl to gene name, I downloaded `gencode.gene.info.v22.tsv` file from GDC data portal website (https://gdc.cancer.gov/about-data/gdc-data-processing/gdc-reference-files). I used this annotation file over the other availble package because it should be the most accurate one and mapped to the most genes. Besides the annotation file, I also downloaded `human_c2_v5p2.rdata` (http://bioinf.wehi.edu.au/software/MSigDB/), which is a C2 curated gene sets for camera gene set enrichment testing.      
      
### Step 4: Differential expression analysis   
After these steps, differential expression analysis can be run on lung adenocarcinoma vs lung squamous cell carcinoma in early stage by R script `DE_Analysis_adenoVSsqu.Rmd`.    
   

   

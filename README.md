# 2dpw4liam

This is a two dimensional pathway analysis of mouse RNA-seq data. 

Reads were previously mapped with Salmon to the mouse transcriptome from Gencode (version vM24).

In this analysis I use DESeq2 for DE analysis and Mitch for 2D pathway enrichment.

Gene sets were obtained from Reactome and converted to mouse using previously written bash script.

The analysis was conducted in R version 4.0.2.

The raw data has been deposited to NCBI GEO under accession GSE213708.

## Contents

* `data`: contains the count matrices for the two substudies in csv format.

* `gsets`: contains the human gene sets obtained from reactome, the gene sets converted to mouse
and the bash script used to do the converting.

* `ref`: contains the mouse gene name reference data which are used in the pathway analysis.

* `2dpw4liam.Rmd`: is the main analysis R markdown script that executes the differential expression
and pathway analyses.

* `README`: this helpful guide.

## Reproducibility

Requirements: 8 GB RAM and 2 CPU threads. Linux with docker installed.

1. Fetch docker image and run a container.

```
docker pull bioconductor/bioconductor_docker:RELEASE_3_12
docker run -it bioconductor/bioconductor_docker:RELEASE_3_12 bash
```

2. Inside the container, install the necessary packages.

```
Rscript -e 'BiocManager::install(c("mitch","DESeq2"),ask=FALSE)'
```

3. Clone the repo.

```
git clone https://github.com/markziemann/2dpw4liam.git
cd 2dpw4liam
```

4. Run the R Markdown script, check the html was generated, then exit the container.

```
Rscript -e 'rmarkdown::render("2dpw4liam.Rmd")'
ls
exit
```

5. Now that you're back on the host system, copy the results from the recent container to the current
working directory.

```
docker cp $(docker ps -aql):/2dpw4liam results
```

6. The newly created results folder contains the HTML and PDF which you can inspect with your favourite
PDF viewer and web browser.

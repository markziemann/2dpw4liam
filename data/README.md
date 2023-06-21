## Project brief

23-3-2020

Liam Hall (Sean McGee's group) provided 4 files for you from the two studies that we wish
to compare. These are from two studies.

### 3D6 neutralising antibody with HFD study
Raw reads data file (allSalmonQuant.csv). Control antibody treated mice labelled as 
Con_11, 15, 18, 19, 22, 23, 3, 8 and 3D6 antibody treated mice labelled as 3D6_12, 16, 
17, 20, 21, 24, 4, 7.
Fold change and p value file, with data expressed as 3D6 treated mice vs control antibody
treated mice (3D6 study differentially expressed genes.csv)

The fold change data from study 2 was calculated manually by Liam from the raw reads data
file, as he thinks there was an issue with the code used. So this will likely need to be
performed again.
 
### Amyloid beta 42 administration study
Raw reads data file (allReadsPerGeneNew_withoutAb53 with sums.csv). Scrambled Ab42 
treated mice (control) labelled as Sc41-45, 47-49 and Ab42 treated mice labelled as Ab51,  
52, 55-58, 60.
Fold change and p value file, with data expressed as vs control scrambled Ab42 treated 
mice (Ab42 v ScrAb42 all p values.csv)

MZ: I noted to Liam that it would be best to have bost datasets processed with the same
pipeline. On the 18th May 2020 he provided the file (allSalmonQuant_Scr_vs_Abeta.csv).
It contains ENSMUST accessions so it probably a mouse transcript level quantification
table. I enquired with Mark Richardson and he said the ENSEMBL accession version is 99.

### To-do

MZ: I will convert the counts to gene-level counts using aggregate function (sum) in R.
Then I will run DESeq2 to get differential expression profiles for these contrasts. Then
I will run the mitch package with these contrasts to yield a multidimensional gene set
enrichment analysis. Deadline 29th May 2020.

Data plan. MZ has saved the data to his personal Google Drive. The report will be generated
as an Rmarkdown because I'm able to easily combine report text, code and tables and charts.
The Rmd will be saved to GitHub.

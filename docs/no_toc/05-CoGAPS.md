


# CoGAPS

## Learning Objectives

- Learn about CoGAPS
- How to load packages in RStudio
- How to load data in RStudio
- How to configure CoGAPS
- How to run CoGAPS
- How to visualize patterns
- How to find pattern markers
- How to document software

## What is CoGAPS?

CoGAPS (Coordinated Gene Activity across Pattern Subsets) is a Bayesian NMF (Nonnegative Matrix Factorization) algorithm. It can be used to perform sparse matrix factorization on any data, and when this data represents biomolecules, to do gene set analysis. CoGAPS improves on other enrichment measurement methods by combining a Markov chain Monte Carlo (MCMC) matrix factorization algorithm (GAPS) with a threshold-independent statistic inferring activity on gene sets.

## What is CoGAPS used for?

CoGAPS can be used to perform sparse matrix factorization on any data. And when this data represents biomolecules, to do gene set analysis.

## Instructions

### Start up a "CoGAPS RStudio" compute container

1. Open [sciserver.org](https://sciserver.org) in a web browser and log in to your account.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; a. If you're already logged in, click "**Home**" in the top menu bar to return to the home page.

<img src="resources/images/05-CoGAPS_files/figure-html//16jh1ov1PyRyPKMTJ7ROiEyNm1B5KxdQlYQovVBCYesk_g25a927a7c80_0_0.png" title="Image of SciServer Dashboard with Home highlighted" alt="Image of SciServer Dashboard with Home highlighted" width="100%" />

2. Scroll down to the second set of boxes and click "**Compute**".

<img src="resources/images/05-CoGAPS_files/figure-html//16jh1ov1PyRyPKMTJ7ROiEyNm1B5KxdQlYQovVBCYesk_g25a927a7c80_0_6.png" title="Image of SciServer Dashboard with Compute highlighted" alt="Image of SciServer Dashboard with Compute highlighted" width="100%" />

3. Click "**Create container**"

<img src="resources/images/05-CoGAPS_files/figure-html//16jh1ov1PyRyPKMTJ7ROiEyNm1B5KxdQlYQovVBCYesk_g25a927a7c80_0_12.png" title="Image of the Compute page with Create container highlighted" alt="Image of the Compute page with Create container highlighted" width="100%" />

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; a. Give your container a name. This can be anything you like, but it’s useful if it says something about the purpose of the container so that you can tell your containers apart. You could name this container “CoGAPS”, since you’ll be using it to run CoGAPS.

<img src="resources/images/05-CoGAPS_files/figure-html//16jh1ov1PyRyPKMTJ7ROiEyNm1B5KxdQlYQovVBCYesk_g25a927a7c80_0_63.png" title="Image of the Compute page with the container name highlighted" alt="Image of the Compute page with the container name highlighted" width="100%" />

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; b. In the “**Compute Image**” drop-down menu, select “**R [version #] (RStudio)**” (there may be multiple versions of R in this drop-down menu; click on the latest version listed).

<img src="resources/images/05-CoGAPS_files/figure-html//16jh1ov1PyRyPKMTJ7ROiEyNm1B5KxdQlYQovVBCYesk_g25a927a7c80_0_69.png" title="Image of the Compute page with the RStudio compute image highlighted" alt="Image of the Compute page with the RStudio compute image highlighted" width="100%" />

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; c. Click "**Create**". This may take a moment.

<img src="resources/images/05-CoGAPS_files/figure-html//16jh1ov1PyRyPKMTJ7ROiEyNm1B5KxdQlYQovVBCYesk_g25a927a7c80_0_74.png" title="Image of the Compute page with the Create button highlighted" alt="Image of the Compute page with the Create button highlighted" width="100%" />

4. You should now see a new entry in your list of containers.

<img src="resources/images/05-CoGAPS_files/figure-html//16jh1ov1PyRyPKMTJ7ROiEyNm1B5KxdQlYQovVBCYesk_g25a927a7c80_0_81.png" title="Image of the Compute page with arrows pointing to the date/time of container's creation, its name, and the container image" alt="Image of the Compute page with arrows pointing to the date/time of container's creation, its name, and the container image" width="100%" />

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; a. "Created at" should be a few moments ago.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; b. "Name" should be the name you chose.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; c. "Image" should be ```"R[version #](RStudio)"```

5. Start your CoGAPS RStudio container by clicking on its **name** (whatever name you chose when you created the container). This will open in a new tab.

<img src="resources/images/05-CoGAPS_files/figure-html//16jh1ov1PyRyPKMTJ7ROiEyNm1B5KxdQlYQovVBCYesk_g25a927a7c80_0_89.png" title="Image of the Compute page with the container name highlighted" alt="Image of the Compute page with the container name highlighted" width="100%" />

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; a. You should see RStudio in this new tab.

<img src="resources/images/05-CoGAPS_files/figure-html//16jh1ov1PyRyPKMTJ7ROiEyNm1B5KxdQlYQovVBCYesk_g25954290abf_0_12.png" title="Image of RStudio screen" alt="Image of RStudio screen" width="100%" />

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; b. If you see something else, you may have picked the wrong "Compute Image" from the drop-down menu.

**If anything goes wrong, you can always delete your container by clicking the red “X” in the last column, and create a new container.**

<img src="resources/images/05-CoGAPS_files/figure-html//16jh1ov1PyRyPKMTJ7ROiEyNm1B5KxdQlYQovVBCYesk_g25a927a7c80_0_95.png" title="Image of the Compute page with an arrow pointing to the red X button" alt="Image of the Compute page with an arrow pointing to the red X button" width="100%" />

### Update rlang

1. Enter and run these commands into RStudio to make sure that you have the current version of ```rlang``` (you will receive an error later on otherwise):

```
packageVersion("rlang") # ‘1.0.6’
devtools::install_github("r-lib/rlang")
packageVersion("rlang") # ‘1.1.0.9000’
```

2. Once you see the output: ```[1] '1.1.1.9000'``` rlang has been updated.

### Install Packages

1. Enter and run this command:

```
devtools::install_github("FertigLab/CoGAPS")
```

2. This <u>will</u> take a while. Once the red "STOP" symbol is no longer visible in the top right hand corner of the Console, the installation is complete.

3. Enter and run this command:

```
devtools::install_github("sjmgarnier/viridis")
```

4. Once the red “STOP” symbol is no longer visible in the top right hand corner of the Console, the installation is complete.

<img src="resources/images/05-CoGAPS_files/figure-html//16jh1ov1PyRyPKMTJ7ROiEyNm1B5KxdQlYQovVBCYesk_g25a927a7c80_0_102.png" title="Image of the red STOP sign in RStudio, indicating that installation is still in progress" alt="Image of the red STOP sign in RStudio, indicating that installation is still in progress" width="100%" />

<img src="resources/images/05-CoGAPS_files/figure-html//16jh1ov1PyRyPKMTJ7ROiEyNm1B5KxdQlYQovVBCYesk_g25a927a7c80_0_109.png" title="Image of the red STOP sign no longer visible in RStudio, indicating that installation is complete" alt="Image of the red STOP sign no longer visible in RStudio, indicating that installation is complete" width="100%" />

5. Enter and run this command:

```
remotes::install_github("satijalab/seurat", "seurat5", quiet = TRUE)
```

6. This <u>will</u> take a while. Once the red "STOP" symbol is no longer visible in the top right hand corner of the Console, the installation is complete.

### Load Packages

1. Enter and run these commands:

```
library( "CoGAPS" )
library( "Seurat" )
library( "viridis" )
```

2. Once the red “STOP” symbol is no longer visible in the top right hand corner of the Console, the packages have been loaded.

### Load Data

1. Enter and run this command:

```
url <- "https://github.com/FertigLab/CoGAPS/raw/master/data/inputdata.Rds"
download.file( url, "inputdata.Rds" )
```

2. You should see this output if the run is successful:

```
trying URL 'https://github.com/FertigLab/CoGAPS/raw/master/data/inputdata.Rds'
Content type 'application/octet-stream' length 433262849 bytes (413.2 MB)
==================================================
downloaded 413.2 MB
```

3. Enter and run this command:

```
pdac_data <- readRDS( "inputdata.Rds" )
pdac_data
```

4. You should see this output if the run is successful:

```
An object of class Seurat 
15184 features across 25442 samples within 2 assays 
Active assay: originalexp (15176 features, 2000 variable features)
 1 other assay present: CoGAPS
 5 dimensional reductions calculated: PCA, Aligned, UMAP, pca, umap
```

5. Enter and run this command:

```
pdac_epi_counts <- as.matrix( pdac_data@assays$originalexp@counts )
```

6. You should see this output if the run is successful:

```
Warning: sparse->dense coercion: allocating vector of size 2.9 GiB
```

### Configure CoGAPS

1. Enter and run this command:

```
pdac_params <- CogapsParams(
  nIterations=100,          # run for 100 iterations 
  seed=42,                  # for consistency across stochastic runs
  nPatterns=8,              # each thread will learn 8 patterns
  sparseOptimization=TRUE,  # optimize for sparse data
  distributed="genome-wide" # parallelize across sets
)
```

2. Enter and run this command:

```
pdac_params <- setDistributedParams( pdac_params, nSets=7 )
```

3. You should see this output if the run is successful:

```
setting distributed parameters - call this again if you change nPatterns
```

### Run CoGAPS

1. Enter and run this command:

```
Sys.time()
```

2. Your output should include today's date and time.

3. Enter and run this command:

```
pdac_epi_result <- CoGAPS( pdac_epi_counts, pdac_params )
```

4. You should see this output if the run is successful (This <u>will</u> take a while, most likely around 20+ minutes):

```
This is CoGAPS version 3.19.1 
Running genome-wide CoGAPS on pdac_epi_counts (15176 genes and 25442 samples) with parameters:

-- Standard Parameters --
nPatterns            8 
nIterations          100 
seed                 42 
sparseOptimization   TRUE 
distributed          genome-wide 

-- Sparsity Parameters --
alpha          0.01 
maxGibbsMass   100 

-- Distributed CoGAPS Parameters -- 
nSets          7 
cut            8 
minNS          4 
maxNS          11 

Creating subsets...
set sizes (min, mean, max): (2168, 2168, 2168)
Running Across Subsets...

Data Model: Sparse, Normal
Sampler Type: Sequential
Loading Data...
Warning: Large values detected, is data log transformed?

Warning: Large values detected, is data log transformed?

Warning: Large values detected, is data log transformed?

Warning: Large values detected, is data log transformed?

Warning: Large values detected, is data log transformed?
Done! (00:00:36)
    worker 1 is starting!
-- Equilibration Phase --

Warning: Large values detected, is data log transformed?
    worker 6 is starting!

Warning: Large values detected, is data log transformed?
    worker 4 is starting!

Warning: Large values detected, is data log transformed?

Warning: Large values detected, is data log transformed?
    worker 5 is starting!

Warning: Large values detected, is data log transformed?

Warning: Large values detected, is data log transformed?
    worker 3 is starting!

Warning: Large values detected, is data log transformed?
    worker 7 is starting!

Warning: Large values detected, is data log transformed?

Warning: Large values detected, is data log transformed?
    worker 2 is starting!
-- Sampling Phase --
    worker 2 is finished! Time: 00:18:04
    worker 7 is finished! Time: 00:18:20
    worker 4 is finished! Time: 00:18:49
    worker 3 is finished! Time: 00:18:42
    worker 6 is finished! Time: 00:18:59
    worker 1 is finished! Time: 00:19:09
    worker 5 is finished! Time: 00:19:19

Matching Patterns Across Subsets…
Running Final Stage...

Connected to your session in progress, last started 2023-Jun-29 16:26:07 UTC (3 hours ago)
Data Model: Sparse, Normal
Sampler Type: Sequential
Loading Data...
Warning: Large values detected, is data log transformed?

Warning: Large values detected, is data log transformed?

Warning: Large values detected, is data log transformed?

Warning: Large values detected, is data log transformed?
Done! (00:00:29)
    worker 1 is starting!
-- Equilibration Phase --

Warning: Large values detected, is data log transformed?
    worker 5 is starting!

Warning: Large values detected, is data log transformed?

Warning: Large values detected, is data log transformed?
    worker 4 is starting!

Warning: Large values detected, is data log transformed?

Warning: Large values detected, is data log transformed?
    worker 6 is starting!

Warning: Large values detected, is data log transformed?
    worker 2 is starting!

Warning: Large values detected, is data log transformed?

Warning: Large values detected, is data log transformed?

Warning: Large values detected, is data log transformed?
    worker 3 is starting!

Warning: Large values detected, is data log transformed?
    worker 7 is starting!
-- Sampling Phase --
   worker 1 is finished! Time: 00:17:04
    worker 6 is finished! Time: 00:17:04
    worker 5 is finished! Time: 00:17:16
    worker 4 is finished! Time: 00:17:15
    worker 7 is finished! Time: 00:17:07
    worker 2 is finished! Time: 00:17:17
    worker 3 is finished! Time: 00:17:11
```

5. Enter and run this command:

```
Sys.time()
```

6. Your output should include today's date and time.

7. Enter and run this command:

```
saveRDS( pdac_epi_result, "../data/pdac_epi_cogaps_result" )
```

8. You should see this output if the run is successful:

```
Warning: cannot open compressed file '../data/pdac_epi_cogaps_result', probable reason 'No such file or directory'Error in gzfile(file, mode) : cannot open the connection
```

9. Enter and run this command:

```
pdac_epi_result
```

10. You should see this output if the run is successful:

```
[1] "CogapsResult object with 15176 features and 25442 samples"
[1] "7 patterns were learned"
```

11. Enter and run this command in order to save your results:

```
saveRDS( pdac_epi_result, "pdac_epi_cogaps_result.rds" )
```

### Visualize Patterns

1. Enter and run this command:

```
cogapsresult <- readRDS( "pdac_epi_cogaps_result.rds" )
```

2. Enter and run this command:

```
patterns_in_order <- t( cogapsresult@sampleFactors[colnames(pdac_data),] )
pdac_data[["CoGAPS"]] <- CreateAssayObject( counts = patterns_in_order )
```

3. You should receive this output:

```
Warning: Feature names cannot have underscores ('_'), replacing with dashes ('-')
```

4. Enter and run this command:

```
inputdata <- pdac_data
DefaultAssay(inputdata) <- "CoGAPS"
pattern_names = rownames( inputdata@assays$CoGAPS )
```

5. Enter and run this command:

```
color_palette <- viridis(n=10)
FeaturePlot(inputdata, pattern_names, cols=color_palette, reduction = "umap") & NoLegend()
```

6. Your output should look like this if the run was successful (visible in the bottom right corner of your screen):

<img src="resources/images/05-CoGAPS_files/figure-html//16jh1ov1PyRyPKMTJ7ROiEyNm1B5KxdQlYQovVBCYesk_g25a5f9f2e31_0_1.png" title="Image of a CoGAPS feature plot" alt="Image of a CoGAPS feature plot" width="100%" />

### Find Pattern Markers

1. Enter and run this command:

```
pm <- patternMarkers( cogapsresult, threshold="cut" )
```

2. You should see this output if the run was successful:

```
Warning: STATS is longer than the extent of 'dim(x)[MARGIN]'
```

3. Enter and run this command:

```
# hallmarks <- PatternHallmarks( cogapsresult )
```

4. Enter and run this command:

```
# plotPatternHallmarks(hallmarks, whichpattern = 7)
```

### Document Software

1. Enter and run this command:

```
sessionInfo()
```

2. Your output should include all the information about your RStudio session.

**Troubleshooting/Reminders:**

- If you restart RStudio, you must repeat the [Load Packages](https://practicalgenomics.github.io/cogaps-on-sciserver/cogaps.html#load-packages) step, otherwise errors will occur and you will not be able to successfully run your code.

## Resources

[CoGAPS Guide Website](https://fertiglab.github.io/CoGAPSGuide/)

<img src="resources/images/05-CoGAPS_files/figure-html//16jh1ov1PyRyPKMTJ7ROiEyNm1B5KxdQlYQovVBCYesk_g25954290abf_0_8.png" title="Image of the CoGAPS Guide website homepage" alt="Image of the CoGAPS Guide website homepage" width="100%" />

[CoGAPS R Guide](https://fertiglab.github.io/CoGAPSGuide/proceduretwo/)

<img src="resources/images/05-CoGAPS_files/figure-html//16jh1ov1PyRyPKMTJ7ROiEyNm1B5KxdQlYQovVBCYesk_g25a927a7c80_0_116.png" title="Image of the R CoGAPS API page" alt="Image of the R CoGAPS API page" width="100%" />

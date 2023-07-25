
{quiz, id: ch5_quiz, attempts: 10}

## Chapter 4: CoGAPS Review Quiz

Based on what you've learned in this chapter, choose the best answer.

{choose-answers: 1}
? How do you load packages in RStudio?

a) Click on the "Packages" tab and select the desired packages
b) Use the ```load_packages()``` function
C) Enter and run the command ```library("package_name")```
d) Use the ```install.packages()``` function

{choose-answers: 1}
? How do you load data in RStudio?

a) Use the ```import_data()``` function
b) Click on the "Import Dataset" button in the top menu bar
c) Enter and run the command ```url <- "[URL]" load_data("file_path")```
D) Enter and run the command ```url <- "[URL]" download.file( url, "inputdata.Rds" )```

{choose-answers: 1}
? How do you know that commands are completed running and you can input your next command?

A) The red "STOP" symbol is no longer visible in the top right hand corner of the Console
b) A green check mark is visible next to the command in the Console
c) There is no way to know
d) A "run successful" message appears in the Console

{choose-answers: 1}
? What do you need to do if you restart your R session and want to continue your work?

A) You need to repeat the *Load Packages* step
b) You need to start everything over again from the first step
c) You need to repeat the *Load Data* step
d) You can't do anything, you've already destroyed all your work

{choose-answers: 1}
? What command is used to start visualizing patterns using CoGAPS results?

a) ```plotPatternHallmarks(hallmarks, whichpattern = 7)```
B) ```color_palette <- viridis(n=10) FeaturePlot(inputdata, pattern_names, cols=color_palette, reduction = "umap") & NoLegend()```
c) ```patterns_in_order <- t(cogapsresult@sampleFactors[colnames(pdac_data), ])```
d) ```cogapsresult <- readRDS("pdac_epi_cogaps_result.rds")```

{/quiz}

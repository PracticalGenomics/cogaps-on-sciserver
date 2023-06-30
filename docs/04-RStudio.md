


# R/RStudio

## Learning Objectives
- Start up a C-MOOR RStudio compute container
- Find and use features of RStudio: R console, help window, viewer, environment window, history.
- Complete your first “swirl” tutorial

## Introduction

Before beginning this assignment, you should have already created a SciServer account and submitted your SciServer username to your instructor. In this assignment you will learn how to set up the “C-MOOR RStudio” compute container on SciServer. You will learn the basics of how to use RStudio, and will practice doing R coding within RStudio. You will also do your first “swirl” lesson. Swirl is a set of R tutorials that run inside RStudio.

## Instructions

### Start up a "C-MOOR RStudio" compute container

1. Open [sciserver.org](https://sciserver.org) in a web browser and log in to your account.

  &nbsp; a. If you’re already logged in, click “**Home**” in the top menu bar to return to the home page.

2. Scroll down to the second set of boxes and click “**Compute**”.
3. Click "**Create container**".
  
  &nbsp; a. Give your container a name. This can be anything you like, but it’s useful if it says something about the purpose of the container so that you can tell your containers apart. You could name this container “RStudio”, since you’ll be using it to access RStudio.
  
  &nbsp; b. In the “**Compute Image**” drop-down menu, select “**C-MOOR RStudio**”.
  
  &nbsp; c. Under “**Data Volumes**”, check the box next to “**C-MOOR Data**”.
 
  &nbsp; d. Click “**Create**”. This may take a moment.

4. You should now see a new entry in your list of containers.
 
  &nbsp; a. “Created At” should be a few moments ago.

  &nbsp; b. “Name” should be the name you chose.

  &nbsp; c. “Image” should be “C-MOOR RStudio".

5. Start your C-MOOR RStudio container by clicking on its **name** (whatever name you chose when you created the container). This will open in a new tab. 
  
  &nbsp; a. You should see RStudio.

![RStudio startup screen](/cogaps-on-sciserver/resources/images/RStudio.png)

  &nbsp; b. If you see something else, you may have picked the wrong “Compute Image” from the drop-down menu.

**If anything goes wrong, you can always delete your container by clicking the red “X” in the last column, and create a new container.**

### Complete your first swirl tutorial

1. Watch this 90 second video tour of RStudio:

<iframe width="560" height="315" src="https://www.youtube.com/embed/n3uue28FD0w" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

2. If you’re not there already, go to the SciServer compute page and start up the C-MOOR RStudio container.
  
  &nbsp; a. Open [sciserver.org](https://sciserver.org) in a web browser and log in to your account.
 
  &nbsp; b. If you’re already logged in, click “**Home**” in the top menu bar to return to the home page.
 
  &nbsp; c. Scroll down to the second set of boxes and click “**Compute**”.
 
  &nbsp; d. Start your C-MOOR container by clicking on its name.

3. In the **R console** window of RStudio (bottom left, or if you have no files open, it may take up the whole left side of the screen) type these commands to start up swirl:
  
  &nbsp; a. ```library(swirl)```
 
  &nbsp; b. ```swirl()```

4. Install the course, following the instructions provided by swirl:
 
  &nbsp; a. Enter your name

  &nbsp; b. Press <ENTER>

  &nbsp; c. Select 1, 2, or 3

  &nbsp; d. Install the course: "**R Programming: The basics of programming in R**".

5. Complete your first swirl lesson.
  
  &nbsp; a. Choose the "**R programming**" course.

  &nbsp; b. Choose Lesson 1 "**Basic Building Blocks**".

  &nbsp; c. Follow the instructions provided by swirl to complete the lesson.

  &nbsp; d. When you get to the end, it will ask if you want credit on Coursera. Choose “**No**” (we are not using Coursera for this course).

### Managing your C-MOOR RStudio compute container

If you delete your container now, you will lose **all** your progress in swirl. If you need to return to any part of the tutorial later, it is a good idea to keep the container until you are sure that you’re finished using it.


```r
devtools::session_info()
```

```
## ─ Session info ───────────────────────────────────────────────────────────────
##  setting  value                       
##  version  R version 4.0.2 (2020-06-22)
##  os       Ubuntu 20.04.5 LTS          
##  system   x86_64, linux-gnu           
##  ui       X11                         
##  language (EN)                        
##  collate  en_US.UTF-8                 
##  ctype    en_US.UTF-8                 
##  tz       Etc/UTC                     
##  date     2023-06-30                  
## 
## ─ Packages ───────────────────────────────────────────────────────────────────
##  package     * version date       lib source                            
##  assertthat    0.2.1   2019-03-21 [1] RSPM (R 4.0.5)                    
##  bookdown      0.24    2023-03-28 [1] Github (rstudio/bookdown@88bc4ea) 
##  cachem        1.0.7   2023-02-24 [1] CRAN (R 4.0.2)                    
##  callr         3.5.0   2020-10-08 [1] RSPM (R 4.0.2)                    
##  cli           3.6.1   2023-03-23 [1] CRAN (R 4.0.2)                    
##  crayon        1.3.4   2017-09-16 [1] RSPM (R 4.0.0)                    
##  desc          1.2.0   2018-05-01 [1] RSPM (R 4.0.3)                    
##  devtools      2.3.2   2020-09-18 [1] RSPM (R 4.0.3)                    
##  digest        0.6.25  2020-02-23 [1] RSPM (R 4.0.0)                    
##  ellipsis      0.3.1   2020-05-15 [1] RSPM (R 4.0.3)                    
##  evaluate      0.20    2023-01-17 [1] CRAN (R 4.0.2)                    
##  fansi         0.4.1   2020-01-08 [1] RSPM (R 4.0.0)                    
##  fastmap       1.1.1   2023-02-24 [1] CRAN (R 4.0.2)                    
##  fs            1.5.0   2020-07-31 [1] RSPM (R 4.0.3)                    
##  glue          1.4.2   2020-08-27 [1] RSPM (R 4.0.5)                    
##  hms           0.5.3   2020-01-08 [1] RSPM (R 4.0.0)                    
##  htmltools     0.5.5   2023-03-23 [1] CRAN (R 4.0.2)                    
##  knitr         1.33    2023-03-28 [1] Github (yihui/knitr@a1052d1)      
##  lifecycle     1.0.3   2022-10-07 [1] CRAN (R 4.0.2)                    
##  magrittr      2.0.3   2022-03-30 [1] CRAN (R 4.0.2)                    
##  memoise       2.0.1   2021-11-26 [1] CRAN (R 4.0.2)                    
##  ottrpal       1.0.1   2023-03-28 [1] Github (jhudsl/ottrpal@151e412)   
##  pillar        1.9.0   2023-03-22 [1] CRAN (R 4.0.2)                    
##  pkgbuild      1.1.0   2020-07-13 [1] RSPM (R 4.0.2)                    
##  pkgconfig     2.0.3   2019-09-22 [1] RSPM (R 4.0.3)                    
##  pkgload       1.1.0   2020-05-29 [1] RSPM (R 4.0.3)                    
##  prettyunits   1.1.1   2020-01-24 [1] RSPM (R 4.0.3)                    
##  processx      3.4.4   2020-09-03 [1] RSPM (R 4.0.2)                    
##  ps            1.4.0   2020-10-07 [1] RSPM (R 4.0.2)                    
##  R6            2.4.1   2019-11-12 [1] RSPM (R 4.0.0)                    
##  readr         1.4.0   2020-10-05 [1] RSPM (R 4.0.2)                    
##  remotes       2.2.0   2020-07-21 [1] RSPM (R 4.0.3)                    
##  rlang         1.1.0   2023-03-14 [1] CRAN (R 4.0.2)                    
##  rmarkdown     2.10    2023-03-28 [1] Github (rstudio/rmarkdown@02d3c25)
##  rprojroot     2.0.3   2022-04-02 [1] CRAN (R 4.0.2)                    
##  sessioninfo   1.1.1   2018-11-05 [1] RSPM (R 4.0.3)                    
##  stringi       1.5.3   2020-09-09 [1] RSPM (R 4.0.3)                    
##  stringr       1.4.0   2019-02-10 [1] RSPM (R 4.0.3)                    
##  testthat      3.0.1   2023-03-28 [1] Github (R-lib/testthat@e99155a)   
##  tibble        3.2.1   2023-03-20 [1] CRAN (R 4.0.2)                    
##  usethis       1.6.3   2020-09-17 [1] RSPM (R 4.0.2)                    
##  utf8          1.1.4   2018-05-24 [1] RSPM (R 4.0.3)                    
##  vctrs         0.6.1   2023-03-22 [1] CRAN (R 4.0.2)                    
##  withr         2.3.0   2020-09-22 [1] RSPM (R 4.0.2)                    
##  xfun          0.26    2023-03-28 [1] Github (yihui/xfun@74c2a66)       
##  yaml          2.2.1   2020-02-01 [1] RSPM (R 4.0.3)                    
## 
## [1] /usr/local/lib/R/site-library
## [2] /usr/local/lib/R/library
```

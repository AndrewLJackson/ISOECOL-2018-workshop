# ISOECOL-2018-workshop

This repository contains a collection of presentations and vignettes written in .*Rmarkdown format for my workshop on Bayesian Statistics for Ecologists running before ISOECOL 2018 in Vina del Mar, Chile on Saturday 28 July. Much of the content here was written by my collaborator and real statistician Andrew Parnell, University of Maynooth, Ireland.

In preparation for the course please install the following, preferably in the below suggested order. Make sure you run these before you arrive in case of poor (or crowded!) internet.

Remember you will need to bring your own personal computer for the duration of the course.

### Step 1

Install the following using the corresponding links and *make sure you have the latest versions installed*:

-	R: [http://www.r-project.org](http://www.r-project.org)

-	Rstudio (optional but recommended): [https://www.rstudio.com](https://www.rstudio.com)

-	JAGS: http://sourceforge.net/projects/mcmc-jags/files/

### Step 2

Now install all the packages required for the course by entering the following code in to R

```{r,eval=FALSE}
install.packages(c('rjags', 'compositions', 'devtools', 
                   'tidyverse', 'vegan', 'ellipse', 
                   'simmr', 'SIBER', 'MixSIAR'))

# our package `siar` is pretty out of date these days, 
# but its useful for quick examples.
# Unfortunately it no longer installs from CRAN and instead 
# we have to build it from the raw source code from github.

devtools::install_github("andrewljackson/siar") 

# It is often worth checking from time to time that our packages
# are up to date.
update.packages(ask = FALSE)

```

These will install the most up to date versions of the packages. Note that this might take a while as some of these are pretty big and complicated packages.

 
### Step 3
 
Finally if you would like to do some pre-course reading (recommended) there are some papers which can be accessed [here](https://github.com/andrewcparnell/simms_course/tree/master/papers).


### Troubleshooting

Here are some common problems with solutions:

  - If you are on Windows and you get an error about not having Rtools please install Rtools from the link it provides you in the error message
  - If you are trying to install Rtools with R 3.5.0 and are getting an error message about incompatibility of Rtools, run the command:
```{r}
library(devtools)
assignInNamespace("version_info", c(devtools:::version_info, 
                  list("3.5" = list(version_min = "3.3.0", 
                  version_max = "99.99.99", path = "bin"))), 
                  "devtools")
```
  Then try the `install_github` command again.
  
  - If you are on a Mac you might need to install X11 from [http://www.xquartz.org](http://www.xquartz.org). 
  - You may get a pop up window be asking if you want 'additional build tools'. Please select 'yes'. 
  - If on a Mac you will likely need to install Xcode from the Mac App Store. This is a big download so make sure you download it before you get to the course.
  - If you get an error about package `stringi` try typing `install.packages('stringi',type='win.binary')` if on Windows or `install.packages('stringi',type='mac.binary')` if on Mac. Then re-run the commands above
  - If you get some errors about `pandoc` when installing simmr leave out the `build_vignettes=TRUE` argument


If you run into any other problems please drop me an email at  <a.jackson@tcd.ie> although I am travelling from Thursday!

## Timetable (proposed and likely flexible)

- 10:00 - 11:30 Introduction to Bayes Theorem and Bayesian Inference (intro_bayes.Rmd)
- 11:30 - 12:30 Fitting our first Bayesian models (*combining-priors-and-likelihoods.Rmd* & *first-jags.Rmd*)
- 12:30 - 14:00 Lunch
- 14:00 - 15:00 Building more complicated regression models (*regression-in-jags.Rmd* &  *basic-simm-jags.Rmd* & if you are more comfortable or quicker at this you might move on to *glmm_in_jags.Rmd* which illustrates how to include a random effect)
- 15:00 - 16:00 Reporting output from Bayesian models (more of a discussion session, but i suspect we will run over from the previous session and we can work together through some examples from mixing models or SIBER type analyeses as a class)


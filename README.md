# IEA-2019-Bayesian-workshop

This repository contains a collection of presentations and vignettes written in .*Rmarkdown format for my workshop on Bayesian Statistics for Ecologists which ran before ISOECOL 2018 in Vina del Mar, Chile on Saturday 28 July. Much of the content here was written by my collaborator and real statistician Prof. Andrew Parnell, University of Maynooth, Ireland.

While the ISOECOL workshops was a full day, we obviously only have a half day and so will move quickly through some content, and not complete all the practical sessions. But I am giving you all the material so that you can work through it yourself.

In preparation for the course please install the following, preferably in the below suggested order. Make sure you run these before you arrive in case of poor (or crowded!) internet.

Remember you will need to bring your own personal computer for the duration of the course.

**_NB_** the timetable is very much more than likely to change. I will be finalising on the train thursday morning, so I wont have a definitive plan until we meet at 14:00!

### Step 1

Install the following using the corresponding links and *make sure you have the latest versions installed* and note that you have to install all three separately:

-	R: [http://www.r-project.org](http://www.r-project.org) - at least verison 3.5.1

-	Rstudio (optional but recommended): [https://www.rstudio.com](https://www.rstudio.com)

-	JAGS: http://sourceforge.net/projects/mcmc-jags/files/

### Step 2

Now install all the packages required for the course by entering the following code in to R

```{r,eval=FALSE}
install.packages(c('rjags', 'devtools', 'tidyverse'))

# It is often worth checking from time to time that all your installed packages
# are up to date.
update.packages(ask = FALSE)

```

These will install the most up to date versions of the packages. Note that this might take a while as some of these may be pretty big and complicated packages.

 
### Step 3
 
Finally if you would like to do some pre-course reading (recommended) there are some papers which can be accessed [here](https://github.com/andrewcparnell/simms_course/tree/master/papers).

You should also be familiar with at least linear modelling in R and using R studio. My [podcast series](https://www.youtube.com/playlist?list=PLXXzyqr0tEhPRNDuEQ6wcvMcpAkGRjVqs) contains follow-along videos and code to get you up to speed if you feel you need a refresher course or are new to this software.


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
  
  - If you are on a Mac you might need to install X11 from [http://www.xquartz.org](http://www.xquartz.org) but likely only if you are using an oldre version of OSX. 
  - You may get a pop up window be asking if you want 'additional build tools'. Please select 'yes'. 
  - If on a Mac you will likely need to install command line tools (which is much smaller than the full Xtools which is available from the App Store). Instructions for installing can be found at http://osxdaily.com/2014/02/12/install-command-line-tools-mac-os-x/
  - If you get an error about package `stringi` try typing `install.packages('stringi',type='win.binary')` if on Windows or `install.packages('stringi',type='mac.binary')` if on Mac. Then re-run the commands above
  - If you get some errors about `pandoc` when installing simmr leave out the `build_vignettes=TRUE` argument


If you run into any other problems please drop me an email at  <a.jackson@tcd.ie> although I am travelling from Thursday!

## Timetable (proposed and likely flexible)

- 14:00 - 14:45 Introduction to Bayes Theorem and Bayesian Inference
(intro_bayes.Rmd)
- 14:45 - 15:15 Combining priors and likelihoods (combining-priors-and-likelihoods.Rmd)
- 15:15 - 15:30 Tea & Coffee
- 15:30 - 16:00 Intro to JAGS practical (first-jags.Rmd)
- 16:00 - 16:30 Bayesian Linear Models (regression-in-jags.Rmd)
- 16:30 - 17:00 Bayesian Hierarchical Models; also known as variance components modelling, random effects, and ultimately mixed effects models (glmm_in_jags.Rmd)

# Instructions for Installation of dependencies for our Wallace-BioModelos 3 Workshop Pre-workshop Bug Testing Meeting!
Thank you for joining!

**Beginner R users**: Please update to the latest version of R (v4) and update all packages (in R Studio go to tools - check for package updates) before starting with the installation steps below.

**Advanced R users**: Update rgbif, paleobioDB, sf

**Another note for beginners**: Also, if you previously installed and used Wallace or ENMEval last year and regularly save your workspace environment, please clear your R Studio workspace environment (using the broom icon on the right side). Then, exit R Studio and when prompted save the (now cleaned) workspace, and open R Studio again before proceeding with the steps below (in the future. don't save your workspace environment).

Run the following lines in R:
```{r}
>#install the devtools package to help you install other things
>install.packages("devtools")
>library(devtools)
>#install the dev version of ENMeval
>install_github("https://github.com/bobmuscarella/ENMeval/tree/dev", dependencies = TRUE, force = TRUE)
># if installation failed, check the error message; it is probably because of other dependencies (like gbm, randomForest) that need to be ># installed, please install them and then try to install enmeval again now, install the dev version of occCite
>install_github("https://github.com/hannahlowens/occCite", dependencies = TRUE, force = TRUE)
>#install maskRangeR
>devtools::install_github("cmerow/maskRangeR/maskRangeR")
># now, we must install changeranger, for which you need to download a zipfile
># here:https://drive.google.com/file/d/12lgBht-251zy7-XdzN6UwmWpodyYrGY-/view?usp=sharing
>#changeranger is still in a private github repo, but for the workshop we will make it public so that it can also be installed via >devtools like the other packages
># after you download it, unzip it, and use the next line to install changeranger from your local computer directory where you saved the
># zipfile, e.g. '/Users/mblair/Desktop/WorkedExample/changeRangeR'
>install_local("your/computer/directory/to/changeRangeR")
>#check that both of these installations worked
>library(maskRangeR)
>library(changeRangeR)
># now install the Wallace v 2 dev version
>install_github("https://github.com/wallaceEcoMod/wallace/tree/multiSp", dependencies = TRUE, force = TRUE)
># if you are asked about whether or not to install a package that needs to be compiled from binaries, say no, which means you choose to >install the older version (like systemfonts)
>#now, load Wallace to test that it works
>library(wallace)
>run_wallace()
>#This should open Wallace
>#Stop here - We will run one more line of code at the beginning of bug testing for you to install the "BioModelos" version of Wallace, >which is almost done (!). Thank you for installing all of these first, to make the installation of the BioModelos version much faster >(re: dependencies) . 
```

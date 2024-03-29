# RforMath1110
 
This is an R package which deploys interactive notebooks to accompany an introductory course in applied statistics. The notebooks follow the freely available [OpenIntro Statistics (4Ed)](http://www.openintro.org/os) textbook and supplementary resources. 

You can install this package by running the following command in R (which requires the `devtools` package as a prerequisite): `remotes::install_github("amhmath/RforMath1110")`

## Grading Functionality

I've updated the package to include functionality from Colin Rundel's `learnrhash` package. This allows students to generate a hash code, which encodes their completed notebook -- students can then paste this hash code into a web-form (such as Google Forms) and then the instructor can reproduce and assess the student's work using `learnrhash` and the student's hash code. See more about this functionality from the [`learnrhash` repo](https://github.com/rundel/learnrhash). Some users will need to install `learnrhash` manually in order for the notebooks to run -- you can do this with `remotes::install_github("rundel/learnrhash")`. I am working on a fix for this issue.

## Running Tutorials

Once the package has been installed you can run the individual notebooks by navigating to the `Tutorials` tab in RStudio's top-right pane. You'll just need to click the *Start Tutorial?* button to render and work through the corresponding interactive notebook. If you get an error stating that `learnrhash` must be installed, you can install it manually using `remotes::install_github("rundel/learnrhash")` -- R will report an error saying that `learnrhash` is not available for your version of R if you allow R to try installing the package on its own. If you prefer to run the tutorials from a web browser rather than RStudio's Tutorials pane, you can access the tutorials using commands of the following structure: `learnr::run_tutorial(NOTEBOOK_NAME, package = "AppliedStatsInteractive")`

The available notebooks are as follows:
+ 00_StartHere
+ 01_IntroToData
+ 02_IntroToR
+ 03_DescriptiveNumCat
+ 04_DataViz
+ 05_DiscreteDistributions
+ 06_NormalDistribution
+ 07_DiscreteDistributionsLab
+ 08_NormalDistributionLab
+ 09_FoundationsForInference
+ 10_IntroInferenceLab
+ 11_HTandCIprop
+ 12_InferencePractice
+ 13_InferenceCategoricalLab
+ 14_ChiSquare
+ 15_HTandCInum
+ 16_InferencePractice
+ 17_InferenceNumericalLab
+ 18_ANOVA
+ 19_LinearRegression

The notebook named 04_DataViz is an adaptation of the data visualization chapter from Hadley Wickham and Garrett Grolemund's [R for Data Science](https://r4ds.had.co.nz/).

## A Note on Rendering Workbooks

(**Note:** *This is a non-issue if running workbooks from the tutorials pane*). Multiple calls to `learnr::run_tutorial()` in a single R session cause rendering errors in the notebooks -- exercises are not rendered correctly. This can be avoided by either restarting R `Ctrl+Shift+F10` or by closing RStudio and re-opening before rendering a second workbook. If you already attempted to render the notebook and experiences the rendering error, you should use your file manager to navigate to the folder containing the workbook and delete the associated *html* file. You can identify the location of the files on your machine by running `find.package("AppliedStatsInteractive")`. Calling `learnr::run_tutorial()` now will re-build the html file. I will update this section when a better workaround is discovered.

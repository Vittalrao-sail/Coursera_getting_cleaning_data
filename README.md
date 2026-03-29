# Getting and Cleaning Data Course Project

This repository contains the R code and documentation for the "Human Activity Recognition Using Smartphones" data cleaning project.

## Project Goal
The objective is to prepare a tidy data set that can be used for later analysis. The data represents measurements collected from the accelerometers of Samsung Galaxy S smartphones worn by 30 subjects performing six different activities.

## Files in this Repository
* `run_analysis.R`: The R script used to transform the raw data into the final tidy dataset.
* `FinalData.txt`: The exported tidy data set (the output of the script).
* `CodeBook.md`: A document describing the variables, the data, and the transformations performed.
* `README.md`: This file, providing an overview of the project.

## How to Run the Analysis
1.  Download the raw data from [this link](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip).
2.  Unzip the folder into your R working directory.
3.  Run `source("run_analysis.R")` in RStudio.
4.  The script will generate a file named `FinalData.txt` in your working directory.

## Script Logic
The `run_analysis.R` script performs the following:
1.  Merges the training and test sets.
2.  Extracts only the measurements for mean and standard deviation.
3.  Replaces activity numeric codes with descriptive names (e.g., "Walking").
4.  Cleans column names to be more readable (e.g., replacing `Acc` with `Accelerometer`).
5.  Calculates the average of each variable for each activity and each subject.

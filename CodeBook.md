# Code Book: Human Activity Recognition Tidy Data

This code book describes the variables, the data, and the transformations performed to clean up the data.

## The Data Source
The data is derived from the "Human Activity Recognition Using Smartphones Dataset" (Version 1.0). 
* **Subjects:** 30 volunteers (aged 19-48).
* **Activities:** Walking, Walking Upstairs, Walking Downstairs, Sitting, Standing, Laying.
* **Sensors:** Smartphone accelerometer and gyroscope.

## Identifiers
* `subject`: The ID of the test subject (1 to 30).
* `activity`: The type of activity performed (Walking, Walking_Upstairs, Walking_Downstairs, Sitting, Standing, Laying).

## Measurements (Extracted Mean and STD)
The variables below represent the **average** of the mean and standard deviation signals for each subject and activity. 
* `TimeBodyAccelerometerMeanX/Y/Z`
* `TimeBodyAccelerometerSTDX/Y/Z`
* `TimeGravityAccelerometerMeanX/Y/Z`
* `TimeBodyGyroscopeMeanX/Y/Z`
* `FrequencyBodyAccelerometerMeanX/Y/Z`
* *(Note: There are 86 total measurement variables in the final set).*

## Transformations and Cleaning
1.  **Merging:** The `subject_train.txt`, `y_train.txt`, and `X_train.txt` files were merged with their "test" counterparts to create one large data frame.
2.  **Selection:** Using `grep`, only columns containing "mean" or "std" were retained.
3.  **Naming:** Numeric activity codes (1-6) were mapped to descriptive strings from `activity_labels.txt`.
4.  **Labeling:** Column names were cleaned using `gsub`:
    * `Prefix t` -> `Time`
    * `Prefix f` -> `Frequency`
    * `Acc` -> `Accelerometer`
    * `Gyro` -> `Gyroscope`
    * `Mag` -> `Magnitude`
5.  **Aggregation:** The data was grouped by subject and activity, and the `mean` function was applied to all remaining columns to create the final tidy dataset.

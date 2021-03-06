### Overview
This CodeBook describes the variables, the data, and any transformations or work that you performed to clean up the data.

#### Experimental Design and Data Collection
The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

#### List of Files Used in run_analysis.R script
* features.txt - List of all features
* activity_labels.txt - Links the class labels with their activity name.
* train/X_train.txt - Training data set.
* train/y_train.txt - Training labels.
* test/X_test.txt - Test data set.
* test/y_test.txt - Test labels.
* train/subject_train.txt - Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 

#### Data Trasformation 
Step 1 - Read and merge x_train with x_test, y_train with y_test, and subject_train with subject_test using rbind()

Step 2 - Subset data based on columns with features having mean() and std(). Column names are then formated by removing "()", capitalizing M and S (in mean and std) and removing hyphens.

Step 3 - Based on activity values, values are replaced with descriptive activiy lables from activitiy_lables.txt. The column name is renamed activity.

Step 4 - Column containing subject is renamed "subject". All data is joined into one large data table using cbind().

Step 5 - Calculates the average of each variable for each activity and each subject using plyr funcation. Write.table() is used to create an independent tidy dataset of the averages






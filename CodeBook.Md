The run_analysis.R script performs the data preparation and then followed by the 5 steps required as described in the course project’s definition.

Download the dataset
Dataset downloaded and extracted under the folder called UCI HAR Dataset

Assign each data to variables

features <- features.txt : 561 rows, 2 columns

The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.

activities <- activity_labels.txt : 6 rows, 2 columns
List of activities performed when the corresponding measurements were taken and its codes (labels)

subject_test <- test/subject_test.txt : 2947 rows, 1 column

contains test data of 9/30 volunteer test subjects being observed
x_test <- test/X_test.txt : 2947 rows, 561 columns

y_test <- test/y_test.txt : 2947 rows, 1 columns

subject_train <- test/subject_train.txt : 7352 rows, 1 column

x_train <- test/X_train.txt : 7352 rows, 561 columns

y_train <- test/y_train.txt : 7352 rows, 1 columns


Merges the training and the test sets to create one data set
X (10299 rows, 561 columns) is created by merging x_train and x_test using rbind() function

Y (10299 rows, 1 column) is created by merging y_train and y_test using rbind() function
Subject (10299 rows, 1 column) is created by merging subject_train and subject_test using rbind() function
Merged_Data (10299 rows, 563 column) is created by merging Subject, Y and X using cbind() function

Extracts only the measurements on the mean and standard deviation for each measurement
TidyData (10299 rows, 88 columns) is created by subsetting Merged_Data, selecting only columns: subject, code and the measurements on the mean and standard deviation (std) for each measurement

From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
FinalData (180 rows, 88 columns) is created by sumarizing TidyData taking the means of each variable for each activity and each subject, after groupped by subject and activity.
Export FinalData into FinalData.txt file.

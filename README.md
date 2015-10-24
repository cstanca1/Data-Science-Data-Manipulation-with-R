##### Getting and Cleaning Data - Data Project

Files:

    README.md -- current file
	CodeBook.md -- codebook describing variables, data and transformations
	run_analysis.R -- script with actual R code

Purpose:	

	Prepare tidy data that can be used for later analysis. 

Data: 

	https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 

Goals: 

	1. Merges the training and the test sets to create one data set. 
	2. Extracts only the measurements on the mean and standard deviation for each measurement. 
	3. Uses descriptive activity names to name the activities in the data set.
	4. Appropriately labels the data set with descriptive activity names. 
	5. Creates a second, independent tidy data set with the average of each variable for each activity and each subject. 

Pre-requisites:

	1. Data is unzipped to "./UCI HAR Dataset" folder. 
	2. The script assumes it has in it's "./UCI HAR Dataset" working directory the following files and folders:
		activity_labels.txt
		features.txt
		features_info.txt
		test/
		train/
	3. The output is created in working directory with the name of uci_har_tidy_data.txt.
	4. The R script is built to run installing needed packages if they are not existent: "data.table", "reshape2"

Steps:

	1. Load activity labels 
	2. Load data column names 
	3. Extract only the measurements on the mean and standard deviation for each measurement. 
	4. Load and process X_test & y_test data. 
	5. Extract only the measurements on the mean and standard deviation for each measurement. 
	6. Bind data 
	7. Load and process X_train & y_train data. 
	8. Extract only the measurements on the mean and standard deviation for each measurement. 
	9. Load activity data
	10. Bind data 
	11. Merge test and train data 
	12. Apply mean function to dataset using dcast function 
	13. Write tidy data with row.name=FALSE to "./uci_har_tidy_data.txt"
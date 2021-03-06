#Getting and Cleaning Data Project

Here is a code book that describes the variables, the data, and any transformations or work that I performed to clean up the data.

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 

For each record it is provided:

- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.

The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 

Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 

Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals). 

These signals were used to estimate variables of the feature vector for each pattern:  
'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.

I divided my work in four steps.

###Step 1
I downloaded the .zip file to my working directory and after that I unzipped it. I wrote an IF statement for us to avoid duplicates of this .zip file, i.e., if a file with that name already exists then R will not download it (it will just unzip it).
###Step 2
As a second step, I loaded the "features.txt" and "activity_labels.txt" files into R and do some manipulations. I used the read.csv function to read the .txt files I was interested on.
Then, I converted columns V2 to characters for me to be able to subset those related with the mean() and std() functions. After this transformation, I was now able to use the grep function to get only those features I was interested on (mean and std).  After I had the features I wanted, I edited the names of those features (I did the following changes: -mean()Mean, std()Standard Deviation). I did these changes by using the gsub function.
###Step 3
In this third step we loaded the following files into R:

•	X_train.txt

•	Y_train.txt

•	subject_train.txt

•	X_test.txt

•	Y_test.txt

•	subject_test.txt

After I loaded those files, I took a subset of the “X_train.txt” and “X_test.txt” files, i.e, I just saved the data I was interested on (data containing the features I mentioned previously). 
###Step 4
After Step3, I merged my data sets and I saved my new data frame in a variable called DATA. Then I assigned the correct names to all the columns of this new data frame. So my DATA had the following variables:


•	Subject                                
•	Activity                               
•	tBodyAccMeanX                          
•	tBodyAccMeanY                          
•	tBodyAccMeanZ                         
•	tBodyAccStandard.DeviationX            
•	tBodyAccStandard.DeviationY            
•	tBodyAccStandard.DeviationZ            
•	tGravityAccMeanX                       
•	tGravityAccMeanY                      
•	tGravityAccMeanZ                       
•	tGravityAccStandard.DeviationX         
•	tGravityAccStandard.DeviationY         
•	tGravityAccStandard.DeviationZ         
•	tBodyAccJerkMeanX                     
•	tBodyAccJerkMeanY                      
•	tBodyAccJerkMeanZ                      
•	tBodyAccJerkStandard.DeviationX        
•	tBodyAccJerkStandard.DeviationY        
•	tBodyAccJerkStandard.DeviationZ       
•	tBodyGyroMeanX                         
•	tBodyGyroMeanY                         
•	tBodyGyroMeanZ                         
•	tBodyGyroStandard.DeviationX           
•	tBodyGyroStandard.DeviationY          
•	tBodyGyroStandard.DeviationZ           
•	tBodyGyroJerkMeanX                     
•	tBodyGyroJerkMeanY                     
•	tBodyGyroJerkMeanZ                     
•	tBodyGyroJerkStandard.DeviationX      
•	tBodyGyroJerkStandard.DeviationY       
•	tBodyGyroJerkStandard.DeviationZ       
•	tBodyAccMagMean                        
•	tBodyAccMagStandard.Deviation          
•	tGravityAccMagMean                    
•	tGravityAccMagStandard.Deviation       
•	tBodyAccJerkMagMean                    
•	tBodyAccJerkMagStandard.Deviation      
•	tBodyGyroMagMean                       
•	tBodyGyroMagStandard.Deviation        
•	tBodyGyroJerkMagMean                   
•	tBodyGyroJerkMagStandard.Deviation     
•	fBodyAccMeanX                          
•	fBodyAccMeanY                          
•	fBodyAccMeanZ                         
•	fBodyAccStandard.DeviationX            
•	fBodyAccStandard.DeviationY            
•	fBodyAccStandard.DeviationZ            
•	fBodyAccMeanFreqX                      
•	fBodyAccMeanFreqY                     
•	fBodyAccMeanFreqZ                      
•	fBodyAccJerkMeanX                      
•	fBodyAccJerkMeanY                      
•	fBodyAccJerkMeanZ                      
•	fBodyAccJerkStandard.DeviationX       
•	fBodyAccJerkStandard.DeviationY        
•	fBodyAccJerkStandard.DeviationZ        
•	fBodyAccJerkMeanFreqX                  
•	fBodyAccJerkMeanFreqY                  
•	fBodyAccJerkMeanFreqZ                 
•	fBodyGyroMeanX                         
•	fBodyGyroMeanY                         
•	fBodyGyroMeanZ                         
•	fBodyGyroStandard.DeviationX           
•	fBodyGyroStandard.DeviationY          
•	fBodyGyroStandard.DeviationZ           
•	fBodyGyroMeanFreqX                     
•	fBodyGyroMeanFreqY                     
•	fBodyGyroMeanFreqZ                     
•	fBodyAccMagMean                       
•	fBodyAccMagStandard.Deviation          
•	fBodyAccMagMeanFreq                    
•	fBodyBodyAccJerkMagMean                
•	fBodyBodyAccJerkMagStandard.Deviation  
•	fBodyBodyAccJerkMagMeanFreq           
•	fBodyBodyGyroMagMean                   
•	fBodyBodyGyroMagStandard.Deviation     
•	fBodyBodyGyroMagMeanFreq               
•	fBodyBodyGyroJerkMagMean               
•	fBodyBodyGyroJerkMagStandard.Deviation
•	fBodyBodyGyroJerkMagMeanFreq


###Step 5
As a fifth step we transformed the Activity and Subject to factors for me to be able to create a tidy data set called “tidy.txt” with the average of each variable for each activity and each subject.

Activity Labels:

1 WALKING
2 WALKING_UPSTAIRS
3 WALKING_DOWNSTAIRS
4 SITTING
5 STANDING
6 LAYING

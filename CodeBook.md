#Getting and Cleaning Data Project

Here is a code book that describes the variables, the data, and any transformations or work that I performed to clean up the data.

I divided my work in four steps.

##Step 1
I downloaded the .zip file to my working directory and after that I unzipped it. I wrote an IF statement for us to avoid duplicates of this .zip file, i.e., if a file with that name already exists then R will not download it (it will just unzip it).
##Step 2
As a second step, I loaded the "features.txt" and "activity_labels.txt" files into R and do some manipulations.
First, to be able to load those files I needed to change my working directory to the folder called “UCI HAR Dataset”.   After this, I used the read.csv function to read the .txt files I was interested on.
Then, I converted columns V2 to characters for me to be able to subset those related with the mean() and std() functions. After this transformation, I was now able to use the grep function to get only those features I was interested on (mean and std).  After I had the features I wanted, I edited the names of those features (I did the following changes: -mean()Mean, std()Standard Deviation). I did these changes by using the gsub function.
##Step 3
In this third step we loaded the following files into R:
•	X_train.txt
•	Y_train.txt
•	subject_train.txt
•	X_test.txt
•	Y_test.txt
•	subject_test.txt
After I loaded those files, I took a subset of the “X_train.txt” and “X_test.txt” files, i.e, I just saved the data I was interested on (data containing the features I mentioned previously). 
##Step 4
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
##Step 5
As a fifth step we transformed the Activity and Subject to factors for me to be able to create a tidy data set called “tidy.txt” with the average of each va
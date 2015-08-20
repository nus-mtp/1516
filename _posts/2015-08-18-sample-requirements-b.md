---
layout: post
title: Sample Requirements A
---

These sample requirements are taken from a past CS3281/2 project.

## UC01 – Create a Device Set
System: X 
Actor: User  
Precondition: User must log in to X
Guarantees: A device set is created and can be used in setting configurations.

<!--more-->

### MSS: 
1. User searches devices by location from search box.  
2. System uses google map API to filter devices from map.  
3. User selects the devices.  
4. User confirms the selecting devices.  
5. User sets the device set name.  
6. User creates a new device set.  
7. System saves the device set. 
Use case ends.  

### Extensions: 
3a. No device has been chosen.  
3a1. System makes user reselect the devices.  
Use case resumes from step 4. 

5a.  User provides invalid device name.  
5a1.  System shows user the required field to fill up.  
Use case resumes from step 5. 
 

## UC02: Create a Configuration  
System: X
Actor: User
Precondition: User must log in to X.  
Guarantees: A configuration is created and viewable in the user’s configurations.  

### MSS
1. User sets the configuration.  
2. User creates a new configuration.  
3. System saves the configuration.  
4. Use case ends. 

### Extensions:  
1a. User does not provide enough information. 
1a1. System shows user the required field to fill up.  
Use case resumes from step 1. 
 
##UC03 Upload a Script  
System: X
Actor: User  
Precondition: The uploaded file must be a Python file with file extension .py.  Guarantees: A script is uploaded to the system. 

### MSS: 
1. User enters the name of a new script.  
2. User chooses the local file to be uploaded.  
3. User uploads the script.    
Use case ends. 

### Extensions: 
2a. File is too large. 
2a1. File is rejected by the system 
Use case resumes from step 2.  

2b. Received file is corrupted.             
2b1. Fail to upload. 
 Use case resumes from step 2. 

## UC04 – Create a Submission  
System: X
Actor: User  
Precondition: A configuration and script must be created first.  
Guarantees:  A new submission is created 

### MSS: 
1. User opens a new submission page.  
2. User inputs a name for the submission.  
3. User selects the script type of the submission.  
4. User selects a script from the corresponding script list.  
5. User selects the configuration to run the script.  
6. User executes the submission.  
7. System returns the submission status. 
Use case ends. 

## UC05 – Download and View Results  
System: X
Actor: User 
Precondition: A submission is made.
Guarantees: Results are downloaded and viewed.  

### MSS: 
1. User chooses one submission from all submissions.  
2. User downloads results. 
3. Use case ends. 

### Extensions: 
2a. The submission has not been completed 
2a1. User can download any results that have been saved by the script since
the submission started.
Use case ends. 

2b. There is a syntax error or exception 
2b1. Error messages will be downloaded as the result.                    
Use case ends. 

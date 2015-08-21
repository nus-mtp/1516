---
layout: post
title: Sample Requirements C
tag: example
date: 2015-08-20 15:37:00
---
This sample is taken from a past CS3283/4 project.

System Y is a software system project aiming to provide historians, history hobbyists, teachers, students as well as casual internet users a friendly and easy-to-use platform where users can create and browse well-visualized historical data in a unique way powered by modern web technologies.
<!--more-->

## USER STORIES

### USERS WHO WANT TO UPLOAD DATA (HISTORIAN, RESEARCHER, TEACHER...)

Users from this group can utilize the system to upload numerical data from their research to visualize their findings in a temporal visualization. This would be helpful especially when the numerical data is huge.

Users who are less-experienced with technology can choose to enter their data with a less complicated and less time consuming method to efficiently enter their data. This will gain merit among users who are less tech-savvy.

### USERS WHO ONLY WANT TO ACCESS THE SYSTEM’S DATA (HISTORIAN, RESEARCHER, STUDENT...)

Users from this group can view research of other researchers in a more interactive way (e.g. playing the temporal visualization to view temporal development/changes) to have a better understanding about the research.

## GENERAL REQUIREMENTS

* The language used in System Y should be English.
* The System Y should allow any user to browse the website.  This means the user may or may not be a registered user.
* The System Y should allow users to be able to view historical data on the website.
* The System Y should provide registered users with a map to allow them to add data
* The System Y should allow users to register for an account.
* The users in this case are people who want to upload data
* The System Y should allow registered users to upload their data onto the website.
* The System Y should be able to process the data that users upload.
* The System Y should be able to visualize the data that users upload.
* The System Y should provide registered users with the ability to keep their data private
* The System Y should have visual stimuli to present the historical information to users.
* The System Y should provide registered users with the ability to publish their data
* The uploading of data into the System Y should be an easy-to-use feature
* This means that registered users need not have computing knowledge in order to upload data. Also, they should learn how to use the system after one iteration of using it.
* The System Y should allow users to navigate through the website using intuition.
* This means there is no need for a tutorial on how to browse the website.
* The System Y should allow users to download information.
* The System Y should allow registered users to be able to track their own submissions with a single click of a mouse button.
* The System Y should be able to convert users’ data into graphs

## FEATURES LIST
* User can create an account
* User can login to their existing account
* User can edit their account information
* User can delete their account
* User can click on any link to view an entry
* Map visualization of statistical details
* 2-step interface to upload data
    * User chooses a time frame for their current data entry. The scale of the time frame can be specified from year to day. Data uploaded afterwards will correspond to the milestone.
    * Upload data
        * Upload data files: Users can use this function for massive data upload. The data should be uploaded in a specific data format (e.g. .xls).
        * Enter data manually:  Users can directly interact with the map and enter data or descriptions regarding the specific location.
* Scalability on maps: Users are able to zoom in and out of maps to view different degrees of detail, ranging from the most magnified view - the world view, to the most minified view - a province.
* Color coding: Data on maps are colored using temperature-based colors to represent their relative intensity
* Shareable web links: Users are able to share the direct link to their entry

## SYSTEM REQUIREMENTS

### 1. FUNCTIONAL REQUIREMENTS

#### A. USER CHARACTERISTICS
* Anonymous user: a user who hasn’t logged in to the system, having the ability to view public visualizations but not granted permission to comment or create new visualizations. They can log in or create a new account using their Facebook account.
* Registered user: a user who has logged in to the system using their Facebook account, having the ability to view visualizations, create/edit/delete their own visualizations and comment/like others’ visualizations.
* System admin: users who are granted special permissions on top of registered users, gaining the ability to delete/edit accounts and delete/edit other visualizations.

### 2. NON-FUNCTIONAL REQUIREMENTS

### A. DEVELOPMENT REQUIREMENTS
* Animated History will be a system built as a web application.
* Backend of the system will be developed on PHP 5+ using MySQL as the database manager. Lavarel
* CodeIgniter library will be used as the MVC framework for the project.
* Frontend of the system will take advantage of modern web technologies (HTML5, CSS3) and open
front-end APIs (specifically Google Maps API for map visualization).
* For the staging stage, the system can be developed on Windows/XAMPP or natively on Linux.
* The system will be deployed to a dedicated server that runs PHP.
* Git will be used as the version control for development, whereas GitHub will be used as the repository.

### B. OPERATION REQUIREMENTS
* The system should work on all modern browsers which support HTML5, provided that the user computer is connected to the internet (IE9+, Firefox 4+), with JavaScript enabled.
* The system should provide a backward-compliant method of displaying UI in case the browser doesn’t support displaying a particular web feature.
* If the browser is outdated (IE8- as such), the system should provide a notice telling the user to upgrade the browser rather than to proceed.
* The system should finish loading in 15 seconds, including the user interface and populated data.
* The system should provide a secured user authentication process, in which password and personal
identities should be encrypted during communication between server and client
* The system should provide a mechanism to protect itself from being over-requested (DDoS), for
which CAPTCHA is a preferred method.
* The system should provide clear, meaningful and friendly error notices to users; technical details of
the error should be logged but not shown to the user.
* The system should not log privately-stored data in users’ PC.

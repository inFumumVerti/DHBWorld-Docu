# DHBWorld - Software Requirements Specification 

## Table of contents
- [Table of contents](#table-of-contents)
- [Introduction](#1-introduction)
    - [Purpose](#11-purpose)
    - [Scope](#12-scope)
    - [Definitions, Acronyms and Abbreviations](#13-definitions-acronyms-and-abbreviations)
    - [References](#14-references)
    - [Overview](#15-overview)
- [Overall Description](#2-overall-description)
    - [Vision](#21-vision)
    - [Use Case Diagram](#22-use-case-diagram)
	- [Technology Stack](#23-technology-stack)
- [Specific Requirements](#3-specific-requirements)
    - [Functionality](#31-functionality)
    - [Usability](#32-usability)
    - [Reliability](#33-reliability)
    - [Performance](#34-performance)
    - [Supportability](#35-supportability)
    - [Design Constraints](#36-design-constraints)
    - [Online User Documentation and Help System Requirements](#37-on-line-user-documentation-and-help-system-requirements)
    - [Purchased Components](#38-purchased-components)
    - [Interfaces](#39-interfaces)
    - [Licensing Requirements](#310-licensing-requirements)
    - [Legal, Copyright And Other Notices](#311-legal-copyright-and-other-notices)
    - [Applicable Standards](#312-applicable-standards)
- [Supporting Information](#4-supporting-information)

## 1. Introduction

### 1.1 Purpose

Welcome to our Software Requirements Specification (SRS). Here we will describe all specifications for our android app "DHBWorld". This SRS will include an overview about our project and what we plan for it in the future. We will also mention and describe information about the planned features and general conditions of the development process.
We want to develop this app because there is currently not a working app for DHBW (Karlsruhe) students which contains a schedule (rapla), meal plan, your grades and  matriculation number. Also some features we thought that they would be nice like tram departure, notification about queue in the cafeteria and the floor plan. So we want to develop an app which contains these things and is actually working correctly.

### 1.2 Scope

The DHBWorld app, as mentioned in "1.1 Purpose", is going to be an android app.

Actors of this app can only be users.

The different features we want to include are:

* Schedule: 
  The schedule is one of our main features for this app. We want to use rapla to show the student his schedule on the app.
* Meal plan: 
  The meal plan should show the student the current meal for the day in the mensa at DHBW Karlsruhe.
* Dualis: 
  The dualis feature should give the user an easy way to look up his grades and we plan to realize a notification if a new grade is published.
* User information: 
  The user information is optional. You will have a page where you can note your student e-mail and matriculation number.
* Tram departure: 
  The tram departure page in our app shows the next few tram departures.
* Floor plan: 
  The floor plan page shows view of the DHBW building to give you an overview about where you are and where the next class is.
* Notification cafeteria, printer, coffee machine: 
  We want to give the user an opportunity to send a notification about the current queue in the cafeteria. If there are enough reports than all other users should get             notificated. The same idea is planned for the printer and the coffee machine at the DHBW.
  

### 1.3 Definitions, Acronyms and Abbreviations

| Abbrevation | Explanation                            |
| ----------- | -------------------------------------- |
| SRS         | Software Requirements Specification    |

### 1.4 References

| Title                                                              | Date       | Publishing organization   |
| -------------------------------------------------------------------|:----------:| ------------------------- |
| [DHBWorld Blog](https://dhbworldka.wordpress.com/blog/)    | 21.10.2021 | DHBWorld Team    |
| [GitHub](https://github.com/inFumumVerti/DHBWorld)              | 21.10.2021 | DHBWorld Team    |
| [YouTrack](https://dhbw-karlsruhe.myjetbrains.com/youtrack/projects/df88e1dd-ce27-4721-bcd7-7820e3aa60fc)              | 09.04.2022 | DHBWorld Team    |
| [Risk Management](https://lists.live.com/:l:/g/personal/b6fef5b2a43fbd53/FIHonHudZfhNtma8HXwP1dQBOCDV7yPLksiIXuwCKay1ZQ) | 24.04.2022 | DHBWorld Team |
### 1.5 Overview

The following chapter provides an overview of this project with vision and Overall Use Case Diagram. The third chapter (Requirements Specification) delivers more details about the specific requirements in terms of functionality, usability and design parameters. Finally there is a chapter with supporting information.

## 2. Overall Description

### 2.1 Vision

Inspired and also annoyed by current not working correctly DHBW android apps we want to develop the DHBWorld app to combine the most important things for a student at DHBW Karlsruhe. The features are explained in "1.2 Scope". We want to build the all in one app so that you have all the key features combined in one __working__ app. So the future students do not have to switch between apps which contains only one or two features.

### 2.2 Use Case Diagram

![alt text](https://raw.githubusercontent.com/inFumumVerti/DHBWorld-Docu/main/Use%20Case%20Diagram_new_new.svg "Use Case Diagram DHBWorld")

* Green: until december
* White: until june
* Yellow: optional
* Gray: updated use cases

### 2.3 Technology Stack

Languages: Java, XML

IDE: Android Studio

Source Control Management: GitHub

Project Management: Youtrack

Database: Firebase

## 3. Specific Requirements

### 3.1 Functionality

#### 3.1.1 Dashboard

The start page of DHBWorld should consist of small information-blocks from all parts of the app. This will be realised in form of customizible dashboard. User can configurate visible blocks there.

**Use Cases:**
* *[View personal Information:](https://github.com/inFumumVerti/DHBWorld-Docu/blob/main/Use%20Cases/View%20personal%20information.md)* User can save important personal Information and view his personal information he saved earlier
* *[Configure Dashboard:](https://github.com/inFumumVerti/DHBWorld-Docu/blob/main/Use%20Cases/Configure%20visible%20information%20on%20dashboard.md)* Configure the visible information of the dashboard

#### 3.1.2 Schedule
This part of the app will be an interface to connect with Rapla-Service to provide information about the DHBW-Schedule.

**Use Cases:**
* *[View schedule:](https://github.com/inFumumVerti/DHBWorld-Docu/blob/main/Use%20Cases/View%20schedule.md)* User can view his upcoming classes
* *Filter classes:* User can filter classes he want to see in the calender

#### 3.1.3 Meal plan
This feature will be an interface for connecting with the OpenMensa-Plattform to provide information about the meal plan for the DHBW.

**Use Cases:**
* *[Show day-plan:](https://github.com/inFumumVerti/DHBWorld-Docu/blob/main/Use%20Cases/Show%20daily%20mealplan.md)* User can see the meal plan for today
* *[Show weekly-plan:](https://github.com/inFumumVerti/DHBWorld-Docu/blob/main/Use%20Cases/Show%20weekly%20meal%20plan.md)* User can see the meal plan for the current week

#### 3.1.4 Organizer
This part of the app will consist of some organisational topics of DHBW, which are important specially for new students. Quick access to this information will save time of student's because they dont need to search on the DHBW-Website oder around the DHBW-Building. 

**Use Cases:**
* *View routes to specific room:* User can view the route to a selected room
* *View organizer:* User can view information about professors, rooms and courses like e-mail-address, phone number or room for a selected professor.

#### 3.1.5 User interaction
This feature will give all of the students a possibility to communicate anonymously with each other to optimize the dealing with problems like a broken coffee machine.

**Use Cases:**
* *Reporting events:* User can report specific events like a broken coffee machine
* *Receiving notifications:* User get a notification if a event gets reported enough

#### 3.1.6 Dualis
This part of the app will be an interface to connect with the Dualis-Service to provide information about personal grades.

**Use Cases:**
* *Logging in:* User can log in with their dualis credentials
* *Receive notifications:* User get a notification if a new grade gets published
* *Show grades in different views:* User can view the grades in a detailed view and in an overview

#### 3.1.7 Tram departure
This feature will be an interface to provide information about public transport near the DHBW through the KVV-API.

**Use Cases:**
* *View departures:* User can view the next tram departures of the DHBW station
* *View disruption:* User can view canceled trams

#### 3.1.8 Settings
The user can configure and personalise the app. 

**Use Cases:**
* *Configure notifications:* Change settings about app-notifications
* *Change design:* Change the design of the app
* *View information about App:* View information about the App like version, developers, etc.

### 3.2 Usability

#### 3.2.1 Familiar Feeling
With the use of the standatized Material UI design the App will be intuitive to use. Users can nagivate through the app in a familiar way.

#### 3.2.2 minimal setup for specific functions
For functions like dualis or the schedule the user only has to provide their credentials in order to get these functionalities.

### 3.3 Reliability

#### 3.3.1 Availability
The App will depend on quite a lot of external APIs in order to provide all of the funcitons. But all of these are well-known and need to function all the time, so they do have some high availability functions build in.

#### 3.3.2 Defect Rate
We will test the external APIs very extensively to make sure they meet our requirements.

### 3.4 Performance

#### 3.4.1 Capacity
Some of the external APIs are limeted to a specific amout of requests per timeunit. If the app will get more user than we expected we can always install a simple caching-server to slow down these requests.

#### 3.4.2 Storage 
We expect out app to be 40-50 MB in size which is no problem for phones with even limited storage like 16 GB.

#### 3.4.3 App perfomance / Response time
Because the app doesn't have to do a lot of calculations, searching, etc. we expect out app to run without any problems on nearly any phone.

### 3.5 Supportability

#### 3.5.1 Coding Standards
We will be using the language specific coding standards to make out code as clean and uniform as possible. We will also implement different "helper classes" in order to provide some translation for specific data.

#### 3.5.2 Testing Strategy
[Test Plan](https://github.com/inFumumVerti/DHBWorld-Docu/blob/main/Test%20plan.md)

### 3.6 Design Constraints
We use the standartized Material UI in order to keep our app clean looking for our users.
Internally we will use the MVC-architecture provided with the android framework.
Our minimum android version will be API Level 26 (Android Version 8.0) in order to support a wide range of devices.

### 3.7 On-line User Documentation and Help System Requirements
Our GitHub-Repository will be linked so users can ask for help, report bugs, or ask for more features. The functions inside the app will be well described.

### 3.8 Purchased Components
Nothing

### 3.9 Interfaces

#### 3.9.1 User Interfaces
n/a

#### 3.9.2 Hardware Interfaces
n/a

#### 3.9.3 Software Interfaces
Android API Level 26 (Android Version 8.0)

#### 3.9.4 Communication Interfaces
Ethernet

### 3.10 Licensing Requirements
[License](https://github.com/inFumumVerti/DHBWorld/blob/main/LICENSE.md)

### 3.11 Legal, Copyright, and Other Notices
[License](https://github.com/inFumumVerti/DHBWorld/blob/main/LICENSE.md)

### 3.12 Applicable Standards
TRIAS-Standard for Tram departures

## 4. Supporting Information
For more information check out our blog at: https://dhbworldka.wordpress.com/ 

# Made with ❤️ by:
| Name                                       | Username              |
| ------------------------------------------ | ----------------- |
| [Daria Kodolova](https://github.com/dk1553) | dk1553 and linus.pust@gmail.com | 
| [Linus Pust](https://github.com/inFumumVerti) | inFumumVerti	|
| [Christian Zäske](https://github.com/blitzdose) | blitzdose |
| [Adrian Kohl](https://github.com/KadrioL) | KadrioL |

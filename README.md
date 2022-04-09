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
### 1.5 Overview

The following chapter provides an overview of this project with vision and Overall Use Case Diagram. The third chapter (Requirements Specification) delivers more details about the specific requirements in terms of functionality, usability and design parameters. Finally there is a chapter with supporting information.

## 2. Overall Description

### 2.1 Vision

Inspired and also annoyed by current not working correctly DHBW android apps we want to develop the DHBWorld app to combine the most important things for a student at DHBW Karlsruhe. The features are explained in "1.2 Scope". We want to build the all in one app so that you have all the key features combined in one __working__ app. So the future students do not have to switch between apps which contains only one or two features.

### 2.2 Use Case Diagram

![alt text](https://raw.githubusercontent.com/inFumumVerti/DHBWorld-Docu/main/Use%20Case%20Diagram_new.svg "Use Case Diagram DHBWorld")

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

**Use Cases:**
* *Save personal Information:* User can save important personal Information
* *View personal Information:* User can view his personal information he saved earlier

#### 3.1.2 Schedule

**Use Cases:**
* *View schedule:* User can view his upcoming classes
* *Filter classes:* User can filter classes he want to see in the calender

#### 3.1.3 Meal plan

**Use Cases:**
* *Show day-plan:* User can see the meal plan for today
* *Show weekly-plan:* User can see the meal plan for the current week

#### 3.1.4 Organizer

**Use Cases:**
* *View routes to specific room:* User can view the route to a selected room
* *View information of professors:* User can view information like e-mail-address or room for a selected professor

#### 3.1.5 User interaction

**Use Cases:**
* *Reporting events:* User can report specific events like a broken coffee machine
* *Receiving notifications:* User get a notification if a event gets reported enough

#### 3.1.6 Dualis

**Use Cases:**
* *Logging in:* User can log in with their dualis credentials
* *Receive notifications:* User get a notification if a new grade gets published
* *Show grades in different views:* User can view the grades in a detailed view and in an overview

#### 3.1.7 Tram departure

**Use Cases:**
* *View departures:* User can view the next tram departures of the DHBW station

#### 3.1.8 Settings

**Use Cases:**
* *Configure notifications:* Change settings about app-notifications
* *Change design:* Change the design of the app
* *Configure Dashboard:* Configure the visible information of the dashboard
* *View information about App:* View information about the App like version, developers, etc.

### 3.2 Usability
tbd.

#### 3.2.1 No training time needed

#### 3.2.2 Familiar Feeling

### 3.3 Reliability

#### 3.3.1 Availability

#### 3.3.2 Defect Rate

### 3.4 Performance

#### 3.4.1 Capacity

#### 3.4.2 Storage 

#### 3.4.3 App perfomance / Response time

### 3.5 Supportability

#### 3.5.1 Coding Standards

#### 3.5.2 Testing Strategy

### 3.6 Design Constraints

### 3.7 On-line User Documentation and Help System Requirements

### 3.8 Purchased Components

### 3.9 Interfaces

#### 3.9.1 User Interfaces

#### 3.9.2 Hardware Interfaces

#### 3.9.3 Software Interfaces

#### 3.9.4 Communication Interfaces

### 3.10 Licensing Requirements

### 3.11 Legal, Copyright, and Other Notices

### 3.12 Applicable Standards

## 4. Supporting Information

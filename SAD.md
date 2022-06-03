# Software Architecture Document (SAD)

# Table of Contents
- [Introduction](#1-introduction)
    - [Purpose](#11-purpose)
    - [Scope](#12-scope)
    - [Definitions, Acronyms and Abbreviations](#13-definitions-acronyms-and-abbreviations)
    - [References](#14-references)
    - [Overview](#15-overview)
- [Architectural Representation](#2-architectural-representation)
- [Architectural Goals and Constraints](#3-architectural-goals-and-constraints)
- [Use-Case View](#4-use-case-view)
    - [Use-Case Realizations](#41-use-case-realizations)
- [Logical View](#5-logical-view)
    - [Overview](#51-overview)
    - [Architecturally Significant Design Packages](#52-architecturally-significant-design-packages)
    - [Design Patterns](#53-design-patterns)
- [Process View](#6-process-view)
- [Deployment View](#7-deployment-view)
- [Implementation View](#8-implementation-view)
    - [Overview](#81-overview)
    - [Layers](#82-layers)
- [Data View](#9-data-view)
- [Size and Performance](#10-size-and-performance)
- [Quality](#11-quality)

## 1. Introduction

### 1.1 Purpose
This document provides an overview of our software architecture. With several different architectural views it depicts different aspects of the system. It is intended to capture and convey the significant architectural decisions which have been made for the system.

### 1.2 Scope
This document describes the architecture of the DHBWorld project.

### 1.3 Definitions, Acronyms and Abbreviations

| Abbrevation | Description                            |
| ----------- | -------------------------------------- |
| MVC         | Model view controller                  |
| SRS         | Software requirements specification    |
| UC          | Use case                               |
| n/a         | not applicable                         |

### 1.4 References

| Title                                                              		| Date       | Publishing organization   |
| --------------------------------------------------------------------------|:----------:| ------------------------- |
| [DHBWorld Blog](https://dhbworldka.wordpress.com/)   		                | 2021-12-09 | DHBWorld Team     |
| [Repository on GitHub](https://github.com/inFumumVerti/DHBWorld)		    | 2021-12-09 | DHBWorld Team     |
| [UC1 Mealplan](./Use%20Cases/uc_mealplan.svg)           		            | 2021-12-09 | DHBWorld Team     |
| [UC2 Personal Information](./Use%20Cases/uc_personalinformation.svg)      | 2021-12-09 | DHBWorld Team     |
| [SRS](./README.md)                      		                            | 2021-12-09 | DHBWorld Team     |

### 1.5 Overview
This document contains the architectural representation, goals and constraints as well 
as the logical, deployment, implementation and data views.

## 2. Architectural Representation
This project uses the MVC Pattern for the front end (Android App) but most of the View-components are handled internally with xml files. The MVC Pattern can be seen in the next picture:

![MVC](./images/MVC.png)

## 3. Architectural Goals and Constraints

### MVC
As mentioned in chapter two our App is using the MVC pattern. This enables a clean software architecture with separate model view and controller.

### Front end
The Android App is written in Java. In the Frontend no MVC Tool is needed, because the MVC Pattern is integrated into the Android Framework.

## 4. Use-Case View
![Overall-Use-Case-Diagram](https://raw.githubusercontent.com/inFumumVerti/DHBWorld-Docu/main/Use%20Case%20Diagram_new_new.svg "Use Case Diagram DHBWorld")

* Green: until december
* White: until june
* Yellow: optional
* Gray: updated use cases

More information about functionality of the application and defined Use-Cases of the Project you can find in [SRS](./README.md).

## 5. Logical View

### 5.1 Overview
In our app we tried to combine all the classes which belong together into a different package. This way it is very clear to anyone who wants to edit the code where he/she can find the code he/she is looking for.

### 5.2 Architecturally Significant Design Packages
The following image shows one of our UML diagrams. Categorized in Model, View and Controller
![UML diagram UserInteraction](./Class%20Diagram/ClassDiagram_UserInteraction.svg)  
As you can see we only marked two classes as "View". As we mentioned in chapter two Android handles most of the "View" part internally and you only have to provide xml files to build the actual views.

### 5.3 Design Patterns
In our architecture we made use of patterns. One pattern we used was the Private Class Data Pattern. The goal of this pattern is protecting class state by minimizing the visibility of its attributes (data). The Private Class Data Pattern seeks to reduce exposure of attributes by limiting their visibility. 

We used  Private Class Data Pattern from the beginning of the project. KVV Class Diagramm is an example of it:
![KVV Class Diagramm](https://github.com/inFumumVerti/DHBWorld-Docu/blob/main/images/KVV_class_diagram_design_pattern.svg)

As you can see hier, all attributes in class Departure are private. KvvActivity Class uses getters to get their value. This pattern was necessary for protections of attributs of Departure-class. Another classes can use values of Departure-Attributes, but they shouldn't be able, to set own values for Departure-Attributes. 
Since we are using them from the beginning, we are not able to show you a before and after comparison. 

## 6. Process View
n/a

## 7. Deployment View
![Deployment diagram](https://raw.githubusercontent.com/inFumumVerti/DHBWorld-Docu/main/images/Deployment%20diagram.svg)
## 8. Implementation View
n/a
### 8.1 Overview
n/a
### 8.2 Layers
n/a

## 9. Data View
Our Database is handled with Firebase. There we don't use the classic ERM but rather a simple JSON structure that you can see in the image below. In the "issue"-object there are three sub-objects: cafeteria, coffee and printer for our three event-reporting-categories. In there we save the reports from the users.

![Database-diagram](./images/Database_strukture.png)

## 10. Size and Performance
n/a

## 11. Quality/Metrics
| class | CBO | DIT | NOC | RFC | WMC | Halstead Bugs | Halstead Difficulty |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
com.main.dhbworld.Calendar.Event | 2.0 | 1.0 | 0.0 | 10.0 | 8.0 | 0.058884047079352436 | 9.545454545454547
com.main.dhbworld.Calendar.EventCreator | 8.0 | 1.0 | 0.0 | 64.0 | 22.0 | 1.4370954678042014 | 110.98979591836735
com.main.dhbworld.Calendar.Events | 5.0 | 1.0 | 0.0 | 4.0 | 3.0 | 0.024514508341238885 | 4.285714285714286
com.main.dhbworld.Calendar.nextEventsProvider | 2.0 | 1.0 | 0.0 | 36.0 | 13.0 | 0.47980529761623614 | 55.53333333333333
com.main.dhbworld.Cantine.CantineUtilities | 2.0 | 1.0 | 0.0 | 9.0 | 5.0 | 0.19028299940573531 | 32.3
com.main.dhbworld.Cantine.Meal | 4.0 | 1.0 | 0.0 | 16.0 | 13.0 | 0.23156190404668872 | 30.86842105263158
com.main.dhbworld.Cantine.MealDailyPlan | 4.0 | 1.0 | 0.0 | 24.0 | 13.0 | 0.4426988509762396 | 48.41379310344828
com.main.dhbworld.CantineActivity | 15.0 | 9.0 | 0.0 | 80.0 | 28.0 | 2.89476095599458 | 156.7577319587629
com.main.dhbworld.DashboardActivity | 21.0 | 9.0 | 0.0 | 57.0 | 82.0 | 6.791596013780426 | 225.34615384615384
com.main.dhbworld.DataPrivacyActivity | 5.0 | 9.0 | 0.0 | 10.0 | 1.0 | 0.030137238289810332 | 7.5
com.main.dhbworld.Debugging.Debugging | 2.0 | 1.0 | 0.0 | 28.0 | 6.0 | 0.34106573948740165 | 38.0
com.main.dhbworld.Dualis.AReceiver | 1.0 | 2.0 | 0.0 | 2.0 | 1.0 | 0.004231947544565554 | 2.5
com.main.dhbworld.Dualis.BackgroundWorker | 7.0 | 3.0 | 0.0 | 59.0 | 6.0 | 0.6040070501049732 | 55.0
com.main.dhbworld.Dualis.DualisAPI | 18.0 | 1.0 | 0.0 | 92.0 | 44.0 | 2.7500975506966516 | 139.56302521008402
com.main.dhbworld.Dualis.DualisAPI.CourseDataLoadedListener |  |  |  | 1.0 |  |  | 
com.main.dhbworld.Dualis.DualisAPI.CourseErrorListener |  |  |  | 1.0 |  |  | 
com.main.dhbworld.Dualis.DualisAPI.DocumentsErrorListener |  |  |  | 1.0 |  |  | 
com.main.dhbworld.Dualis.DualisAPI.DocumentsLoadedListener |  |  |  | 1.0 |  |  | 
com.main.dhbworld.Dualis.DualisAPI.OverallDataLoadedListener |  |  |  | 1.0 |  |  | 
com.main.dhbworld.Dualis.DualisAPI.OverallErrorListener |  |  |  | 1.0 |  |  | 
com.main.dhbworld.Dualis.DualisDocument | 2.0 | 1.0 | 0.0 | 4.0 | 4.0 | 0.019153699757992665 | 4.5
com.main.dhbworld.Dualis.DualisDocumentAdapter | 6.0 | 2.0 | 0.0 | 22.0 | 5.0 | 0.21594811065651265 | 28.52173913043478
com.main.dhbworld.Dualis.DualisDocumentAdapter.ViewHolder | 3.0 | 2.0 | 0.0 | 3.0 | 1.0 | 0.021374342789906867 | 5.714285714285714
com.main.dhbworld.Dualis.DualisDocumentFragment | 12.0 | 2.0 | 0.0 | 44.0 | 10.0 | 0.42821564105049825 | 39.33695652173913
com.main.dhbworld.Dualis.DualisFragmentAdapter | 5.0 | 3.0 | 0.0 | 7.0 | 7.0 | 0.05826476403619942 | 10.818181818181818
com.main.dhbworld.Dualis.DualisOverallFragment | 12.0 | 2.0 | 0.0 | 51.0 | 10.0 | 0.629664255023958 | 50.942622950819676
com.main.dhbworld.Dualis.DualisParser | 2.0 | 1.0 | 0.0 | 62.0 | 35.0 | 1.8002915247769142 | 85.17948717948718
com.main.dhbworld.Dualis.DualisSemesterFragment | 12.0 | 2.0 | 0.0 | 57.0 | 12.0 | 0.874808496237176 | 72.88888888888889
com.main.dhbworld.Dualis.LoggedInView | 10.0 | 1.0 | 0.0 | 16.0 | 8.0 | 0.2107214990691616 | 23.903225806451612
com.main.dhbworld.Dualis.OverallCourseAdapter | 6.0 | 2.0 | 0.0 | 17.0 | 5.0 | 0.1881277825710014 | 24.64
com.main.dhbworld.Dualis.OverallCourseAdapter.ViewHolder | 3.0 | 2.0 | 0.0 | 3.0 | 1.0 | 0.025300389119935245 | 5.777777777777778
com.main.dhbworld.Dualis.OverallCourseModel | 2.0 | 1.0 | 0.0 | 6.0 | 6.0 | 0.0320815943809429 | 5.25
com.main.dhbworld.Dualis.SecureStore | 3.0 | 1.0 | 0.0 | 53.0 | 10.0 | 0.6939028500539967 | 54.93103448275862
com.main.dhbworld.Dualis.VorlesungAdapter | 6.0 | 2.0 | 0.0 | 17.0 | 7.0 | 0.7675925241204883 | 62.213114754098356
com.main.dhbworld.Dualis.VorlesungAdapter.MyViewHolder | 4.0 | 2.0 | 0.0 | 30.0 | 3.0 | 0.4663894452053526 | 45.23809523809524
com.main.dhbworld.Dualis.VorlesungModel | 3.0 | 1.0 | 0.0 | 5.0 | 5.0 | 0.023703620924169742 | 4.5
com.main.dhbworld.DualisActivity | 10.0 | 9.0 | 0.0 | 55.0 | 21.0 | 2.0295403776471703 | 134.73333333333332
com.main.dhbworld.Enums.InteractionState | 6.0 |  |  | 7.0 | 13.0 | 0.07202367529428721 | 6.764705882352942
com.main.dhbworld.Firebase.CurrentStatusListener |  |  |  | 1.0 |  |  | 
com.main.dhbworld.Firebase.DataSendListener |  |  |  | 2.0 |  |  | 
com.main.dhbworld.Firebase.Issue | 1.0 | 1.0 | 0.0 | 7.0 | 7.0 | 0.04283920571660523 | 9.333333333333334
com.main.dhbworld.Firebase.ReportCountListener |  |  |  | 1.0 |  |  | 
com.main.dhbworld.Firebase.SignedInListener |  |  |  | 2.0 |  |  | 
com.main.dhbworld.Firebase.TooManyClicksException | 1.0 | 3.0 | 0.0 | 2.0 | 1.0 | 0.0038186432128421402 | 2.5
com.main.dhbworld.Firebase.Utilities | 11.0 | 1.0 | 0.0 | 37.0 | 48.0 | 1.5695572993987392 | 103.63207547169812
com.main.dhbworld.Fragments.DialogCofirmationUserInteraction | 5.0 | 3.0 | 0.0 | 10.0 | 8.0 | 0.17754671153264864 | 27.692307692307693
com.main.dhbworld.KVV.DataLoaderListener |  |  |  | 1.0 |  |  | 
com.main.dhbworld.KVV.Departure | 6.0 | 1.0 | 0.0 | 7.0 | 7.0 | 0.03773104662723634 | 5.25
com.main.dhbworld.KVV.Disruption | 5.0 | 1.0 | 0.0 | 5.0 | 5.0 | 0.02903937837660743 | 5.0
com.main.dhbworld.KVV.KVVDataLoader | 8.0 | 1.0 | 0.0 | 52.0 | 17.0 | 0.8136446322567957 | 58.993421052631575
com.main.dhbworld.KVV.KVVListAdapter | 8.0 | 2.0 | 0.0 | 33.0 | 5.0 | 0.4307572757512007 | 46.467741935483865
com.main.dhbworld.KVV.KVVListAdapter.ViewHolder | 3.0 | 2.0 | 0.0 | 9.0 | 7.0 | 0.06458098639233258 | 9.615384615384615
com.main.dhbworld.KVVActivity | 11.0 | 9.0 | 0.0 | 72.0 | 11.0 | 0.9386772315590947 | 83.38888888888889
com.main.dhbworld.LicenseActivity | 6.0 | 9.0 | 0.0 | 15.0 | 1.0 | 0.057126634386159336 | 11.307692307692307
com.main.dhbworld.MainActivity | 6.0 | 9.0 | 0.0 | 30.0 | 16.0 | 1.3725779650178875 | 85.71428571428571
com.main.dhbworld.Navigation.NavigationUtilities | 12.0 | 1.0 | 0.0 | 10.0 | 14.0 | 0.1782422533685484 | 20.5
com.main.dhbworld.NetworkAvailability | 4.0 | 1.0 | 0.0 | 5.0 | 5.0 | 0.0658386765819414 | 12.571428571428571
com.main.dhbworld.Organizer.Course | 4.0 | 1.0 | 0.0 | 8.0 | 8.0 | 0.02952152068557086 | 5.333333333333333
com.main.dhbworld.Organizer.CourseDataHandler | 3.0 | 2.0 | 0.0 | 10.0 | 5.0 | 0.07484286885306186 | 21.25
com.main.dhbworld.Organizer.DataHandler | 3.0 | 1.0 | 3.0 | 1.0 | 0.0 | 0.0 | 0.0
com.main.dhbworld.Organizer.OrganizerActivity | 8.0 | 9.0 | 0.0 | 41.0 | 14.0 | 0.46372613808049257 | 45.47727272727273
com.main.dhbworld.Organizer.OrganizerCourseAdapter | 6.0 | 2.0 | 0.0 | 16.0 | 9.0 | 0.4107621638279016 | 39.13636363636363
com.main.dhbworld.Organizer.OrganizerCourseAdapter.ViewHolder | 3.0 | 2.0 | 0.0 | 3.0 | 1.0 | 0.020427161279358765 | 6.3
com.main.dhbworld.Organizer.OrganizerFragmentAdapter | 2.0 | 3.0 | 0.0 | 7.0 | 8.0 | 0.09844542473397155 | 17.307692307692307
com.main.dhbworld.Organizer.OrganizerOverallFragment | 15.0 | 2.0 | 0.0 | 38.0 | 15.0 | 0.5083773741097835 | 50.368421052631575
com.main.dhbworld.Organizer.OrganizerParser | 6.0 | 1.0 | 0.0 | 44.0 | 43.0 | 1.327644423167576 | 107.02325581395348
com.main.dhbworld.Organizer.OrganizerPersonAdapter | 6.0 | 2.0 | 0.0 | 17.0 | 9.0 | 0.3242316702809833 | 30.833333333333332
com.main.dhbworld.Organizer.OrganizerPersonAdapter.ViewHolder | 3.0 | 2.0 | 0.0 | 3.0 | 1.0 | 0.01790641806124263 | 5.6
com.main.dhbworld.Organizer.OrganizerRoomAdapter | 6.0 | 2.0 | 0.0 | 17.0 | 9.0 | 0.293637218708733 | 32.18181818181818
com.main.dhbworld.Organizer.OrganizerRoomAdapter.ViewHolder | 3.0 | 2.0 | 0.0 | 3.0 | 1.0 | 0.01790641806124263 | 5.6
com.main.dhbworld.Organizer.Person | 4.0 | 1.0 | 0.0 | 10.0 | 10.0 | 0.02873684162318899 | 4.166666666666667
com.main.dhbworld.Organizer.PersonDataHandler | 3.0 | 2.0 | 0.0 | 12.0 | 5.0 | 0.08717603909054795 | 23.07142857142857
com.main.dhbworld.Organizer.Room | 4.0 | 1.0 | 0.0 | 9.0 | 9.0 | 0.025246289192137814 | 4.6875
com.main.dhbworld.Organizer.RoomsDataHandler | 3.0 | 2.0 | 0.0 | 11.0 | 5.0 | 0.07594675492231913 | 20.57142857142857
com.main.dhbworld.Organizer.SearchResultsActivity | 0.0 | 5.0 | 0.0 | 9.0 | 4.0 | 0.043783001176375826 | 13.125
com.main.dhbworld.Organizer.SearchViewModel | 2.0 | 2.0 | 0.0 | 4.0 | 2.0 | 0.015818663387686963 | 6.75
com.main.dhbworld.ProgressIndicator | 2.0 | 1.0 | 0.0 | 11.0 | 6.0 | 0.12231058420360925 | 21.0
com.main.dhbworld.Services.UserInteractionMessagingService | 7.0 | 6.0 | 0.0 | 23.0 | 16.0 | 0.6581134819116559 | 65.52380952380952
com.main.dhbworld.SettingsActivity | 8.0 | 9.0 | 0.0 | 23.0 | 5.0 | 1.642703655384174 | 95.57425742574257
com.main.dhbworld.SettingsActivity.SettingsFragment | 12.0 | 3.0 | 0.0 | 55.0 | 28.0 | 1.186293970668809 | 73.69186046511628
com.main.dhbworld.UserInteraction | 10.0 | 9.0 | 0.0 | 47.0 | 51.0 | 2.2072276384319705 | 115.05747126436782
Total |  |  |  |  | 872.0 |  | 
Average | 5.9 | 2.9 | 0.04 | 21.4 | 11.9| 0.6009808320234812 | 42.42064756974269

**CBO** = Coupling between object Classes

**DIT** = Depth of inheritence tree

**NOC** = Number of children of a class

**RFC** = Response for Class

**WMC** = Weightened methods for class

The table above shows an overview of our current metrics, taken via MetricsReloaded in Android Studio.



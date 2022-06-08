# Use-Case Specification: Configure Visible Information On Dashboard

# 1. Use Case Brief Description
This use case allows users to view brief information from all of the app parts in one page called dashboard. It should contain the most important information from tram departures, schedule, meal plan, personal information and event reporting. Also user can configure visible information on dashboard and hide blocks of data, which he doesn't need.

All of the showed information is in the real time (for "now"):
* Tram departures: the next three trams departures 
* Schedule: next lecture's name with the time of the start or of the end of next lecture
* Meal plan: main courses for today
* Peronal information: view matriculation number, library number and student e-mail, if this information is already saved
* Reporting events: view current status of queue in canteen, coffemaker and printer

## 1.1 Mockup
We didn't designed view befor realization of use case. Design of the page view was left to the developer.

# 2. Flow of Events

## 2.1 Basic Flow

### Activity Diagram


### .feature File
![.feature file](https://github.com/inFumumVerti/DHBWorld-Docu/raw/main/Feature%20files/Featurefile%20configureVisisbleInformationOnDashboard.png)

## 2.2 Alternative Flows
n/a

## 2.3 Created View
![Screenshot](https://github.com/inFumumVerti/DHBWorld-Docu/raw/main/Screenshots/screenshot_configureVisiblaInformationOnDashboard.png)

# 3. Special Requirements
* API Open Mensa
* API Rapla
* API Kvv

# 4. Preconditions
The main preconditions for this use case are:

* The user has started the app and has navigated to the dashboard.
* The user has an active internet connection
* The OpenMensa Server is available
* The Rapla Server is available
* The Kvv Server is available

# 5. Postconditions
The app is able to use internal storage of the phone

### 5.1 Save changes
The information will be retrieved from the internal storage of the used phone

# 6. Function Points
We estimated this use case with 8 Story Points.

(Our Story Points scala: 1, 2, 3, 5, 8, 13)

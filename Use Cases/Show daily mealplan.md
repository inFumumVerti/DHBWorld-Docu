# Use-Case Specification: Show daily mealplan

# 1. Use Case Brief Description
This use case allows users to view the daily mealplan. Every meal has a brief description like a meal's name, price and notes about allergens or ingredients. The app get this information from OpenMensa Server.

## 1.2 Mockup 
![Mockup Mealplan](https://raw.githubusercontent.com/inFumumVerti/DHBWorld-Docu/main/Screenshots/screenshot_mealplan.svg)

# 2. Flow of Events

## 2.1 Basic Flow

### Activity Diagram
![Activity Diagram](https://raw.githubusercontent.com/inFumumVerti/DHBWorld-Docu/main/Use%20Cases/uc_mealplan.svg)

### .feature File
![.feature file](https://github.com/inFumumVerti/DHBWorld-Docu/blob/useCases/Feature%20files/Featurefile%20showDailyMealPlan.png)

## 2.2 Alternative Flows
n/a

## 3.2 Created View
![Screenshot](https://github.com/inFumumVerti/DHBWorld-Docu/blob/useCases/Screenshots/screenshot_showWeeklyMealPlan.png)

# 3. Special Requirements
 * OpenMensa-API

# 4. Preconditions
The main preconditions for this use case are:

 * The user has started the app and has navigated to the meal plan.
 * The user has an active internet connection
 * The OpenMensa Server is available

# 5. Postconditions
n/a

# 6. Function Points
We estimated this use case with 8 Story Points.

(Our Story Points scala: 1, 2, 3, 5, 8, 13)

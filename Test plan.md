# Test Plan

## Table of contents

- [1. Introduction](#1-introduction)
  * [1.1 Purpose](#11-purpose)
  * [1.2 Scope](#12-scope)
  * [1.3 Intended Audience](#13-intended-audience)
  * [1.4 Document Terminology and Acronyms](#14-document-terminology-and-acronyms)
  * [1.5  References](#15--references)
  * [1.6 Document Structure](#16-document-structure)
- [2. Evaluation Mission and Test Motivation](#2-evaluation-mission-and-test-motivation)
  * [2.1 Background](#21-background)
  * [2.2 Evaluation Mission](#22-evaluation-mission)
  * [2.3 Test Motivators](#23-test-motivators)
- [3. Target Test Items](#3-target-test-items)
- [4. Outline of Planned Tests](#4-outline-of-planned-tests)
  * [4.1 Outline of Test Inclusions](#41-outline-of-test-inclusions)
  * [4.2 Outline of Other Candidates for Potential Inclusion](#42-outline-of-other-candidates-for-potential-inclusion)
  * [4.3 Outline of Test Exclusions](#43-outline-of-test-exclusions)
- [5. Test Approach](#5-test-approach)
  * [5.1 Initial Test-Idea Catalogs and Other Reference Sources](#51-initial-test-idea-catalogs-and-other-reference-sources)
  * [5.2 Testing Techniques and Types](#52-testing-techniques-and-types)
    + [5.2.1 Data and Database Integrity Testing](#521-data-and-database-integrity-testing)
    + [5.2.2 Functional Testing](#522-functional-testing)
    + [5.2.3 Business Cycle Testing](#523-business-cycle-testing)
    + [5.2.4 User Interface Testing](#524-user-interface-testing)
    + [5.2.5 Performance Profiling](#525-performance-profiling)
    + [5.2.6 Load Testing](#526-load-testing)
    + [5.2.7 Stress Testing](#527-stress-testing)
    + [5.2.8 Volume Testing](#528-volume-testing)
    + [5.2.9 Security and Access Control Testing](#529-security-and-access-control-testing)
    + [5.2.10 Failover and Recovery Testing](#5210-failover-and-recovery-testing)
    + [5.2.11 Configuration Testing](#5211-configuration-testing)
    + [5.2.12 Installation Testing](#5212-installation-testing)
- [6. Entry and Exit Criteria](#6-entry-and-exit-criteria)
  * [6.1 Test Plan](#61-test-plan)
    + [6.1.1 Test Plan Entry Criteria](#611-test-plan-entry-criteria)
    + [6.1.2 Test Plan Exit Criteria](#612-test-plan-exit-criteria)
    + [6.1.3 Suspension and Resumption Criteria](#613-suspension-and-resumption-criteria)
  * [6.2 Test Cycles](#62-test-cycles)
      - [6.2.1 Test Cycle Entry Criteria](#621-test-cycle-entry-criteria)
      - [6.2.2 Test Cycle Exit Criteria](#622-test-cycle-exit-criteria)
      - [6.2.3 Test Cycle Abnormal Termination](#623-test-cycle-abnormal-termination)
- [7. Deliverables](#7-deliverables)
- [7.1 Test Evaluation Summaries](#71-test-evaluation-summaries)
- [7.2 Reporting on Test Coverage](#72-reporting-on-test-coverage)
- [7.3 Perceived Quality Reports](#73-perceived-quality-reports)
- [7.4 Incident Logs and Change Requests](#74-incident-logs-and-change-requests)
- [7.5 Smoke Test Suite and Supporting Test Scripts](#75-smoke-test-suite-and-supporting-test-scripts)
- [7.6      Additional Work Products](#76------additional-work-products)
  * [7.6.1     Detailed Test Results](#761-----detailed-test-results)
  * [7.6.2     Additional Automated Functional Test Scripts](#762-----additional-automated-functional-test-scripts)
  * [7.6.3     Test Guidelines](#763-----test-guidelines)
  * [7.6.4     Traceability Matrices](#764-----traceability-matrices)
- [8. Testing Workflow](#8-testing-workflow)
- [9. Environmental Needs](#9-environmental-needs)
  * [9.1 Base System Hardware](#91-base-system-hardware)
  * [9.2 Base Software Elements in the Test Environment](#92-base-software-elements-in-the-test-environment)
  * [9.3 Productivity and Support Tools](#93-productivity-and-support-tools)
  * [9.4 Test Environment Configurations](#94-test-environment-configurations)
- [10. Responsibilities, Staffing, and Training Needs](#10-responsibilities--staffing--and-training-needs)
  * [10.1 People and Roles](#101-people-and-roles)
  * [10.2 Staffing and Training Needs](#102-staffing-and-training-needs)
- [11. Iteration Milestones](#11-iteration-milestones)
- [12. Risks, Dependencies, Assumptions, and Constraints](#12-risks--dependencies--assumptions--and-constraints)
- [13. Management Process and Procedures](#13-management-process-and-procedures)

## 1. Introduction

### 1.1 Purpose

The purpose of the Iteration Test Plan is to gather all of the information necessary to plan and control the test effort for a given iteration. It describes the approach to testing the software.
This Test Plan for DHBWorld supports the following objectives:

- Identifies the items that should be targeted by the tests.
- Identifies the motivation for and ideas behind the test areas to be covered.
- Outlines the testing approach that will be used.
- Identifies the required resources and provides an estimate of the test efforts.

### 1.2 Scope

In our project we will be using functional testing using JUnit and AndroidJUnit4 for functional tests, Cucumber for UI tests and we will be doing a usability test with out users.

### 1.3 Intended Audience

This document is intended for internal documentation and overview over the testing enviroment. This is a living document with the intend of been completed at the end of the fourth semester.

### 1.4 Document Terminology and Acronyms

| Abbr | Abbreviation                        |
|------|-------------------------------------|
| API  | Application Programmable Interface  |
| CI   | Continuous Integration              |
| CD   | Continuous Delivery/Deployment      |
| n/a  | not applicable                      |
| SRS  | Software Requirements Specification |
| tbd  | to be determined                    |
| UI   | User Interface                      |
| VC   | Version Control                     |
| TDD  | Test Driven Development             |

### 1.5  References

| Title                                                              | Date       | Publishing organization   |
| -------------------------------------------------------------------|:----------:| ------------------------- |
| [DHBWorld Blog](https://dhbworldka.wordpress.com/blog/)    | 21.10.2021 | DHBWorld Team    |
| [GitHub](https://github.com/inFumumVerti/DHBWorld)              | 21.10.2021 | DHBWorld Team    |
| [YouTrack](https://dhbw-karlsruhe.myjetbrains.com/youtrack/projects/df88e1dd-ce27-4721-bcd7-7820e3aa60fc)              | 09.04.2022 | DHBWorld Team    |
| [Risk Management](https://lists.live.com/:l:/g/personal/b6fef5b2a43fbd53/FIHonHudZfhNtma8HXwP1dQBOCDV7yPLksiIXuwCKay1ZQ) | 24.04.2022 | DHBWorld Team |

### 1.6 Document Structure

See table of contents.


## 2. Evaluation Mission and Test Motivation

### 2.1 Background

Testing serves to ensure that the written code does what it is intended to do. It also prevents future code changes to break existing functionality unnoticed. In the context of integration it can also prevent broken software states to be merged into secured VC branches.

### 2.2 Evaluation Mission

The goals of testing is the improvement and preservation of the functionality and quality of the project. Therefore the tests are focused on reporting issues with functionality and quality. Also bugs should be minimized.

### 2.3 Test Motivators

These test support the effort of better quality, less bugs and faster development.

## 3. Target Test Items

The listing below identifies those test items software, hardware, and supporting product elements ¾that have been identified as targets for testing. This list represents what items will be tested.

- Android Devices
  - From API Level 26 up to Level 31
  - Different screen sizes

## 4. Outline of Planned Tests

### 4.1 Outline of Test Inclusions

*Frontend/Backend: Android Client*:

- UI testing of views/fragments
- Unit testing

The tests themself will not be tested and will not account into code coverage.

### 4.2 Outline of Other Candidates for Potential Inclusion

n/a

### 4.3 Outline of Test Exclusions

We will not test any external API to be working directly because all the APIs are actively maintained and we expect them to be tested by the creators.

## 5. Test Approach

### 5.1 Initial Test-Idea Catalogs and Other Reference Sources

n/a

### 5.2 Testing Techniques and Types

#### 5.2.1 Data and Database Integrity Testing

n/a

#### 5.2.2 Functional Testing

| Unit Tests            | Description                                                                             |
|-----------------------|-----------------------------------------------------------------------------------------|
|Technique Objective    |  Test basic functionality of single components.                                         |
|Technique              |  JUnit4 / AndroidJUnit4 Tests                                                           |
|Oracles                |  Checks asserted output of a basic function against the output of the implementation.   |
|Required Tools         |  JUnit4 / AndroidJUnit4                                                                 |
|Success Criteria       |  The asserted output is identical to the generated output.                              |
|Special Considerations |  Random generation of inputs must be expected when handling cryptographic instructions. |

#### 5.2.3 Business Cycle Testing

n/a

#### 5.2.4 User Interface Testing

| UI Tests              | Description                                                         |
|-----------------------|---------------------------------------------------------------------|
|Technique Objective    | Simulation of UI interaction.                                       |
|Technique              | UI Tests                                                            |
|Oracles                | Interactions with UI components through touch screen input.         |
|Required Tools         | Cucumber                                                            |
|Success Criteria       | All tests pass with the intended result.                            |
|Special Considerations | -                                                                   |

#### 5.2.5 Performance Profiling

n/a


#### 5.2.6 Load Testing

n/a


#### 5.2.7 Stress Testing

n/a


#### 5.2.8 Volume Testing

n/a


#### 5.2.9 Security and Access Control Testing

n/a

#### 5.2.10 Failover and Recovery Testing

n/a


#### 5.2.11 Configuration Testing

n/a


#### 5.2.12 Installation Testing

n/a

## 6. Entry and Exit Criteria

### 6.1 Test Plan

#### 6.1.1 Test Plan Entry Criteria

n/a

#### 6.1.2 Test Plan Exit Criteria

n/a

#### 6.1.3 Suspension and Resumption Criteria

n/a

### 6.2 Test Cycles

##### 6.2.1 Test Cycle Entry Criteria

n/a

##### 6.2.2 Test Cycle Exit Criteria

n/a

##### 6.2.3 Test Cycle Abnormal Termination

n/a


## 7. Deliverables

## 7.1 Test Evaluation Summaries

n/a

## 7.2 Reporting on Test Coverage

The Test-Coverage will be determined by Jacoco an visualized by CodeClimate.

## 7.3 Perceived Quality Reports

n/a

## 7.4 Incident Logs and Change Requests

We use GitHub Actions to automate our tests on every pull request and push. We will be notified by E-Mail if a test fails. The testing itself is done by a self hosted linux machine.

## 7.5 Smoke Test Suite and Supporting Test Scripts

n/a

## 7.6      Additional Work Products
n/a

### 7.6.1     Detailed Test Results
n/a

### 7.6.2     Additional Automated Functional Test Scripts

n/a

### 7.6.3     Test Guidelines
n/a

### 7.6.4     Traceability Matrices
n/a



## 8. Testing Workflow

1. Local testing in the IDE
2. Push to a branch will trigger automated builds and tests
3. Pull Requests to the main branch will trigger these builds and tests too

## 9. Environmental Needs

### 9.1 Base System Hardware

The following table sets forth the system resources for the test effort presented in this Test Plan.

| Resource                                                                | Quantity | Name and Type                           |
|-------------------------------------------------------------------------|:--------:|-----------------------------------------|
| CI/CD Testing Server                                                    |1         |Self hosted Linux Machine (Debian 11)    |
| Local Test Machine                                                      |3         |Each team members own developing device  |
| Android virtual test device                                             |3         |Virtual devices created in Android Studio|
| Android test device                                                     |3         |Each team members own Android device     |

### 9.2 Base Software Elements in the Test Environment

The following base software elements are required in the test environment for this Test Plan.

| Software Element Name |  Type and Other Notes                        |
|-----------------------|----------------------------------------------|
| Android Studio        | Test Runner / IDE                            |
| JUnit 4               | Unit testing library                         |
| AndroidJUnit 4        | Unit testing library                         |
| Cucumber              | human readable test definitions              |
| Jacoco                | Code coverage tool                           |

### 9.3 Productivity and Support Tools

tbd.

The following tools will be employed to support the test process for this Test Plan.

| Tool Category or Type             | Tool Brand Name                | Vendor or In-house |
|-----------------------------------|--------------------------------|--------------------|
| Repository                        | [GitHub](github.com)           | Vendor             |
| Test Coverage Monitor             | [CodeClimate](codeclimate.com) | Vendor             |
| Metrics Tool                      | [CodeClimate](codeclimate.com) | Vendor             |
| CI/CD Service                     | GitHub Action Runner           | In-house           |

### 9.4 Test Environment Configurations

n/a

## 10. Responsibilities, Staffing, and Training Needs

### 10.1 People and Roles

tbd.

This table shows the staffing assumptions for the test effort.

| Role                      | Person Assigned                           |  Specific Responsibilities or Comments                                   |
|---------------------------|:-----------------------------------------:|--------------------------------------------------------------------------|
| Test Manager              | tbd                                       | Provides management oversight.                                           |
| Test Designer             | tbd                                       | Defines the technical approach to the implementation of the test effort. |
| Test System Administrator | [Christian](https://github.com/blitzdose) | Ensures test environment and assets are managed and maintained.          |


### 10.2 Staffing and Training Needs

n/a

## 11. Iteration Milestones

We want to keep over 15% code coverage.

## 12. Risks, Dependencies, Assumptions, and Constraints

| Risk                                                                     | Mitigation Strategy                 | Contingency (Risk is realized) |
|--------------------------------------------------------------------------|-------------------------------------|--------------------------------|
| [See Risk Management](https://dhbworldka.wordpress.com/2022/04/15/week-12-risky-business/) | Continuous Risk Management            | Version Control                |

## 13. Management Process and Procedures

n/a

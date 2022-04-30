# Test Plan Template

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

tbd.
[Provide a brief outline of both the form and content of the reports used to measure the extent of testing, and indicate how frequently they will be produced. Give an dication as to the method and tools used to record, measure, and report on the extent of testing.]

## 7.3 Perceived Quality Reports

n/a

## 7.4 Incident Logs and Change Requests

tbd.
[Provide a brief outline of both the method and tools used to record, track, and manage test incidents, associated change requests, and their status.]

## 7.5 Smoke Test Suite and Supporting Test Scripts

n/a

## 7.6      Additional Work Products
n/a

### 7.6.1     Detailed Test Results
n/a

### 7.6.2     Additional Automated Functional Test Scripts

tbd.
[These will be either a collection of the source code files for automated test scripts, or the repository of both source code and compiled executables for test scripts maintained by the test automation product.]

### 7.6.3     Test Guidelines
n/a

### 7.6.4     Traceability Matrices
n/a



## 8. Testing Workflow
tbd.

[Provide an outline of the workflow to be followed by the test team in the development and execution of this Test Plan.
The specific testing workflow that you will use should be documented separately in the project's Development Case. It should explain how the project has customized the base RUP test workflow (typically on a phase-by-phase basis). In most cases, we recommend you place a reference in this section of the Test Plan to the relevant section of the Development Case. It might be both useful and sufficient to simply include a diagram or image depicting your test workflow.
More specific details of the individual testing tasks are defined in a number of different ways, depending on project culture; for example:
* defined as a list of tasks in this section of the Test Plan, or in an accompanying appendix
* defined in a central project schedule (often in a scheduling tool such as Microsoft Project)
* documented in individual, "dynamic" to-do lists for each team member, which are usually too detailed to be placed in the Test Plan
* documented on a centrally located whiteboard and updated dynamically
* not formally documented at all
Based on your project culture, you should either list your specific testing tasks here or provide some descriptive text explaining the process your team uses to handle detailed task planning and provide a reference to where the details are stored, if appropriate.
For Master Test Plans, we recommend avoiding detailed task planning, which is often an unproductive effort if done as a front-loaded activity at the beginning of the project. A Master Test Plan might usefully describe the phases and the number of iterations, and give an indication of what types of testing are generally planned for each Phase or Iteration.
Note: Where process and detailed planning information is recorded centrally and separately from this Test Plan, you will have to manage the issues that will arise from having duplicate copies of the same information. To avoid team members referencing out-of-date information, we suggest that in this situation you place the minimum amount of process and planning information within the Test Plan to make ongoing maintenance easier and simply reference the "Master" source material.]

## 9. Environmental Needs

[This section presents the non-human resources required for the Test Plan.]

### 9.1 Base System Hardware

tbd.

[The specific elements of the test system may not be fully understood in early iterations, so expect this section to be completed over time. We recommend that the system simulates the production environment, scaling down the concurrent access and database size, if and where appropriate.]

The following table sets forth the system resources for the test effort presented in this Test Plan.

| Resource                                                                | Quantity | Name and Type |
|-------------------------------------------------------------------------|----------|---------------|
| Database Server                                                         |          |               |
| - Network or Subnet                                                     |          | TBD           |
| - Server Name                                                           |          | TBD           |
| - Database Name                                                         |          | TBD           |
| Client Test PCs                                                         |          |               |
| - Include special configuration requirements                            |          | TBD           |
| Test Repository                                                         |          |               |
| - Network or Subnet                                                     |          | TBD           |
| - Server Name                                                           |          | TBD           |
| Test Development PCs                                                    |          | TBD           |

### 9.2 Base Software Elements in the Test Environment

The following base software elements are required in the test environment for this Test Plan.

| Software Element Name |  Type and Other Notes                        |
|-----------------------|----------------------------------------------|
| Android Studio        | Test Runner / IDE                            |
| JUnit 4               | Unit testing library                         |
| AndroidJUnit 4        | Unit testing library                         |
| Cucumber              | human readable test definitions              |

[These are examples!]

### 9.3 Productivity and Support Tools

tbd.

The following tools will be employed to support the test process for this Test Plan.

| Tool Category or Type             | Tool Brand Name | Vendor or In-house | Version |
|-----------------------------------|-----------------|--------------------|---------|
| Test Management                   |                 |                    |         |
| Defect Tracking                   |                 |                    |         |
| ASQ Tool for functional testing   |                 |                    |         |
| ASQ Tool for performance testing  |                 |                    |         |
| Test Coverate Monitor or Profiler |                 |                    |         |
| Project Management                |                 |                    |         |
| DBMS tools                        |                 |                    |         |

### 9.4 Test Environment Configurations

tbd.

The following Test Environment Configurations need to be provided and supported for this project.

| Configuration Name                | Description | Implemented in Physical Configuration |
|-----------------------------------|-------------|---------------------------------------|
| Average user configuration        |             |                                       |
| Minimal configuration supported   |             |                                       |
| Visually and mobility challenged  |             |                                       |
| International Double Byte OS      |             |                                       |
| Network installation (not client) |             |                                       |

## 10. Responsibilities, Staffing, and Training Needs

### 10.1 People and Roles

tbd.

This table shows the staffing assumptions for the test effort.

| Human Resources                          |                                                                         |                                                                                                                                                                                                                                                                                   |
|------------------------------------------|-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Role                                     | Minimum Resources Recommended (number of full-time roles allocated)     | Specific Responsbilities or Comments                                                                                                                                                                                                                                              |
| Test Manager                             |                                                                         | Provides management oversight. Responsibilities include: planning and logistics agree mission identify motivators acquire appropriate resources present management reporting advocate the interests of test evaluate effectiveness of test effort                                 |
| Test Analyst                             |                                                                         | Identifies and defines the specific tests to be conducted. Responsibilities include: identify test ideas define test details determine test results document change requests evaluate product quality                                                                             |
| Test Designer                            |                                                                         | Defines the technical approach to the implementation of the test effort. Responsibilities include: define test approace define test automation architecture verify test techniques define testability elements structure test implementation                                      |
| Tester                                   |                                                                         | Implements and executes the tests. Responsibilities include: implement tests and test suites execute test suites log results analyze and recover from test failures document incidents                                                                                            |
| Test System Administrator                |                                                                         | Ensurs test environment and assets are managed and maintained. Responsibilities include: administer test management system install and support access to, and recovery of, test environment configurations and test labs                                                          |
| Database Administrator, Database Manager |                                                                         | Ensures test data (database) environment and assets are managed andmaintained. Responsibilities include: support the administration of test data and test beds (database)                                                                                                         |
| Designer                                 |                                                                         | Identifies and defines the operations, attributes, and associations of the test classes. Responsibilities include: defines the test classes required to support testability requirements as defined by the test team                                                              |
| Implementer                              |                                                                         | Implements and unit tests the test classes and test packages. Responsibilities include: creates the test components required to support testability requirements as defined by the designer                                                                                       |

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

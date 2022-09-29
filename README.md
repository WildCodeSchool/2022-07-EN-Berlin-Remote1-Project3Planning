# 2022-07-EN-Berlin-Remote1-Project3Planning
Contains the planning and the design documentation for the industry project with REMONDIS group.

# Planning

## Timeline (WIP)

```mermaid
gantt
dateFormat  YYYY-MM-DD
axisFormat  %W
title GANTT Chart for the Development of a Fullstack Decluttering App for REMONIDS
excludes weekends

section A section
Negotiations                    :active,  des1, 2022-09-29, 2d
Design (API and data)           :         des2, after des1, 4d
Frontend skeleton               :         des3, after des2, 5d
Backend skeleton                :         des4, after des2, 5d
Dev environment (data, tests)   :         des5, after des2, 5d
Retr.                           :         des6, after des3 after des4 after des5, 1d
```

## Teams

- _Architects_: people who devise the "schema" of data layers and "endpoints" of API interfaces. In later stages they help create a development environment for other teams including providing sample data, unit tests, demanding architectural changes (i.e. refactoring), and monitoring code quality overall.
- _Designers_: people who devise the LoFi wireframes in the beginning of the project. In later stages they do the actual design including the Figma mockups. Upon approval they move to providing the styled components (writing CSS from scratch or using any framework/library they deem appropriate). These people will also look after useability and responsive design, it is a massive job.
- _Frontend_: people who use React.js or Next.js in any way they deem appropriate to build the logic of the frontend (i.e. browser) application. They are responsible for the offering a great functional experience. Using local storage, form constraints, and a great camera experience on mobile for the _inspector_ user role. The use of any state manager or form validation library is allowed and encouraged.
- _Backend_: people who use Express, Fastify or any other NodeJS framework to build the backend while implementing the API precisely as designed by the _architects_.

# Design

## User roles

- _Manager_: is the user role capable of creating new cases
- _Inspector_: is the user role capable of filling in "inspection data" into a case that had been assigned to them

## Case state diagram

```mermaid
stateDiagram-v2
    state "CREATED  (a manager just created the case)" as created
    state "RESERVED (an inspector expressed his intention to take-on the inspection)" as reserved
    state "PARTIALLY-INSPECTED (some inspection data has been entered, some still missing)" as partial
    state "FULLY-INSPECTED (all inspection information has been entered)" as full
    state "QUOTED (customer sent a quote)" as quoted
    
    [*] --> created: A manager creates a fresh case
    created --> reserved: An inspector reserves a freshly created case
    reserved --> created: An inspector releases the case before entering any data
    reserved --> full: An inspector fills all the information
    reserved --> partial: An inspector fills some of the information
    partial --> reserved: An inspect re-reserves a case to fill in more information
    full --> quoted: A manager sends a quote to the customer
```

## Inspection data fields

_TODO_

## REST API design

To be provided using OpenAPI (i.e. Swagger).

## Database Schema

_TODO_

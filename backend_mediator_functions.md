Those mediator functions are implemented in the Frontend repo at this location: https://github.com/WildCodeSchool/2022-07-EN-Berlin-Remote1-Project3Frontend/blob/mock-api/src/api/api.ts

# What & Why

The Frontend of the REMONDIS internal de-cluttering application relies on the Backend to perform functions related to the core logic of the application, including logging in as well as creating/viewing, assigning, editing, and submitting de-cluttering cases.

The Backend provides a REST API that is served using the HTTP(s) protocol. Using this API involves making requests over a network.

To create separation between the Frontend and the Backend during development, we have decided to use a set of mediator functions.

## Mock implementation

During development, the functions give back meaningful data that is stored in memory, while still implementing the application logic. This is important, for us to be able to create a meaningful demo during Backend development.

## Actual implementation

As the Backend enters testing and gets deployed, we are able to change these mediator functions to Fetch the data using the actual Endpoints from the API, without changing the code in the Frontend.

## Current list of functions

```
  apiGetAppointments,
  apiPostAppointment,
  apiGetAppointmentById,
  apiPutAppointmentById,
  apiDeleteAppointmentById,
  
  apiGetCases,
  apiGetCasesToDo,
  apiPostCases,
  apiGetCasesById,
  apiPatchCaseById,
  apiPutCasesById,
  apiPatchCasesByIdAssign,
  apiPatchCasesByIdDecline,
  apiPatchCasesByIdAccept,
  apiPatchCasesByIdReady,
  apiPatchCasesByIdQuote,
  apiPatchCasesByIdClose,
  
  apiGetCaseItems,
  apiGetCaseItem,
  apiPostCaseItem,
  apiPutCaseItem,
  apiDeleteCaseItem,
  
  apiGetUsersList,
  apiGetUsersListById,
  apiDeleteUsersById,
  apiPostUsersRegister,
  apiPostUsersConfirm,
  apiGetUsersLogin,
  apiGetUsersForgotPassword,
  apiPatchUsersSetNewPassword,
  
```

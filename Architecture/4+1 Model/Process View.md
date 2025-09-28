From [[L4-design.pdf]] the **Process** view of the **4+1 Architecture Model:**
- Deals with dynamic aspects of the system
- Explains system processes and how they communicate
- Focusses on runtime behaviour of the system
- Includes sequence state diagram

We also include some user flow diagrams here (see the [[#User Flow]] section)

## Use Case Diagram

An approximate **use case diagram** for ICN Navigator (subject to future requirement changes).

![[use case diagram.png]]

## (Select) System Sequence Diagram/s

### US02 Account Signup & Login

This sequence diagram shows how a new user creates an account. The user enters their email in the frontend, which sends a signup request to the backend. The backend communicates with an external authentication service to register the user. After successful creation, the backend stores the user record in the database and returns a success response to the frontend. The frontend then displays a confirmation message to the user.

![[Sequence Diagram US02.png]]

NOTE: this is for free tier, subscription sign/up/login will be more complex - this will need to be updated once the payment provider is confirmed.

### US05 Map Result Filtering

This sequence diagram explains how users filter company results. The user selects filter options in the frontend, which sends a request with the filter parameters to the backend. The backend queries the database and returns filtered company results. The frontend updates both the map pins and the list view in parallel. If no results are found, a “No matches” message is shown. If there are more results, the user can scroll to load the next page of data, and the frontend appends the new items while keeping the map synchronised.

![[Sequence Diagram US05.png]]

## User Flow 

### App Setup

A **user flow** diagram covering the app setup phase of the app. NOTE: error flows are omitted for clarity.

![[app-setup-user-flow.pdf]]



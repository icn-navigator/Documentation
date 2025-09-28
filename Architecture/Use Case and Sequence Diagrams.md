## Use Case Diagram

![[use case diagram.png]]

## Sequence Diagram

### US02 Account Signup & Login

This sequence diagram shows how a new user creates an account. The user enters their email in the frontend, which sends a signup request to the backend. The backend communicates with an external authentication service to register the user. After successful creation, the backend stores the user record in the database and returns a success response to the frontend. The frontend then displays a confirmation message to the user.

![[Sequence Diagram US02.png]]

NOTE: this is for free tier, subscription sign/up/login will be more complex - this will need to be updated once the payment provider is confirmed.

### US03 Map View

This sequence diagram describes how the user loads and interacts with the map. When the user opens the map page, the frontend requests map tiles from the map service and queries the backend for company data within the current viewport. The backend retrieves the data from the database and returns it to the frontend, which renders pins on the map. When the user pans or zooms, the frontend repeatedly fetches updated company data for the new viewport, keeping the map interactive and synchronized.

![[Sequence Diagram US03.png]]

### US05 Map Result Filtering

This sequence diagram explains how users filter company results. The user selects filter options in the frontend, which sends a request with the filter parameters to the backend. The backend queries the database and returns filtered company results. The frontend updates both the map pins and the list view in parallel. If no results are found, a “No matches” message is shown. If there are more results, the user can scroll to load the next page of data, and the frontend appends the new items while keeping the map synchronised.

![[Sequence Diagram US05.png]]
## Priority Explanation – MoSCoW Method
To help our team allocate resources and time effectively, we use the **MoSCoW prioritization method** to define the urgency and importance of each user story. This method breaks down 
features into four categories:
- **Must-Have:** Initiatives that must not lack in your product.
- **Should-Have:** Essential initiatives but not vital in your product.
- **Could-Have:** Initiatives that are nice to have in your product.
- **Won't-Have:** Initiatives that are not the priorities in your product.

## Story Point##
We use PlanningPokerOnline.com as a collaborative tool to estimate story points through team voting. Each team member selects a number representing their estimate, and the team discusses discrepancies to reach a consensus.

We apply the Fibonacci sequence (0, 1, 2, 3, 5, 8, 13, 21, ...) as the voting scale. This sequence reflects increasing uncertainty and effort as task complexity grows, making it ideal for agile estimation.

Reason of Choosing Fibonacci: 
- Encourage discussion on tasks with large gaps in estimates
- Reflect the relative size and risk of each user story
- Provide a simple yet effective scale for general sense building

Please vote for the story point via the link. 
**Voting Link:** https://planningpokeronline.com/hEsEctBQ3fbNNypoIAH0/
Fibonacci specification as followed:

| **Point** | **Effort Level** | **Description**                                                          |
| --------- | ---------------- | ------------------------------------------------------------------------ |
| **1**     | Very Easy        | Trivial task, no complexity, no dependencies.                            |
| **2**     | Easy             | Simple UI or logic, clear scope, low risk.                               |
| **3**     | Moderate         | Small feature, maybe 1–2 steps involved.                                 |
| **5**     | Medium           | Average complexity; some UI + logic; moderate unknowns.                  |
| **8**     | Hard             | Complex feature, multiple parts; cross-team collaboration may be needed. |
| **13**    | Very Hard        | High uncertainty, unclear scope, many dependencies.                      |
| **21**    | Extremely Hard   | Epic-sized task. Needs to be broken down or discussed further.           |
**Substitute Voting Plan:**
Due to the team's current difficulty in finding a suitable time for synchronous estimation, we have decided to conduct anonymous voting using Google Form instead of PlanningPokerOnline.
- Each team member will cast their votes asynchronously using the form.
- Once all responses are collected, we will **review the results** together.
- Any User Stories with significant discrepancies in points will be discussed in our next team meeting to reach consensus.
This approach ensures flexibility while maintaining collaborative estimation integrity.
**Voting Link:** https://forms.gle/mR38nX5t6UrkPC6p6
## UI User Story
### US1 - Welcome Page
**As a** new user,  
**I want to** see a welcome screen with clear benefits,  
**so that** I understand what the platform offers.
### US2 - Account Signup & Login
**As a** visitor,  
**I want to** create an account and log in securely,  
**so that** I can save my preferences and access more features.
### US3 - Map View
**As a** user,  
**I want to** view companies on a map,  
**so that** I can visually explore local businesses and their capabilities.
### US4 - Switch Map & List View
**As a** user,  
**I want to** switch between map view and list view,  
**so that** I can choose the format that best fits my browsing needs.
### US5 - Condition Filter
**As a** user,  
**I want to** filter companies by sector, components, size, capability type, ownership status etc.,  
**so that** I can narrow down the most relevant businesses.
### US6 - Category Icons
**As a** user,  
**I want to** see company locations with category specific icons on the map,  
**so that** I can quickly distinguish different types of companies at a glance.
### US7 - Company Detail Page
**As a** user,  
**I want to** view company profile pages with detailed information,  
**so that** I can understand their offerings, services, and contact information.
### US8 - Responsive & User-Friendly Design
**As a** user,  
**I want to** the UI to be intuitive and responsive,  
**so that** the experience is smooth on both desktop and mobile.
### US9 - Searching
**As a** user,  
**I want to** search by location or keyword,  
**so that** I can quickly find businesses matching specific terms or regions.
## Detailed description
### US1
- **Title:** Welcome Page
- **Priority:** Must
- **Story Point:** ?? wait for voting
- **Due Date:** September 4th 2025
- **Assignee:** Matthew & Alex
- **Status:** Done
- **Acceptance Criteria:**
	- A visually appealing welcome screen appears on first visit
	- Clearly states the platform’s purpose and benefits
	- Works properly on both desktop and mobile
- **Reviewer:** Julian & Oliver
### US2
- **Title:** Account Signup & Login
- **Priority:** Must
- **Story Point:**
- **Due Date:** September 4th 2025
- **Assignee:** Matthew & Alex
- **Status:** Done
- **Acceptance Criteria:**
	- Users can create accounts with required fields(Only Email for now)
- **Reviewer:** Julian & Oliver
### US3
- **Title:** Map View
- **Priority:** Must
- **Story Point:**
- **Due Date:** September 4th 2025
- **Assignee:** Matthew & Alex
- **Status:** Done
- **Acceptance Criteria:**
	- Map displays relevant company pins
	- Interactive zoom and pan functions
	- Pins load dynamically based on viewport
- **Reviewer:** Julian & Oliver
### US4
- **Title:** Switch Map & List View
- **Priority:** Should
- **Story Point:**
- **Due Date:** September 4th 2025
- **Assignee:** Matthew & Alex
- **Status:** Done
- **Acceptance Criteria:**
	- Toggle button is clearly visible and functional
	- Map and List views are synchronized
	- Both views have consistent styling and data
- **Reviewer:** Julian & Oliver
### US5
- **Title:** Condition Filter
- **Priority:** Must
- **Story Point:**
- **Due Date:** September 4th 2025
- **Assignee:** Matthew & Alex
- **Status:** Done
- **Acceptance Criteria:**
	- Filters include sector, components, ownership status, etc.
	- Multi-select filters work correctly
	- Filters update map and list views in real time
- **Reviewer:** Julian & Oliver
### US6
- **Title:** Category Icons
- **Priority:** Could
- **Story Point:** 
- **Due Date:** September 4th 2025
- **Assignee:** Zoy
- **Status:** Done
- **Acceptance Criteria:**
	- Each business category has a meaningful icon
	- Icons display properly at various zoom levels
	- Tooltip or label appears on hover or click
- **Reviewer:** Julian & Oliver
### US7
- **Title:** Company Detail Page
- **Priority:** Must
- **Story Point:** 
- **Due Date:** September 4th 2025
- **Assignee:** Matthew & Alex
- **Status:** Done
- **Acceptance Criteria:**
	- Profile contains company name, services, contact, and tags
	- UI layout is clear and consistent
	- Navigation back to map/list view is easy
- **Reviewer:** Julian & Oliver
### US8
- **Title:** Responsive & User-Friendly Design
- **Priority:** Should
- **Story Point:** 
- **Due Date:** September 4th 2025
- **Assignee:** Matthew & Alex
- **Status:** Done
- **Acceptance Criteria:**
	- Layout adjusts gracefully to mobile/desktop
	- Touch interactions work on mobile
	- No broken elements when resizing browser
- **Reviewer:** Julian & Oliver
### US9
- **Title:** Searching
- **Priority:** Must
- **Story Point:** 
- **Due Date:** September 4th 2025
- **Assignee:** Matthew & Alex
- **Status:** Done
- **Acceptance Criteria:**
	- Search bar accepts location or keyword input
	- Autocomplete suggestions appear
	- Results are reflected in both map and list view
- **Reviewer:** Julian & Oliver




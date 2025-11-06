This document provides an overview of the features implemented during the development of the ICN Navigator, organised by implementation status and development sprint.

**Overall Progress:**
- Total User Stories: 16
- **Fully Supported:**  11
- **Partially Supported:** 5
- **Unsupported:** 2

## User Story Completion

| Feature Area                    | User Story                                                  | Status        | Notes                                                                                                                                                                   |
| ------------------------------- | ----------------------------------------------------------- | ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Platform Access**             | [[User Stories#US01 - Web Application Access]]              | *Partial*     |                                                                                                                                                                         |
|                                 | [[User Stories#US02 - Mobile Application Access]]           | **Supported** |                                                                                                                                                                         |
| **Authentication & Onboarding** | [[User Stories#US03 - Welcome Page(s)]]                     | **Supported** |                                                                                                                                                                         |
|                                 | [[User Stories#US04 - Account Signup & Login]]              | **Supported** |                                                                                                                                                                         |
|                                 | [[User Stories#US05 - Onboarding Questions]]                | **Supported** |                                                                                                                                                                         |
|                                 | [[User Stories#US06 - Subscription Tiers & Feature Access]] | *Partial*     | Not all tiered features are implemented. Some require data missing from the provided data set. Full support is setup with flexible design for handling tiered features. |
| **Map & Navigation**            | [[User Stories#US07 - Map View]]                            | **Supported** |                                                                                                                                                                         |
|                                 | [[User Stories#US08 - Category Icons]]                      | **Supported** |                                                                                                                                                                         |
|                                 | [[User Stories#US09 - Optional List View]]                  | *Partial*     | Handled through the bottom sheet, no specific list view. Although this would be easy to implement give our design approach.                                             |
| **Search & Filtering**          | [[User Stories#US10 - Searching]]                           | **Supported** |                                                                                                                                                                         |
|                                 | [[User Stories#US11 - Map Result Filtering]]                | **Supported** |                                                                                                                                                                         |
| **Company Information**         | [[User Stories#US12 - Company Detail/Profile Page]]         | *Partial*     |                                                                                                                                                                         |
|                                 | [[User Stories#US13 - Company News & Trends]]               | Unsupported   | Decided to be out of scope                                                                                                                                              |
| **User Features**               | [[User Stories#US14 - Export Company Details]]              | **Supported** |                                                                                                                                                                         |
|                                 | [[User Stories#US15 - Save/Bookmark Companies]]             | *Partial*     | User cannot save into specific folders (premium feature) feature)                                                                                                       |
|                                 | [[User Stories#US16 - Chat/Communications Feature]]         | Unsupported   | Premium feature. Was decided to be out of scope. But framework is there.                                                                                                |

---

## Implementation by Sprint

### Sprint 1:  W1 - W6

**Focus:** Initial Prototype & Application Foundations

**Completed (not exhaustive):**
- Finalised project requirements (see [[Breakdown of Reqs]])
- Design process documentation (see [[Design Process]])
- Research and discovery documentation (see [[Research and Discovery]])
- Low-fidelity UI prototypes (see [[Low Fidelity]])
- High-fidelity UI prototype (see [[High Fidelity]])
- Deployment pipeline draft (see [[Deployment]])
- High level architecture (see [[High Level Overview]])

**Features:**
- Simple app setup flows (**frontend only**) ([[User Stories#US03 - Welcome Page(s)]])
	- Login and Sign Up page/s ([[User Stories#US04 - Account Signup & Login]])
	- Verify page
	- Reset password page
	- Onboarding page ([[User Stories#US05 - Onboarding Questions]])
- API integration preparation and state management

**Technical Achievements:**
* **Protected routing** for handling user authenticated vs. unauthenticated user access (framework setup, not implemented with backend in this sprint).
* **State management** for simple persistence of app state across reloads.
* **Online documentation deployment** integrated into CI/CD workflow using GitHub actions.

### Sprint 2: W7 - W9

**Focus:** Core Features & Backend Integration

**Completed:**
- DB Schema finalised (see [[Database Overview]])
- ICN Data processing and cleaning
- UI for tiered features (see [[High Fidelity#Main App (Mobile)]])
- UI mockup for Web (see [[High Fidelity#Main App (Web)]])

**Features:**
* Launched DB instance
- Backend support 
	- Sessions
	- Tiered features
	- Sectors
	- item List
* Main app map view ([[User Stories#US07 - Map View]])
- Organisation page ([[User Stories#US12 - Company Detail/Profile Page]])
- Filters ([[User Stories#US11 - Map Result Filtering]])
	- Item search
	- Filter on capability
	- Filter on saved

**Technical Achievements:**
- **Data cleaning** and **normalisation** in preparation for ingestion into DB
- **CI/CD** workflow setup for testing (backend with bun test) and code linting (across full codebase with prettier)
### Sprint 3: W10 - W14

**Focus:** Feature Completion, Refinement & Testing 

**Features**
- Filters ([[User Stories#US11 - Map Result Filtering]])
	- Filter on distance (handled on backend)
	- Filter on sector
- Company export ([[User Stories#US14 - Export Company Details]])
- Bookmarking ([[User Stories#US15 - Save/Bookmark Companies]])
	- Includes backend support for persistence across devices
- Web support ([[User Stories#US01 - Web Application Access]])
	- Authentication flows
	- Main app

**Technical Achievements:**
- **Export to PDF**
- **Filter design** - API handles filter on distance, all other filters handled locally. Makes filters extensible and acceptably performant. 
- Small **UI/UX improvements** and optimisations


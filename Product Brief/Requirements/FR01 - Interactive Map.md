## Overview

| **Functional Requirement** | Display an interactive, **map-based directory** of companies, including their location.                                                               |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Source**                 | [[high-lvl-reqs.pdf#page=1&selection=124,0,124,27\|high-lvl-reqs, page 1]] and [[intro-slides.pdf#page=5&selection=21,0,28,35\|intro-slides, page 5]] |
## User Stories



### US01 - View companies on map

**As a** business seeker  
**I want to** view nearby companies displayed on an interactive map  
**So that** I can quickly identify potential suppliers/partners in my region

**Acceptance Criteria:**
* A map view is available in the main app navigation
* Company markers are displayed with correct geolocation
### US02 – Explore company details from map

**As a** business seeker  
**I want to** click on a company marker and open its profile page  
**So that** I can learn more about its capabilities and decide if it suits my needs

**Acceptance Criteria:**
*  Tapping/clicking a marker opens a profile preview or links to the full profile page
*  Profile includes location, capabilities, and contact information

#TODO - add more + more details

---
## Notes / Design Considerations

- Map provider is expected to be **Mapbox** (see [[DR07 - Map Framework]])
- Must support both **mobile and desktop** layouts with responsive scaling.
- Consider accessibility (e.g., non-map list view fallback).
- Performance optimisation required if dataset includes thousands of companies.

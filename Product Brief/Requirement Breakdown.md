
**Please Note:**

As of 25/07/25, the client has not yet provided a full requirements document that was initially expected. So, as decided in [[W4 - Stand Up]], we have developed a working set of requirements using our current understanding of the product, and the following resources:

* [[high-lvl-reqs.pdf]] - the high-level overview of the product from initial project pitch
* [[intro-slides.pdf]] - the first presentation the client's gave in Week 2
* [ICN's Website](https://icn.org.au/icn_vic) - ICN Victoria's website

Our agile approach ensures we can adapt and refine these requirements if and when the official documentation becomes available. 

**Also Note:**

This document **focusses on the software product** - the *ICN Navigator App*. However, as an assignment, this project does include other deliverables (this document for instance!). These other "requirements" are included in our GitHub Project but are labeled with the "documentation" tag, and are not omitted from this breakdown.

## Functional Requirements

A **functional** requirement is *what the system must do*, including key observable behaviour, services and features.

| ID   | Requirement                                                                                                    | Source                                                                                                                                                |
| ---- | -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| #FR1 | Display an interactive, **map-based directory** of companies, including their locations and capabilities<br>   | [[high-lvl-reqs.pdf#page=1&selection=124,0,124,27\|high-lvl-reqs, page 1]] and [[intro-slides.pdf#page=5&selection=21,0,28,35\|intro-slides, page 5]] |
| #FR2 | Provide **company profiles** with key capabilities and details                                                 | [[high-lvl-reqs.pdf#page=1&selection=65,65,70,17\|high-lvl-reqs, page 1]]                                                                             |
| #FR3 | Enable **filtering/searching** of companies by sector, capability, or location                                 | [[intro-slides.pdf#page=7&selection=32,0,72,4\|intro-slides, page 7]] and [[high-lvl-reqs.pdf#page=1&selection=62,11,67,38\|high-lvl-reqs, page 1]]   |
| #FR4 | Optional **list view** of companies (sorted by distance from current location)                                 | [[intro-slides.pdf#page=7&selection=26,0,28,17\|intro-slides, page 7]]                                                                                |
| #FR5 | Fetch and display data from simple **REST API database** using ICN data.                                       | [[high-lvl-reqs.pdf#page=2&selection=24,0,36,5\|high-lvl-reqs, page 2]]                                                                               |
| #FR6 | Provide lightweight **authentication**                                                                         | [[high-lvl-reqs.pdf#page=2&selection=54,0,56,29\|high-lvl-reqs, page 2]]                                                                              |
| #FR6 | Support **multi-platform support** with both web browsers and mobile.                                          | [[high-lvl-reqs.pdf#page=1&selection=84,0,120,22\|high-lvl-reqs, page 1]]                                                                             |
| #FR7 | Ability to make an **account** and **sign-in**                                                                 | [[intro-slides.pdf#page=6&selection=26,0,26,28\|intro-slides, page 6]]                                                                                |
| #FR8 | **Membership tiers** (direct payment integration not required) - presumably with access to different features. | [[intro-slides.pdf#page=6&selection=28,0,46,16\|intro-slides, page 6]]                                                                                |
| #FR9 | **Onboarding** when user first signs up.                                                                       | [[intro-slides.pdf#page=6&selection=10,0,12,24\|intro-slides, page 6]]                                                                                |

## Non-Functional Requirements

A **non-functional** requirement is *how the system must perform*, including the quality of the system as a whole.

| ID    | Requirement                                                                                                                                                | Source                                                                    |
| ----- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| #NFR1 | Modern, clean, and responsive UI design                                                                                                                    | [[high-lvl-reqs.pdf#page=2&selection=40,0,46,48\|high-lvl-reqs, page 2]]  |
| #NFR2 | Lightweight and **maintainable** code with modular components                                                                                              | [[high-lvl-reqs.pdf#page=2&selection=78,0,92,70\|high-lvl-reqs, page 2]]  |
| #NFR3 | Secure all communication with **HTTPS**                                                                                                                    | [[high-lvl-reqs.pdf#page=2&selection=60,0,60,64\|high-lvl-reqs, page 2]]  |
| #NFR4 | **Easy deployment** to common platforms ([Vercel](https://vercel.com/), [Netlify](https://www.netlify.com/), etc.) - no complex enterprise infrastructure. | [[high-lvl-reqs.pdf#page=2&selection=64,0,74,55\|high-lvl-reqs, page 2]]  |
| #NFR5 | **Reliable performance** and tested for usability (unit, intergration, UAT)                                                                                | [[high-lvl-reqs.pdf#page=2&selection=163,0,166,1\|high-lvl-reqs, page 2]] |

## Out-of-Scope Requirements

**Out of scope requirements** are things we explicitly won't do for this project.

| ID    | Requirement                                                 | Rationale                                                                                                                  |
| ----- | ----------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| #OSR1 | Building native iOS / Android apps from scrachj             | Covered by cross-platform suppport                                                                                         |
| #OSR2 | Complex enterprise security or SSO integrations             | Out of scope per "simple security measures" (see [[high-lvl-reqs.pdf#page=2&selection=50,0,60,63\|high-lvl-reqs, page 2]]) |
| #OSR3 | Migration of all historical ICN directories into the system | Privacy / copyright concerns means we will be working with anonymised ICN data                                             |


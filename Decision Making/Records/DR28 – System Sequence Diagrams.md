
| **Status**     | #Planned                                    |
| -------------- | ------------------------------------------- |
| **Impact**     | #High                                       |
| **Driver/s**   | Oliver                                      |
| **Approver/s** | Julian, Zoy                                 |
| **Date**       | Sunday, September 29th                      |
| **Links**      | Sprint 7 Meeting Notes, User Story Diagrams |

## Background
Sprint feedback emphasised the importance of adding **system sequence diagrams (SSDs)** to illustrate the interactions for key flows. SSDs clarify how external actors (users) interact with the system through the UI, and how the backend responds to fulfil those requests.

## Relevant Data
- Key flows identified: **Sign-in**, **Data Queries (Map + Filters)**.  
- SSDs provide a middle ground between use case diagrams (high-level) and sequence diagrams (technical).  
- Including SSDs improves documentation completeness and supports client/stakeholder understanding.  

## Options Considered
**Option 1: Skip SSDs and rely only on detailed sequence diagrams**  
- Pro: Less duplication.  
- Con: Harder for non-technical stakeholders to follow.  

**Option 2: Create SSDs for only one key flow (e.g., sign-in)**  
- Pro: Minimal effort.  
- Con: Incomplete coverage of core system behaviour.  

**Option 3: Create SSDs for multiple key flows (Chosen)**  
- Pro: Provides clarity for sign-in and data queries, the two most important flows.  
- Con: Requires some extra diagramming effort.  

## Action Items
- Create SSD for **User Sign-in** (actor → system interactions).  
- Create SSD for **Map View + Filtering** (actor → system queries + responses).  
- Add diagrams to documentation and link to related user stories.  

## Outcome
The team decided to **create system sequence diagrams for sign-in and data query flows**.  
This ensures clear representation of user-system interactions at the right level of abstraction for reviews.

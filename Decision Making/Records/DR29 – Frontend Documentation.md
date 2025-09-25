
| **Status**     | #Planned                                                             |
| -------------- | -------------------------------------------------------------------- |
| **Impact**     | #Medium                                                              |
| **Driver/s**   | Matthew                                                              |
| **Approver/s** | Oliver, Julian                                                       |
| **Date**       | Monday, September 30th                                               |
| **Links**      | Sprint 8 Plan, User Story Documentation                              |

## Background
As the frontend grows in complexity, the team recognised the need for **detailed frontend documentation**. This ensures components are easier to maintain, tested consistently, and understandable for new contributors.

## Relevant Data
- The frontend is built with React Native and TypeScript.  
- Components include onboarding screens, map view, filters, and company profile pages.  
- Current documentation is limited to user stories and code comments.  

## Options Considered
**Option 1: No dedicated frontend documentation**  
- Pro: Saves time.  
- Con: Hard for others to understand or test components.  

**Option 2: Document only high-level structure**  
- Pro: Faster to write.  
- Con: Lacks details on individual components and their test cases.  

**Option 3: Break down components and link test cases (Chosen)**  
- Pro: Comprehensive; improves maintainability and testing clarity.  
- Con: Requires extra writing effort and ongoing updates.  

## Action Items
- Break down frontend into components (e.g., MapView, FilterPanel, CompanyCard).  
- Document props, behaviours, and dependencies of each component.  
- Link each component to corresponding test cases.  
- Store documentation alongside code for easy updates.  

## Outcome
The team decided to **create detailed frontend documentation**, breaking down components and linking to their test cases.  
This improves maintainability, testing, and onboarding of future contributors.


| **Status**     | #Planned                                                             |
| -------------- | -------------------------------------------------------------------- |
| **Impact**     | #Medium                                                              |
| **Driver/s**   | Zoy                                                                  |
| **Approver/s** | Matthew, Alex                                                        |
| **Date**       | Monday, September 30th                                               |
| **Links**      | Sprint 8 Plan, API Design Notes                                      |

## Background
The backend is being developed using **Bun with TypeScript** and connects to a PostgreSQL database. To support development, testing, and client handover, the team identified the need for **clear backend documentation**, particularly around API endpoints.

## Relevant Data
- Current API development covers user authentication, company data queries, and filtering.  
- There is limited written documentation beyond code comments.  
- Feedback suggested documenting status codes, methods, and schemas for clarity.  

## Options Considered
**Option 1: Rely on code and comments only**  
- Pro: Saves effort.  
- Con: Makes it hard for frontend developers and client reviewers to understand API behaviour.  

**Option 2: Document only key endpoints**  
- Pro: Provides a minimal reference.  
- Con: Incomplete picture; risks confusion later.  

**Option 3: Document all endpoints with methods, status codes, and schemas (Chosen)**  
- Pro: Comprehensive; supports testing and client review.  
- Con: Requires consistent updates alongside development.  

## Action Items
- Create an API reference with endpoint paths, HTTP methods, expected status codes, and request/response schemas.  
- Link documentation to relevant user stories.  
- Store docs in repo (`/docs` or `backend/docs`) for easy access.  

## Outcome
The team decided to **document all backend API endpoints**, including status codes and schemas.  
This ensures clarity for frontend integration, testing, and client understanding.

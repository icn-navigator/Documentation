
| **Status**     | #Complete                                                            |
| -------------- | -------------------------------------------------------------------- |
| **Impact**     | #Medium                                                              |
| **Driver/s**   | Matthew                                                              |
| **Approver/s** | Julian, Zoy                                                          |
| **Date**       | Tuesday, October 1st                                                 |
| **Links**      | Sprint 7 Meeting Notes, GitHub Repo Setup                            |

## Background
As the project involves both a frontend (React/TypeScript) and backend (Bun/TypeScript with PostgreSQL), the team needed a clear **repository structure** to avoid confusion and make local development easier.

## Relevant Data
- Initially, frontend and backend code were mixed together in the root directory.  
- Developers had difficulty locating files and setting up environments.  
- Standard practice is to separate components into dedicated folders for modularity.  

## Options Considered
**Option 1: Keep all code in a single root folder**  
- Pro: Simplest structure.  
- Con: Confusing as the project grows; hard to set up environments.  

**Option 2: Split into two repos (frontend + backend)**  
- Pro: Complete separation, clear responsibilities.  
- Con: Overhead in maintaining two repos; less convenient for integration.  

**Option 3: Monorepo with `frontend/` and `backend/` folders (Chosen)**  
- Pro: Clear separation within one repo; easier integration.  
- Con: Slightly more complex repo setup.  

## Action Items
- Create `frontend/` and `backend/` directories at repo root.  
- Move existing React code into `frontend/` and Bun backend code into `backend/`.  
- Update documentation (`README.md`) with setup steps for both.  

## Outcome
The team decided to use a **monorepo with separated `frontend/` and `backend/` folders**.  
This keeps development organised while allowing integration within a single repository.

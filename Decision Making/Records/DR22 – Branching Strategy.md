
| **Status**     | #Complete                                                            |
| -------------- | -------------------------------------------------------------------- |
| **Impact**     | #Medium                                                              |
| **Driver/s**   | Zoy                                                                  |
| **Approver/s** | Oliver, Alex                                                         |
| **Date**       | Monday, September 30th                                               |
| **Links**      | Sprint 7 Meeting Notes, GitHub Repo Setup                            |

## Background
To manage parallel development work and ensure stable integration, the team needed to decide on a **branching strategy** for Git. A clear workflow reduces merge conflicts, improves code quality, and provides structure for sprint-based development.

## Relevant Data
- The project involves multiple developers working on frontend and backend simultaneously.  
- Without a clear branching model, commits risk overwriting each other.  
- Industry standards suggest GitFlow or lightweight adaptations for small teams.  

## Options Considered
**Option 1: Work directly on `main` branch**  
- Pro: Simplest.  
- Con: High risk of breaking production code; no stability guarantees.  

**Option 2: GitFlow (full model)**  
- Pro: Clear separation of develop, feature, release, hotfix branches.  
- Con: Heavy for a student MVP project.  

**Option 3: Lightweight branching with `develop` + feature branches (Chosen)**  
- Pro: Balanced approach; stable `develop` branch for integration, features isolated.  
- Con: Requires some discipline to follow process.  

## Action Items
- Use `main` branch for production-ready code.  
- Use `develop` as the integration branch for all features.  
- Each new feature/fix is developed in its own branch, merged into `develop` via PR.  
- Delete merged feature branches to keep repo clean.  

## Outcome
The team decided to adopt a **lightweight branching strategy**:  
- `main` = stable, production-ready code.  
- `develop` = integration branch.  
- Feature branches created and merged via PR.  
This ensures stable integration while keeping workflow simple for the project’s scale.

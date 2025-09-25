
| **Status**     | #Planned                                               |
| -------------- | ------------------------------------------------------ |
| **Impact**     | #Medium                                                |
| **Driver/s**   | Oliver                                                 |
| **Approver/s** | Julian, Zoy                                            |
| **Date**       | Tuesday, October 1st                                   |
| **Links**      | Sprint 8 Feedback, GitHub Repo Contribution Guidelines |

## Background
The team already has **contribution guidelines** for commits and branching, but lacks a consistent **code formatting and linting standard**. Feedback recommended adopting shared configuration files (Prettier, ESLint) to improve code quality and ensure consistency across developers.

## Relevant Data
- Current repo shows variations in indentation, spacing, and naming.  
- Inconsistent style slows reviews and increases merge conflicts.  
- Prettier and ESLint are widely used in TypeScript/React projects.  

## Options Considered
**Option 1: Rely on developer discipline without tooling**  
- Pro: No setup required.  
- Con: Inconsistent results; high risk of style drift.  

**Option 2: Use Prettier only**  
- Pro: Standardises formatting.  
- Con: Does not enforce best practices in TypeScript code.  

**Option 3: Use Prettier + ESLint with shared config (Chosen)**  
- Pro: Covers both formatting and linting rules; ensures consistent, high-quality code.  
- Con: Requires initial setup and integration into CI/CD.  

## Action Items
- Add Prettier and ESLint config files to the repo.  
- Document usage in README.  
- Integrate lint/format checks into CI/CD pipeline.  
- Enforce style before merging pull requests.  

## Outcome
The team decided to **adopt Prettier and ESLint with a shared config**, integrated into CI/CD.  
This ensures a consistent coding style, reduces conflicts, and improves maintainability.

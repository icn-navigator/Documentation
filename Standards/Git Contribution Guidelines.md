
# Overview
Unfortunately Github doesn't provide a method of implementing branch protection for free on a private repository, so this document is intended to outline the standard procedure for contributing code to the project.

The intention of these rules is just to:
- Make sure all code contributed meets the desired standard
- Ensure no contribution causes unnecessary conflicts with other peoples' work
- Make sure the main branch maintains stability as the "release branch"

## Repository Structure
- `main` - Our "release branch". This must be kept stable and is what is deployed to a production server.
- `develop` - The primary branch we'll merge changes to (See *rule 2* for conventions on contribution).
- `hotfix` - Used when there is an urgent issue with the `main` branch that needs to be fixed immediately.
- All other branches are *feature branches*


# Rules

## Rule 1 - Don't commit directly to main

Before implementing something in code, think about what "unit of work" is being implemented. Typically this will be a subtask derived from a user story (or even a user story itself, depending on how large it is), for example: "user authentication" or "map filtering". Once you have thought about the exact feature you intend to implement, create a *feature branch* for it in your local repository (e.g. login-page).
- Feel free to commit as much as needed to this new feature branch! (Using the format listed in *Rule 4*)
- This should keep main stable and conflict free


## Rule 2 - Use pull requests

When you've finished implementing your feature, and your feature branch is in a stable state, don't just directly `git merge` into the main branch on your local repository - go to the branch on GitHub and select "open pull request".

After opening the pull request, message me and I'll review the changes - after which I'll either approve the merge back into main or write comments and close the PR (so you know what to fix before re-opening it).

## Rule 3 - Stay up to date!

When working on a feature branch, make sure to regularly pull changes to your local copy of the main and either merge or rebase them into your feature branch. This should help catch any conflicts early while they're insignificant and easy to address.
- Let me know if you need help with doing this!

## Rule 4 - Commit Naming Scheme

When making a commit to any branch, use the following format for the commit message to make the history easier to follow:
```
<type>: <subject>
```

The **type** should be one of:
- `fix` (for bug fixes)
- `feat` (for work on new features)
- `chore` (routine updates, e.g. formatting, documenting, minor rewrites)

The **subject** should be a short message in the *imperative* mood.
- For example: `Add new login page styling`, or `Fix server panic when filtering map`







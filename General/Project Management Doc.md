
We are using [GitHub Projects](https://github.com/orgs/icn-navigator/projects/3/views/3) for our project management (see [[Tools Used]] for access details). This page provides a guide on it's setup and best practices for adding new tasks.

>[!info] Resources 
> * Our initial GitHub Projects setup was inspired by the video series [Scrum with Github Projects]([https://youtube.com/playlist?list=PLGxFXI4dC2siB2ENZ6OhagfwSId5FcWmY&si=LyZADQK-y4O0dWGC](https://youtube.com/playlist?list=PLGxFXI4dC2siB2ENZ6OhagfwSId5FcWmY&si=LyZADQK-y4O0dWGC "https://youtube.com/playlist?list=PLGxFXI4dC2siB2ENZ6OhagfwSId5FcWmY&si=LyZADQK-y4O0dWGC")) 
> * For understanding Scrum and the Agile methodology[ Atlassian's no-nonsense guide to Agile](https://www.atlassian.com/agile) was a valuable resource 
> * See also the lecture/workshop slides and [[L2-agile.pdf]] and [[W3-sprint-planning.pdf]] 

---
## Hierarchy of Work Items

We use three levels of work items to organise and track progress. Each level helps break down the project into smaller more manageable parts:

* **Epic** - A large body of work that represents a major feature, them, or deliverable. May be completed over multiple sprints.
* **Requirement** - A specific piece of functionality or capability needed to deliver part of an Epic
* **Task** - The smallest unit of work. Tasks are concrete, actionable steps that team members can pick up during a sprint. 

Together, they form the following hierarchy:

![[work-item-heirarchy.svg|600]]

### On GitHub Projects

On **GitHub Projects** the `tag` field specifies whether a item is an Epic, Requirement or Task.

There are three filtered `views`  for each type. Each view is configured with specific fields with varying levels of details tailored to the type of work item it summarises.

![[github-projects-view-highlight-1.png]]

It's important to note that GitHub Projects is built on top of GitHub Issues. Because of this, every item must be linked to an issue and a repository. So, to achieve the hierarchy of work items illustrated above, **sub-issues** are used. For example, a **Requirement** item will be a parent issue for for several **Task** items and itself a **sub-issue** of an **Epic**. 
### How we use User Stories

> [!info]- What are User Stories?
> A user story is an informal, general explanation of a software feature written from the perspective of the end user. Its purpose is to articulate how a software feature will provide value to the customer. User stories give the team important context and associate tasks with the value those tasks bring. 
> 
> As a (type of user), I want to (do something specific) so that (I achieve some outcome).
> 
> They should also include **acceptance criteria**. Read more here: [Atlassian - User Stories](https://www.atlassian.com/agile/project-management/user-stories)
> 

Some Agile resources (such as [Atlassian’s guide](https://www.atlassian.com/agile/project-management/epics-stories-themes?utm_source=chatgpt.com)) use the term **User Story** in place of what we call a **Requirement**.

We’ve chosen to use **Requirement** instead because this project is broader than just software development. As a university project, our deliverables include not only code but also documentation, progress checklists, and presentations. These don’t always map cleanly to the idea of a “user story,” but they can still be captured as requirements that contribute to the overall project outcome.

So, **where do we use user stories?** In general, user stories help describe **Task**-level work items that are software related. On GitHub projects, the `description` section of an Task item should include the relevant user story.

Multiple user stories make up a requirement. To see our breakdown of user stories into requirements check out our [[Breakdown of Reqs]].

## Other Pages

### Backlog

![[github-projects-view-highlight-2.png]]

The **Backlog** is the central collection of all work items - Epics, Requirements, and Tasks. New items are added here whenever they arise. During **Sprint Planning** (like [[W4 - Sprint Planning]]), the team selects which items to bring into the upcoming sprint, and at that point their [[#Priority]] and [[#Estimate]] values are reviewed and confirmed.

### Current Sprint

![[github-projects-view-highlight-3.png]]

The **Current Sprint** view uses a Kanban-style board to track progress. It is filtered to show only **Tasks**, since these are the actionable units of work. The board is further filtered to include only the Tasks assigned to the active sprint, as agreed during Sprint Planning.

## Fields

Some fields in GitHub Projects need clarification on how we use them.

### Status

Every Task has a status that reflects its current stage in the workflow:

* **To Do** – The item has not been started.
* **In Progress** – Work on the item is actively underway.
* **Under Review** – The item is awaiting review (e.g., code review, documentation check).
* **Done** – The item has been completed.

Statuses are updated throughout the sprint to provide a clear picture of progress and to keep the Kanban board accurate.
### Priority

Every Task is assigned a priority. We use a simple three-level system:

* **P0** - Highest priority
* **P1** - Medium priority
* **P2** - Lowest priority

Priorities are reviewed and confirmed during **sprint planning** to ensure the team is focused on the most important work.

### Estimate

Instead of using “story points,” we estimate effort using the **Fibonacci sequence**, where the number corresponds to the expected duration of a Task in **hours** (e.g., 1, 2, 3, 5, 8).

This approach makes estimates easier to interpret and has the added benefit that GitHub Projects can automatically sum the estimates of all Tasks within a Requirement, giving an overall time estimate for that Requirement.

Estimates are decided as a team during **sprint planning**. 

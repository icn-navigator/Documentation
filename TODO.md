The [[progress-checklist.pdf]] is due on the **Sunday, 7th of September**.

>[!info]- Goal of this document
> 
> As highlighted in Harry’s presentation at the start of the W6 tutorial (see: [[W5-sprint-end.pdf]]), there is a significant amount of work ahead.
> 
> This document breaks down that workload into manageable tasks, making it easier to **see what’s required**, **discuss priorities**, and **coordinate as a team**.
> 
> **General Advice**
> * Prioritise progress checklist tasks
> 	* Focus on activities that contribute directly to the **progress checklist**
> 	* While other tasks may seem interesting, they risk consiming tasks without moving us closer to the deadline
> 	* Even the "boring" jobs are important if they check boxes
> * Don't get stuck
> 	* If you're blocked, ask for help/clarification
> 	* Switch to a different task
> 	* Routinely report your progress for feedback
> * Unsure what do do
> 	* Ask what to do
> 	* Check if anyone needs help
> 	* Review/edit others work
> 	
> **Useful resources**
> * [[progress-checklist-marking.pdf]] - Note that marking criteria differ between projects, so this key won’t exactly match Harry’s expectations (see discussion in the sections below).
> * [[W5-sprint-end.pdf]] - The workshop slides that discuss the project-checklist
> * [[table-of-contents-exemplar.pdf]] - If you’re unsure where something belongs in the documentation, review this exemplar (or ask on Discord).

**NOTE:** For most tasks, make sure it’s added to [GitHub Projects](https://github.com/orgs/icn-navigator/projects/3?utm_source=chatgpt.com) before you begin, and update it once you’ve completed it.
## Adherence to Agile Ceremonies
[[W5-sprint-end.pdf#page=7&selection=0,0,28,19|W5-sprint-end, page 7]]

**Doing OK.**  Making sure this is up-to-scratch is everyones responsibility, although overall management is left to @Julian as the Scrum Master.

- [ ] Backlog (a work in progress) 
	- [ ] Estimates / priority assignment for current sprint
- [ ] Ceremonies
	- [ ] Sprint Planning (in-progress: [[W3-sprint-planning.pdf]])
	- [ ] Retrospective[^6] 
	- [ ] Review
- [ ] (Optional) Edit the [[W5 - Stand Up]] notes to better reflect your activities.

[^6]: Technically, this sprint does end soon, so we will need to do a **retrospective** - hopefully this week is productive so we have things to talk about!
### Role Assignments
 [[W5-sprint-end.pdf#page=9&selection=0,0,12,42|W5-sprint-end, page 9]]

**Effectively done.** Roles were assigned a while ago, just make sure your communication and tasks reflect your role (this is something that's graded)

- [w] [[Roles]] is already assigned and responsibilities described.
- [ ] A good **Discord** communication history with behaviour reflective of roles
- [ ] **GitHub projects** kanban board/tasks regularly used

### Group Decision Making
[[W5-sprint-end.pdf#page=10&selection=0,0,30,13|W5-sprint-end, page 10]]

**Doing OK.** Our [[Decision Log]] is a good concept, but needs more items.

- [ ] Fill in incomplete [[Decision Log]] decision records
- [ ] Add more Decision Records
	- [ ] Look at [[high-lvl-system-arch.pdf]] - justify choices[^1]
		- [ ] Amazon EC2
		- [ ] Postgres DB
		- [w] Map box
- [ ] Justify UI decisions (some ideas below...)
	- [ ] Inspiration artefacts
	- [ ] Simple page describing our overall methodology[^7]
	- [ ] A comments / notes in Figma
- [ ] Add [[Change Log]] for any decisions that have changed

[^1]: For areas with many interrelated decisions (e.g. backend architecture), a tailored note may be clearer than separate decision records. A single document can explain how the choices collectively support scalability, maintainability, and future extensibility, with alternatives mentioned more briefly. Link this instead of a decision record in the decision log.

### Meetings
[[W5-sprint-end.pdf#page=11&selection=0,0,23,11|W5-sprint-end, page 11]]

**Doing OK.** If time, we could make the meeting notes more detailed but not a priority.

- [w] Meetings notes
	- [ ] Link more decision records (makes meeting outcomes clear)
	- [ ] Add more action items (can be backfilled)
- [ ] Have at least one more meeting (or async meeting)

### Communication
[[W5-sprint-end.pdf#page=12&selection=2,0,32,17|W5-sprint-end, page 12]]

**Probably, "Below Expectations".**  Especially our **Discord** chat history. However, if we do the other sections well, this should improve organically.

**Internal communication:** Please actively engage!
* Post what you're working on
* Ask questions
* Give others feedback
* Send at least one message a day

**External communication:** Client is making this tricky, but there are still things to do.
- [ ] Set up documentation for client interactions
	- [ ] Section noting client communication struggles 
	- [ ] General questions for client
	- [ ] Link things awaiting client review / feedback
- [ ] Prepare plan for presenting to client next tutorial (W6 Thursday)

## Artefacts

### Requirements
[[W5-sprint-end.pdf#page=14&selection=0,0,28,38|W5-sprint-end, page 14]]

**First stage done.**  Just needs to be broken down further into **User Stories**.

- [ ] [[Requirement Breakdown]][^2]
	- [w] Functional
	- [w] Non-Functional
	- [w] Out-of-scope
	- [ ] Review by all team members
	- [ ] (Maybe) change [[W3-sprint-planning.pdf]] to better match this.
- [ ] **Large task:** Break down into **user stories*
	- [ ] Start with those specific to the current / next sprint (e.g. login / onboarding)
	- [ ] Remaining user stories
- [ ] Add to **GitHub projects**[^3]
	- [ ] Add user stories to epics/requirements/tasks (maybe in `description` section)
	- [ ] Priority assignment
	- [ ] Story point estimation
- [ ] Find a way to document (major) **requirement changes** (shouldn't rely on commit history for this)

**NOTE:** Writing requirements is an **incremental** process - we'll likely identify more throughout the project and have to add more user stories progressively.

[^2]: Where possible and appropriate, please refer to these requirements in written discussion using the tags. For example, "To support #FR3 we chose this approach because..."

[^3]: Requirements might not map nicely to "Requirement" issue types - they may correspond to Epics, Requirements, or Tasks - or neither, in which case they should just be referenced.

### Frontend Design
[[W5-sprint-end.pdf#page=15&selection=0,0,30,36|W5-sprint-end, page 15]]

Going well. However, frontend design is a large task and a major deliverable. 

>[!proposal]-
>The key point here is that for this sprint Harry is **not** expecting a high-fidelity UI prototype of the **whole app** - this is not realistic both due to the scale of the app and the lack of client interaction. 
>
>So, for this sprint/progress checklist, we should focus on the "initial-setup" phase of the app: login, authentication, onboarding (everything before the user enters the main app). We should get the UI design to a polished state up to this point, and not much further (for now) since we are under time-constraints.
>
>That means completing the following artefacts for this section:
> * Low-fidelity prototype (wireframe)
> * High-fidelity prototype (Figma)
>   
>  It would be more valuable to design a smaller section *fully*, rather than the whole app *partially*. With a fully complete design, frontend coding can confidently start. In general, an alternating design-code, design-code, etc. will be our main workflow.

- [ ] Make a (team) decision on whether we will use a UI Component Library[^4]
- [ ] Low-fidelity prototype of setup 
	- [w] Mobile - (needs review: [[wireframe-app-setup.pdf]]) 
	- [ ] Web - (not a priority, focus on mobile first)
- [ ] High-fidelity prototype of app setup (Figma)
	- [ ] Mobile
	- [ ] Web
- [ ] UI-Documentation (might just be one long page, psst... ChatGPT can help waffle)
	- [ ] Description of methodology (e.g. are we "simple, but effective UI")
	- [ ] Inspiration (e.g. Imprint, HappyCow, etc.)
	- [ ] Theme/colour palette (cite the [[brand-guidelines.pdf]])
	- [ ] Justification / thought process behind decisions 
- [ ] Low-fidelity prototype of other parts of the app - **NOT a priority for this week**.
	- [ ] Map
	- [ ] Map filtering
 
[^4]: This is a very **important** decision, and should be made as a team (meeting/discord). If a UI Library is decided on, the high fidelity prototype should be built/adapted using it's assets.

### Architectural Design 
[[W5-sprint-end.pdf#page=16&selection=0,0,24,13|W5-sprint-end, page 16]]

**LOTS of work to do here.** The [[L4-design.pdf]] lecture outlined the 4+1 architecture approach, which Harry also recommended. The exemplar followed this structure, with a page for each "view" containing the relevant artefacts and justifications (see: [[table-of-contents-exemplar.pdf]]). The list below is not exhaustive - there may be other diagrams worth including - but aim for at least one artefact per view.

- [ ] Architecture goals and constraints (see: [[L4-design.pdf#page=13&selection=0,0,0,32|L4-design, page 13]])
- [ ] Logical view
	- [ ] Domain / Class Diagram (maybe not necessary for us?)
	- [ ] Database diagram (**definitely**, at least a draft)
- [ ] Development View (dynamic aspects of the system)
	- [ ] Maybe a web-flow routing for user sign-in/setup
	- [ ] System sequence diagrams (maybe not necessary)
- [ ] Process View
	- [ ] Package diagram
	- [w] System diagram (done: [[high-lvl-system-arch.pdf]])
- [ ] Physical View
	- [ ] Deployment pipeline

**Software:** preferred software for diagrams is [Lucid Chart](https://www.lucidchart.com/pages) and export to pdf. For simple diagrams, consider [Mermaid](https://mermaid.js.org/#/) which is renders natively in Obsidian.

>[!warning]- Just completing a diagram is not sufficient
>Diagrams should have written notes linked with them that justify the decisions within them - perhaps link with a **decision record** / **requirement**. Justifications should include references to **scalability**, **extendability**, **maintainability**.

### Codebase
[[W5-sprint-end.pdf#page=17&selection=0,0,55,10|W5-sprint-end, page 17]]

**Setup required.** As Harry noted, code is not the focus of this sprint and an MVP is not expected. The key client deliverable is the UI prototypes. Our priority should be to set up and organise the codebase so it’s ready for the next sprint. At most, this might include basic frontend/backend scaffolding, but this is **not a priority** compared to the other tasks listed.

- [ ] README 
	- [ ] Project title / description
	- [ ] Installation / setup instructions (if code scaffold is setup)
	- [ ] Build & deployment instructions
	- [ ] Include links to relevant docs (e.g. contribution guidelines)
- [ ] Dev guidelines
	- [w] Contribution guidelines (done: [[Git Contribution Guidelines]]) 
	- [ ] Code style enforcement (Prettier / ESLinter setup / guidelines - documentation needed too)
- [ ] Start coding (**NOT a priority**)
	- [ ] Backend setup
	- [ ] Frontend setup
### Testing & Deployment
[[W5-sprint-end.pdf#page=18&selection=0,0,3,1|W5-sprint-end, page 18]]

**Some work required.** Expectations for this sprint are low, but there are still tasks to complete. The main focus should be on **researching**, **planning**, and **documenting** these choices. If time permits, setting up and implementing basic scaffolds of the workflow can also be worthwhile, though this is secondary.

- [ ] Testing (research/plan)
- [ ] Deployment (research/plan)
	- [ ] Maybe a deployment pipeline diagram (see [[#Architectural Design]])
- [ ] Acceptance criteria for User Stories
## Other

As mentioned in the intro, the above tasks are the priority - they are what's going to be graded. Nevertheless, there are a few miscellaneous tasks:

- [ ] Quartz deployment of this documentation[^5]
	- [ ] Index page 
	- [ ] Custom theme (low priority)
	- [ ] Auto-deployment on push (low priority)
- [ ] General tidy-up of Obsidian docs before submission

[^5]: In the [[progress-checklist.pdf]] we submit, we will include links to this, so it's is **important.**

[^7]: If the task is low-value, repetitive, and mainly about ticking a box, feel free to use ChatGPT to speed it up (**but not for coding**).

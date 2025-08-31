This document discusses the approach taken to frontend design for UI/UX.
## Process

### Our design-code iteration model

We are follow an *iterative*, back-and-forth design process rather than a long "design first, then build" sequence. Each UI feature moves through a tight loop: research, low-fidelity prototype, high-fidelity prototype, refine and implement.

For example, for **Sprint 1** (see: [[W4 - Sprint Planning]]) we are focussing solely on the "Setup" phase of the app. This includes:
* Sign-in 
* Sign-up
* Authentication
* Onboarding

This is opposed to designing the UI and user-flows of the **full app** in one go before beginning on it's implementation. 
### Why we chose this approach

* **Uncertain requirements** - some requirements and preferences are still evolving, this approach is more agile and flexible to changes for less cost.
* **Client feedback** - related to the above, due to the infrequency and low availability of client feedback, this approach:
	* Reduces the risk of going to far ahead on a design the client is disagreeable to
	* Makes feedback more concrete and focussed on smaller increments
* **Value sooner** - this approach means we are able reach implementation (code) sooner. Moreover, lessons learnt coding (e.g. hard to implement elements) might informer future design decisions - improving efficiency.

### Typical loop

* **Discover and research** - Clarify the user story, constraints, and success criteria. Research for inspiration (unless design ethos is already well established)
* **(Optional) User Flow diagram** - For complex interactions a [user flow diagram](https://www.figma.com/resource-library/user-flow/)
* **Low-fidelity prototype/s** - A simplified sketch / design (basic layout etc.) aka wireframe
* **High-fidelity prototype/s** - A detailed, ready-to-implement design (possibly intractable) likely in [Figma](https://www.figma.com/). 

### Other guidelines

* **User a design system** - shared components, and patterns in Figma (and code) for consistency and efficiency.
* **Decision log** - We record client preferences and rationale to avoid back-and-forth on settled choices. 

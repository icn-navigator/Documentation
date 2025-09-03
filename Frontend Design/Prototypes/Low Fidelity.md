
**This document presents the low-fidelity UI prototypes (wireframes).**  

In addition to those introduced in [[Research and Discovery]], it also provides discussion and justification for key design decisions.

**NOTE:** As discussed in our [[Design Process]], we are following an **iterative design approach.** To reflect this, the document is divided into sections corresponding to different parts of the application (e.g., app setup, account, main-interface/maps). This structure makes it easier to review and update individual areas as the design evolves.  
## App Setup

This prototype "Setup" phase of the app. This includes:
* Sign-in 
* Sign-up
* Authentication
* Onboarding
* *(Basically everything before the user enters the main app)*

![[wireframe-app-setup.pdf]]

**Annotated wireframe diagram of app-setup** (see: [[wireframe-app-setup.pdf]])

While the wireframe annotations capture most details, the following considerations guided our design: 

* **Clear entry point** - users have the flexibility to either create a new account or sign in with an existing one (potentially with alternative sign-in options, although we acknowledge that SSO auth may be costly development-wise)
* **Progressive authentication** - email, verification and password creation are all broken down into steps to reduce cognitive load on the user. 
* **Onboarding** - Provides more context on what the app may include a short questionnaire to personalise the experience, so the app is relevant from first use.
* **Premium trial** - shown at the end of onboarding, this introduces the value proposition early without blocking free use. (we're also considering making this a pop-up whenever the user tries to access premium features)

Together, these choices aim to make account creation smooth, guide users into the right category, and set expectations before entering the main app.

## Main App Pages

This section provides a high-level overview of the **main app interface**, focusing on its overall layout and the core pages that make it up.

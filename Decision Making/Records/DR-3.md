
| **Status**   | #Complete                                                          |
| ------------ | ------------------------------------------------------------------ |
| **Impact**   | #High                                                              |
| **Driver**   | @Everyone                                                          |
| **Approver** | @Everyone                                                          |
| **Date**     | 2025-08-18                                                         |
| **Links**    | Links to relevant research, pages, meetings, and related decisions |

## Background

We need to decide on a frontend framework.

## Relevant Data

> The platform should work on web browsers and mobile devices (iOS and Android) without building separate apps from scratch. A modern JavaScript framework such as Vue.js (possibly combined with tools like Ionic or Capacitor) or React (with React Native) is recommended for cross-platform compatibility.

[[icn-requirements-doc.pdf#page=1&selection=89,1,120,23|icn-requirements-doc, page 1]]
## Options Considered

### React Native

[React Native](https://reactnative.dev/) is an open-source UI software framework developed for building native mobile applications using the React JavaScript framework.

**Positives:**
* A few of us (Julian, Oliver and Matthew) already have experience with JavaScript and React. If you understand React, it should be easier to pick up React Native.
* Cross-platform development from a single codebase
* Quick fixes (OTA Updates)
* Hot Reloading (also see [Expo](https://expo.dev/))

**Negatives:**
* Potential performance issues (although there have been [improvements](https://reactnative.dev/architecture/landing-page))
* Debugging can be challenging

## Action items

* [ ] Team members should make sure they feel comfortable with Javascript / Typescript and begin to learn React Native

--- 
## Outcome

We have decided we're going to use **React Native** for our frontend framework.

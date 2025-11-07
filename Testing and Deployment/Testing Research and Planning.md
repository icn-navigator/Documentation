
> [!info] 
>  See [[High Level Overview]] for an overview of the architecture and technologies we are using. 

## Goals

Our testing strategy will focus on achieving the following outcomes:
1) **Frontend** behaves consistently and smoothly across iOS/Android/Web runtimes
2) **Backend** services (REST API) are correct and performant
3) **Database** is reliable and queries return accurate results

General approach:
 * Will prioritise automated testing where it is possible and productive to do so
 * Support with manual acceptance testing for end-to-end validation
## Frontend Testing

Front end testing validates how an application’s user interface behaves and appears to end users. It ensures that all visual elements and interactive components function correctly across platforms.

> [!warning]  
> We anticipate the frontend to be primarily act as a **stateless representation of backend data**, with most business logic handled by the backend. Given this, and considering project time constraints, we do not anticipate implementing comprehensive automated frontend tests for all components. Instead, a significant portion of frontend testing will rely on **manual acceptance testing** to validate core user flows. Nevertheless, we have still researched suitable frontend testing approaches should additional automation become feasible later in the project.  

### Testing Methodologies

Core:
* **Unit Testing**: Validates individual components work in isolation
* **Integration Testing:** Ensure multiple individual components work together as expected (including integration with backend services)
* **End-to-End (E2E) Testing:** Simulates real user flows from start to finish
* **Acceptance /Manual Testing**
	* Running the app in **Expo Go** on iOS, Android, and web sandbox environments
	* Does the UI display backend data correctly? Is navigation intuitive?

Other:
* **Visual Regression Testing**: Detects unintended UI changes across builds.
* **Cross-Browser Testing:** Confirms consistent behaviour across different browsers.
* **Accessibility Testing:** Verifies compliance with accessibility standards like WCAG.
* **Responsiveness Testing:** Checks layout adaptability across screen sizes and devices.

### Testing Frameworks:

React automation testing tools *can* help verify your apps quality by performing various tests, ranging from static analysis to end-to-end tests.

* [Jest](https://jestjs.io/) - Popular choice with built-in assertions, snapshot testing, and zero-config setup. (React actually ships with it - see [React Testing Overview](https://reactnative.dev/docs/testing-overview#writing-tests))
* [Jasmine](https://jasmine.github.io/) - Behaviour-driven framework supporting clean syntax and easy test structuring.

### Useful Resources:

* https://www.browserstack.com/guide/front-end-testing
* https://reactnative.dev/docs/testing-overview
* https://reactnavigation.org/docs/testing/

## Backend Testing

Backend testing is a type of software testing that focuses on testing the non-user-facing components of a software application, such as the database, APIs, and server-side code. Backend testing is important to ensure that the application can handle the expected load and provide a reliable and secure user experience.

Since the backend contains most of the project's business logic, testing here should be very structured. 

### Bun Testing

Since we're using Bun runtime (see: [[DR05 - Backend Language]]), Bun's built in test runner ([docs](https://bun.com/docs/cli/test)) is the obvious choice.

- **Unit Tests**: Validate individual services, utilities, and API endpoints.  
- **Integration Tests**: Test the REST API end-to-end with mocked or test databases.  
- **Workflow Integration**:  Tests can run as part of CI/CD (via GitHub Actions) on pull requests to catch regressions early.  

### Useful Resources:

* https://www.geeksforgeeks.org/software-testing/what-is-backend-testing/
* https://bun.com/docs/cli/test



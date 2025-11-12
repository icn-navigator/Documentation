## Security

This project is an enterprise information navigation platform involving user registration, data access, and continuous interaction with the backend database. Therefore, our system design focused on authentication mechanisms, secure communication, data storage, and deployment security. 

### Project and Code Security

Like many applications, our source code is stored on GitHub. We opted to structure our project as a set of private repositories owned by a single private organisation (see more on [Github Organisations](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/about-organizations)). This project structure allows us to precisely control read and write access to the source code. Despite the code having invite-only read access, there are still important security considerations and best practices relating to sensitive data. Our application utilises several APIs (and connects to a database instance), so we have ensured credentials for these processes are loaded at run-time from an environment file (which is prevented from being tracked by git version control). The contents of the environment file were privately distributed using secure channels.

### Authentication and Session Security

For user authentication and session management, we ensured login security through one-time code verification and secure session tokens. In the user authentication step, each session token is based on UUIDv4 (which is resistant to brute-force guessing) and has a defined expiration time. Once the token expires, it is deleted from the database automatically and users must log in again to the application. This helps prevent replay attacks and stops stolen tokens from remaining valid indefinitely.  We also avoid storing sensitive information in the frontend’s localStorage. This can prevent the data leaking risk from the frontend side. Instead, we use secure browser cookies, such as httpOnly and Secure attributes. We also use encrypted mobile storage solutions such as SecureStore and Keychain for security considerations. 

All passwords are stored as hashed values in the backend using [Argon2](https://argon2-cffi.readthedocs.io/en/stable/argon2.html) with random salting for security, ensuring that even leaked passwords are not directly useful to potential attackers (even with [rainbow-table attacks](https://www.strongdm.com/what-is/rainbow-table-attack)). 

Also see the [[API Documentation]] for more context on of how these authentication and session flows are implemented. 

### Data Protection and API Security

Regarding API and database security, all data transmissions between the client and the server use HTTPS (TLS) encryption to prevent man-in-the-middle (MITM) attacks and unauthorised access to plaintext data in-flight. We also use use [Zod](https://zod.dev/) schemas to strictly validate all front-end and back-end inputs. This ensures that all request parameters follow the correct format and helps prevent injection attacks at the source. Our database queries use Bun’s parameterised query mechanism from their standard library Postgres driver, effectively eliminating the risk of SQL injection.

### Deployment and Operational Security

In terms of deployment and data handling, all environment variables, API keys, and database URLs are securely managed using `.env` files and protected by `.gitignore` to prevent accidental exposure in public repositories. 

## Ethics

Although not many direct ethical issues arose during this project, there are still topics worth discussing. In this section, we focus on three main ethical issues: data fairness, accessibility and inclusivity, and the responsible use of generative AI. 

### Data Representation and Fairness

One of the key ethical concerns that arose in our project was ensuring fairness in how organisations are represented. This was an issue also raised directly by our client from a [Q&A response]([[common-q&a.pdf]]). When asked whether the platform should display company ratings or trending pages, the client mentioned that such features would make the app resemble platforms like _Hi-Pages_ and would conflict with the goal of providing fair, neutral information.

Aligned with this ethos, we deliberately avoided ranking or popularity-based features and instead focussed our design around tag-based filtering and categorisation. This approach aims to reduce bias where possible while not reducing usability. In both the design of our UI and underlying algorithms (e.g. search/filtering) we aimed to give equal visibility to small and medium enterprises, emerging sectors, and regional industries, promoting fair competition and transparent access to information.

It is worth mentioning, on the search side of things, a possible improvement we considered was randomising the top search result. While we didn't have time to implement this feature, it could be another way to improve equitable representation of organisations. 

### Accessibility and Inclusivity

We also prioritised accessibility and inclusivity in our design process. Guided by the principles of Universal Design, we aimed to make the platform approachable for users with varying levels of digital literacy and technical experience. 

Since none of our team members have a design background, this was a significant challenge. However, we made a conscious effort to follow recognised UI/UX best practices and drew inspiration from established, user-friendly platforms such as Happy Cow (See our design [[Research and Discovery]] documentation for more details on our design inspiration sources and process). Elements like buttons, typography (within the [brand guidelines]([[brand-guidelines.pdf]]), of course), and map interactions were simplified to maximise clarity and ease of navigation. 

We also discussed additional steps for improving accessibility that were outside the project’s immediate scope. For instance, implementing features such as high-contrast colour modes and multilingual support could make the platform more inclusive for users with visual impairments or from culturally and linguistically diverse backgrounds. These would be valuable directions for future development.

### Responsible use of Generative AI

As a team, we discussed the ethical implications of using generative AI tools during development. While we used AI assistance for general coding support and some planning, we were mindful of its limitations and potential risks. Our general policy focussed on responsible use - AI could assist us, but not replace our own understanding or decision making. 

Relating to the previous section, we were particularly cautious about using AI in security-sensitive areas and followed a clear policy to at minimum review and understand any generated content before adoption - ideally seeking feedback from another team member inline with our [[Git Contribution Guidelines]]. In practice, this meant using AI as a supplementary resource rather than a primary development tool. Indeed, as several team members were learning new technologies such as React Native for the first time, many found it valuable to research and implement solutions independently to build genuine understanding and technical skills.

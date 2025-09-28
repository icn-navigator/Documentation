Break down of primary goals and constraints using the what/why/how format suggested in the lectures (see [[L4-design.pdf]])

Note, some of this has some overlap with the requirements discussed in our [[Breakdown of Reqs]] section.

### Authentication

**What?**
System should verify a user is who they say they are.

**Why?**
To protect sensitive data from unauthorised access.

**How?**
- Require users to log-in to correct account before providing sensitive information
- Use custom Bun api #TODO link decision record

### Confidentiality

**What?**
System should ensure sensitive information is only accessible to those who are authenticated

**Why?**
To protect sensitive data from being utilised maliciously and maintain trust from users

**How?**
- Encrypt data in transit (HTTPS)
- Use secure methods of storing information in database

### Data Persistence

**What?**
System should ensure data is saved and can be accessed later. This includes (but is not limited to):

- Users saved data (e.g. favorited organisations)
- User login status

**Why?**
To prevent data from getting lost. Most database data (like organisation records) should inherently be persistent. But for the case of user data (like persisting login state) - this is essential for user experience (user doesn't have to sign in every open the app).

**How?**
- Database (postgres SQL - see [[DR08 - Database]])
- In the case of preserving login status, this can be achieved using persistent storage (e.g. `expo-secure-store` perhaps with something like [Zustand](https://zustand.docs.pmnd.rs/) for state management)

### Usability

**What?**
System should be intutive and accessible to users. This should be the case for both web and mobile interfaces (and there should be a cohesive design philosohpy across both

**Why?**
Complex interfaces reduce adoption and user satisfiaction. For the cohesive design aspect - it should be intutive to come from the mobile app and use the web app and vis versa.

**How?**

- Follow platform UI guidelines (e.g. respect safe areas)
- Look at good sources of inspirtation of established apps
- Implement responsive design
- Consider accessibility standards (although, lower priority than main product features)

### Performance

**What?**
The app (both UI and backend services that are in our control) should respond quickly and handle demanding situations (e.g. many pins rendering simultaneously) and concurrent users efficiently.

**Why?**
Poor performance leads to user frustration.

**How?**
- For frontend: following good react strategies (e.g. minimising rerenders, good state management)
- In general: caching strategies, optimising database queries, using efficient data structures (will be especially important for how we decide to implement our search functionality)

### Scalability

**What?**
Our system should be able to handle a growing number of users (and potentially organisations!) without degrading performance.

**Why?**
- Potential future grown for ICN/ICN Navigator
- Prevent system failures under load

**How?**
- Good database design and optimised queries (maybe making sure indexing is optimised for anticipated searches)

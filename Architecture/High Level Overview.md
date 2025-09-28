
## Architecture Diagram

![[new-high-level-arch.pdf]]

## Summary and Justification

### Frontend

We're using *React Native* with the *Expo Framework* (in *Typescript*) as they offer a well-tested and flexible cross platform UI development experience.

See [[DR03 - Frontend Framework]] and [[DR04 - Frontend Language]] for more information.

### Backend

We're using the *Bun* runtime and framework (with *Typescript*) for our backend as they are fast, modern, easy to pickup and develop secure applications with, and widely supported.

See [[DR05 - Backend Language]] for more information.

### Database

Our main database is *PostgreSQL* as it's an extremely popular and modern choice for building reliable and performant applications with data storage needs.

See [[DR08 - Database]] for more information.

### Hosting Provider

We are using *Render*'s hosting platform, as it offers a simple and friendly abstraction over AWS without removing too much flexibility regarding server architecture - providing the best of both worlds in simplicity, price, scalability, and flexibility.

See [[DR06 - Deployment]] for more information.

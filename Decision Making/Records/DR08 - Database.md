
| **Status**     | #Complete              |
| -------------- | ---------------------- |
| **Impact**     | #High                  |
| **Driver/s**   | @Julian @Oliver        |
| **Approver/s** |                        |
| **Date**       | Wednesday, August 27th |
| **Links**      | [[W2 - Meeting 1]]     |

## Background

ICN Navigator requires an internal database (separate to the *ICN Directory Data*) for several aspects of the platform:
- Data protection through user authentication
- Monetization through subscription-based access (ties into previous point)
- Storing user preferences

## Options Considered

### MySQL
**Positives:**
- Most members of the team have worked with MySQL before
- Simple hosting and deployment options available
**Negatives:**
- Becoming a legacy system, used less in modern applications (compared to PostgreSQL)
	- Potentially less up-to-date resources
- Doesn't have the same first-class support in Bun ([[DR05 - Backend Language]]) as PostgreSQL

### PostgreSQL
**Positives:**
- Modern, widely supported option
- Very performant
- First-class support in Bun 
	- See here: <https://bun.com/docs/api/sql>
**Negatives:**
- Team isn't as familiar with specifics of PostgreSQL syntax
	- *However*, many of the important differences are only apparent with more advanced use cases, which are likely to not occur in the account management of ICN Navigator

## Action items

--- 
## Outcome

Overall, we decided PostgreSQL was the best option for our application.


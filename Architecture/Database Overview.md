
## DB Schema Diagram

This is the core DB schema for the app, based on the relevant requirements for sprint 1

![[ICN Navigator DB Schema.pdf]]

## Schema Features

### Account Management
The schema design allows users to register their account with a username and password, securely hashing the password in the `users` table.
- We also have an integer value denoting the user's account subscription tier, which provides us a simple method of determining what features they are able to access based on their current plan.
- We do not have any explicit subscription management information in the database schema as we have not been provided with exact instruction about which payment processor to use and how it should be integrated. However, our approach of using an abstracted subscription tier should permit future flexibility for payment processor choice.

Linked to each account is 1 or more onboarding question responses, which are a flexible way to reflect the personalisation questions asked when first onboarding a user.

We also store user `sessions`, which are used for keeping the user logged in to the app after they close it. The general session verification flow is as follows:
1. User enters correct credentials for an account
2. Session token is generated with a random UUID (which is logged in the DB along with an expiry date)
3. UUID is sent to the user device for non-volatile storage
4. When the user wants to access a feature that requires authentication (e.g. the app main page, or an authenticated-only API), they must send the session token UUID as the `Bearer` token in an `Authorization` header, where it can be verified on the backend

If a user logs out, the corresponding session token for that device is deleted.

### Saved Organisations

A user can save organisations of interest to more conveniently retrieve them later.

### ICN Directory Storage

The provided example ICN directory data has been broken down into a set of normalised tables that represent the relationships between the entities.
- These are tied to users through the saved organisation link, but are otherwise queried separately.

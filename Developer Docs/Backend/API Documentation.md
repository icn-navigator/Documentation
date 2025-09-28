
## Account Management

### POST `/api/account`

**Summary:** Creates an account based on the information provided in the request body.
**Headers:** N/A
**Body:** `NewAccountDetails`
- `name`: string
- `email`: string
- `password`: string
- `subscriptionTier`: 0,1,2,3

#### Returned Values:
- **Status Code:** 201 (CREATED)
	- **Value:** 
		- `accountId`: number
		- `sessionId`: string (UUID)
	- Occurs when account creation succeeds.

- **Status Code:** 422 (UNPROCESSABLE ENTITY)
	- **Value:** "Invalid account details provided"
	- Occurs when the body format is incorrect

- **Status Code:** 409 (CONFLICT)
	- **Value:** "Email already registered"

- **Status Code:** 500 (INTERNAL SERVER ERROR)
	- **Value:** "Failed to create account"
	- Occurs when the account record insertion process failed.

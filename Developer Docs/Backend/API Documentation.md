
## Account Management

---

### `POST /api/account`

Creates a new user account.

#### Request Body

```json
{
  "name": "string",
  "email": "string",
  "password": "string",
  "subscriptionTier": "number"
}
```
- `name`: The user's full name.
- `email`: The user's email address. Must be unique.
- `password`: The user's password (min 8 characters).
- `subscriptionTier`: `1` (Free), `2` (Standard), `3` (Pro).

#### Responses

- **`201 CREATED`**
  - **Description:** Account creation was successful.
  - **Body:**
    ```json
    {
      "accountId": "number",
      "sessionId": "string"
    }
    ```

- **`409 CONFLICT`**
  - **Description:** "Email already registered"

- **`422 UNPROCESSABLE ENTITY`**
  - **Description:** "Invalid account details provided"

- **`500 INTERNAL SERVER ERROR`**
  - **Description:** "Failed to create account"

## Session Management

---

### `POST /api/login`

Authenticates a user and returns a new session token.

#### Request Body

```json
{
  "email": "string",
  "password": "string"
}
```
- `email`: The user's email address.
- `password`: The user's password.

#### Responses

- **`200 OK`**
  - **Description:** Authentication successful.
  - **Body:**
    ```json
    {
      "token": "string"
    }
    ```

- **`400 BAD REQUEST`**
  - **Description:** "Bad Request"

- **`401 UNAUTHORIZED`**
  - **Description:** "Unauthorized"

- **`500 INTERNAL SERVER ERROR`**
  - **Description:** "Internal Server Error"

---

### `POST /api/logout`

Logs a user out by invalidating their session token.

#### Request Headers
- `Authorization`: "Bearer <SESSION_TOKEN>"

#### Responses

- **`200 OK`**
  - **Description:** Logout successful.

- **`401 UNAUTHORIZED`**
  - **Description:** "Unauthorized"

---

### `GET /api/validate-session`

Validates a session token.

#### Request Headers
- `Authorization`: "Bearer <SESSION_TOKEN>"

#### Responses

- **`200 OK`**
  - **Description:** "OK" (Token is valid)

- **`401 UNAUTHORIZED`**
  - **Description:** "Unauthorized"
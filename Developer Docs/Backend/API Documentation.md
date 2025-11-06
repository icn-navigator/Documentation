**Base URL:** `http://localhost:8000`

---

## Authentication & Account Management

### Start Signup

**Endpoint:** `POST /api/auth/signup/start`

Initiates account creation by storing pending account details and sending a verification code via email.

#### Request Body

```json
{
  "name": "string",
  "email": "string",
  "password": "string",
  "subscriptionTier": 0 | 1 | 2 | 3
}
```

- `name`: User's full name (required)
- `email`: Valid email address (required, must be unique)
- `password`: User's password (required)
- `subscriptionTier`: `0` (Invalid), `1` (Free), `2` (Plus), `3` (Premium)

#### Responses

- **`200 OK`**
  - **Description:** Signup initiated successfully, verification code sent to email
  - **Body:** `null`

- **`409 CONFLICT`**
  - **Description:** "Email already registered"

- **`422 UNPROCESSABLE ENTITY`**
  - **Description:** "Invalid account details provided"

---

### Verify Challenge Code

**Endpoint:** `POST /api/auth/verify-challenge`

Verifies a challenge code (from signup or login) and creates a session.

#### Request Body

```json
{
  "email": "string",
  "code": "string"
}
```

- `email`: Email address used for signup/login (required)
- `code`: 6-digit verification code received via email (required)

#### Responses

- **`200 OK`**
  - **Description:** Challenge verified, account created (if signup) and session established
  - **Body:**
    ```json
    {
      "userId": "number",
      "token": "string (UUID v4)",
      "hasCompletedOnboarding": "boolean",
      "subscriptionTier": 0 | 1 | 2 | 3
    }
    ```

- **`400 BAD REQUEST`**
  - **Description:** "Pending signup not found" or "Account not found"

- **`401 UNAUTHORIZED`**
  - **Description:** "Invalid or expired code"

- **`422 UNPROCESSABLE ENTITY`**
  - **Description:** "Invalid code details provided"

- **`500 INTERNAL SERVER ERROR`**
  - **Description:** Account or session creation failed

---

### Complete Onboarding

**Endpoint:** `POST /api/auth/onboarding/complete`

Completes the user onboarding process by storing user preferences and answers.

#### Request Headers
- `Authorization: Bearer <SESSION_TOKEN>`

#### Request Body

```json
{
  "answers": {
    // Onboarding answer data structure
  }
}
```

#### Responses

- **`200 OK`**
  - **Description:** Onboarding completed successfully
  - **Body:** `"Onboarding completed"`

- **`401 UNAUTHORIZED`**
  - **Description:** "Unauthorized" (Token missing, invalid, or expired)

- **`422 UNPROCESSABLE ENTITY`**
  - **Description:** "Invalid answers provided"

---

### Start Login

**Endpoint:** `POST /api/auth/login/start`

Validates credentials and sends a verification code to the user's email.

#### Request Body

```json
{
  "email": "string",
  "password": "string"
}
```

- `email`: User's email address (required)
- `password`: User's password (required)

#### Responses

- **`200 OK`**
  - **Description:** Credentials valid, verification code sent
  - **Body:** `null`

- **`400 BAD REQUEST`**
  - **Description:** "Bad Request" (invalid request format)

- **`401 UNAUTHORIZED`**
  - **Description:** "Unauthorized" (email not found or incorrect password)

- **`500 INTERNAL SERVER ERROR`**
  - **Description:** Challenge creation or email sending failed

**Note:** After receiving a 200 response, use `/api/auth/verify-challenge` to complete login.

---

### Validate Session

**Endpoint:** `GET /api/auth/validate-session`

Checks if a session token is valid and not expired.

#### Request Headers
- `Authorization: Bearer <SESSION_TOKEN>`

#### Responses

- **`200 OK`**
  - **Description:** "OK" (Token is valid)

- **`401 UNAUTHORIZED`**
  - **Description:** "Unauthorized" (Token missing, invalid, or expired)

---

### Start Password Reset

**Endpoint:** `POST /api/auth/password-reset/start`

Initiates password reset by sending a verification code via email.

#### Request Body

```json
{
  "email": "string"
}
```

- `email`: User's email address (required)

#### Responses

- **`200 OK`**
  - **Description:** Request processed (verification code sent if email exists)
  - **Body:** `null`

- **`400 BAD REQUEST`**
  - **Description:** "Bad Request" (invalid request format)

**Security Note:** Always returns 200 even if email doesn't exist to prevent email enumeration.

---

### Complete Password Reset

**Endpoint:** `POST /api/auth/password-reset/complete`

Completes password reset by verifying code and updating password.

#### Request Body

```json
{
  "email": "string",
  "code": "string",
  "newPassword": "string"
}
```

- `email`: User's email address (required)
- `code`: 6-digit verification code (required)
- `newPassword`: New password (required)

#### Responses

- **`200 OK`**
  - **Description:** Password updated successfully
  - **Body:** `null`

- **`400 BAD REQUEST`**
  - **Description:** "Bad Request" (invalid request format)

- **`401 UNAUTHORIZED`**
  - **Description:** "Unauthorized" or "Invalid or expired code"

---

### Logout

**Endpoint:** `POST /api/auth/logout` or `GET /api/auth/logout`

Terminates the user session.

#### Request Headers
- `Authorization: Bearer <SESSION_TOKEN>`

#### Responses

- **`200 OK`**
  - **Description:** Logout successful
  - **Body:** Empty string

- **`401 UNAUTHORIZED`**
  - **Description:** "Unauthorized" (Token missing or invalid)

---

## ICN Data

### Get Items

**Endpoint:** `GET /api/items`

Retrieves all available items for filtering/searching.

#### Request Headers
- `Authorization: Bearer <SESSION_TOKEN>`

#### Responses

- **`200 OK`**
  - **Description:** Items retrieved successfully
  - **Body:**
    ```json
    [
      {
        "id": "string",
        "detailedId": "string",
        "name": "string",
        "detailedName": "string"
      }
    ]
    ```

- **`401 UNAUTHORIZED`**
  - **Description:** "Unauthorized"

- **`500 INTERNAL SERVER ERROR`**
  - **Description:** "Failed to fetch items"

---

### Get Sectors

**Endpoint:** `GET /api/sectors`

Retrieves all available sectors for filtering.

#### Request Headers
- `Authorization: Bearer <SESSION_TOKEN>`

#### Responses

- **`200 OK`**
  - **Description:** Sectors retrieved successfully
  - **Body:**
    ```json
    [
      {
        "mappingId": "string",
        "name": "string"
      }
    ]
    ```

- **`401 UNAUTHORIZED`**
  - **Description:** "Unauthorized"

- **`500 INTERNAL SERVER ERROR`**
  - **Description:** "Failed to fetch sectors"

---

### Get Organisations

**Endpoint:** `GET /api/organisations`

Retrieves organisations within a specified geographic radius along with their capabilities.

#### Request Headers
- `Authorization: Bearer <SESSION_TOKEN>`

#### Query Parameters
- `latitude` (required): User's latitude coordinate (float)
- `longitude` (required): User's longitude coordinate (float)
- `radiusKm` (optional, default=20): Search radius in kilometers (positive number)

#### Responses

- **`200 OK`**
  - **Description:** Organisations retrieved successfully
  - **Body:**
    ```json
    [
      {
        "id": "string",
        "name": "string",
        "billingStreet": "string",
        "billingCity": "string",
        "billingProvince": "string",
        "billingPostalCode": "string",
        "latitude": "number",
        "longitude": "number",
        "itemCapabilities": [
          {
            "capability": "string",
            "capabilityType": "string",
            "validationDate": "ISO 8601 date",
            "item": {
              "id": "string",
              "detailedId": "string",
              "name": "string",
              "detailedName": "string"
            },
            "sector": {
              "mappingId": "string",
              "name": "string"
            }
          }
        ]
      }
    ]
    ```

- **`400 BAD REQUEST`**
  - **Description:** Missing required parameters or invalid values
  - **Body:**
    ```json
    {
      "error": "latitude and longitude are required"
    }
    ```
    or
    ```json
    {
      "error": "radiusKm must be a positive number"
    }
    ```

- **`401 UNAUTHORIZED`**
  - **Description:** "Unauthorized"

- **`500 INTERNAL SERVER ERROR`**
  - **Body:**
    ```json
    {
      "error": "Internal server error"
    }
    ```

**Capability Types:**
- Assembler
- Retailer
- Manufacturer
- Manufacturer (Parts)
- Project Management
- Service Provider
- Wholesaler
- Item Supplier
- Designer
- Supplier
- Parts Supplier
- Raw Materials Supplier

---

### Export Organisation

**Endpoint:** `GET /api/organisation/:id/export`

Generates and downloads a PDF summary of an organisation's details and capabilities.

#### Request Headers
- `Authorization: Bearer <SESSION_TOKEN>`

#### URL Parameters
- `id` (required): Organisation ID (string)

#### Responses

- **`200 OK`**
  - **Description:** PDF generated successfully
  - **Content-Type:** `application/pdf`
  - **Content-Disposition:** `attachment; filename="organisation-{id}.pdf"`
  - **Body:** Binary PDF data

- **`400 BAD REQUEST`**
  - **Description:** Organisation ID is required
  - **Body:**
    ```json
    {
      "error": "Organisation ID is required"
    }
    ```

- **`401 UNAUTHORIZED`**
  - **Description:** "Unauthorized" (Token missing, invalid, or expired)

- **`404 NOT FOUND`**
  - **Description:** Organisation not found
  - **Body:**
    ```json
    {
      "error": "Organisation not found"
    }
    ```

- **`500 INTERNAL SERVER ERROR`**
  - **Description:** PDF generation or server error
  - **Body:**
    ```json
    {
      "error": "Internal server error"
    }
    ```

**PDF Contents:**
- Organisation name and ID
- Full billing address
- List of all capabilities with:
  - Capability name and type
  - Associated item details
  - Associated sector
  - Validation date
- Generation timestamp

---

## Subscription Management

### Upgrade Subscription

**Endpoint:** `POST /api/subscription/upgrade`

Upgrades the user's subscription tier.

#### Request Headers
- `Authorization: Bearer <SESSION_TOKEN>`

#### Request Body

```json
{
  "newTier": 0 | 1 | 2 | 3
}
```

- `newTier`: New subscription tier (0=Invalid, 1=Free, 2=Plus, 3=Premium)

#### Responses

- **`200 OK`**
  - **Description:** Subscription upgraded successfully
  - **Body:**
    ```json
    {
      "success": true,
      "newTier": 0 | 1 | 2 | 3
    }
    ```

- **`401 UNAUTHORIZED`**
  - **Description:** "Unauthorized"

- **`422 UNPROCESSABLE ENTITY`**
  - **Description:** Invalid request body

**Note:** This is currently a proof-of-concept without payment validation.

---

## Authentication Details

**Session Tokens:**
- Format: UUID v4
- Expiration: 30 days from creation
- Header format: `Authorization: Bearer <token>`
- Automatic cleanup of expired tokens runs hourly

**Password Security:**
- Passwords are hashed using Bun's built-in password hashing
- Challenge codes are 6-digit strings sent via email
- Challenge codes are single-use (deleted after verification)

---

## Error Response Format

Most endpoints return plain text error messages. The `/api/organisations` endpoint returns JSON error objects:

```json
{
  "error": "Error message here"
}
```

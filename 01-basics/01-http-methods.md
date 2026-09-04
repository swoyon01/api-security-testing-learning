# HTTP Methods

> HTTP (HyperText Transfer Protocol) methods define the action to be performed on a resource. In API security testing, understanding these methods is essential because each method has different security implications.

---

## 📋 Overview of HTTP Methods

| Method | Purpose | Safe | Idempotent | Security Risk |
|--------|---------|:----:|:----------:|---------------|
| **GET** | Retrieve data | ✅ | ✅ | Data exposure in URL |
| **POST** | Create data | ❌ | ❌ | CSRF, injection |
| **PUT** | Full update | ❌ | ✅ | Unauthorized modification |
| **PATCH** | Partial update | ❌ | ❌ | Mass assignment |
| **DELETE** | Remove data | ❌ | ✅ | Unauthorized deletion |
| **OPTIONS** | Check allowed methods | ✅ | ✅ | Information disclosure |
| **HEAD** | Get headers only | ✅ | ✅ | Fingerprinting |

---

## 1️⃣ GET Method

### What it does
Requests data from a specified resource.

### Example Request
```http
GET /api/users/1 HTTP/1.1
Host: example.com
Authorization: Bearer eyJhbGci...
```

### Example Response
```json
{
  "id": 1,
  "name": "John Doe",
  "email": "john@example.com"
}
```

### Security Notes
- ⚠️ **Never send sensitive data in GET requests** — data appears in:
  - Browser history
  - Server logs
  - Referrer headers
- URLs have length limits (~2048 characters)
- GET requests can be cached by browsers/proxies

### Testing Tip
```
GET /api/users/1 → 200 OK (valid user)
GET /api/users/2 → 200 OK? (BOLA/IDOR test)
GET /api/users/9999 → 404 Not Found?
GET /api/admin/users → 403 Forbidden? (BFLA test)
```

---

## 2️⃣ POST Method

### What it does
Submits data to be processed to a specified resource (usually creates a new resource).

### Example Request
```http
POST /api/users HTTP/1.1
Host: example.com
Content-Type: application/json
Authorization: Bearer eyJhbGci...

{
  "name": "Jane Doe",
  "email": "jane@example.com",
  "role": "user"
}
```

### Example Response
```json
{
  "id": 101,
  "name": "Jane Doe",
  "email": "jane@example.com",
  "role": "user",
  "created_at": "2024-01-15T10:30:00Z"
}
```

### Security Notes
- ✅ **Use for sensitive data** — data is in the body, not URL
- ⚠️ **Mass Assignment Risk** — sending extra fields like `"role": "admin"`
- ⚠️ **CSRF Risk** — if no proper tokens/headers
- ⚠️ **Injection Risk** — SQLi, NoSQLi in body parameters

### Testing Tip
```json
// Normal request
{
  "name": "Jane",
  "email": "jane@test.com"
}

// Mass Assignment test
{
  "name": "Jane",
  "email": "jane@test.com",
  "role": "admin",
  "is_admin": true,
  "id": 1
}
```

---

## 3️⃣ PUT Method

### What it does
Updates a resource by replacing the entire resource with the request payload.

### Example Request
```http
PUT /api/users/1 HTTP/1.1
Host: example.com
Content-Type: application/json
Authorization: Bearer eyJhbGci...

{
  "id": 1,
  "name": "John Updated",
  "email": "john.updated@example.com",
  "role": "user"
}
```

### Key Difference: PUT vs PATCH
| PUT | PATCH |
|-----|-------|
| Replaces **entire** resource | Updates **only specified** fields |
| Must send all fields | Can send just one field |
| Idempotent (same result every time) | Idempotent |

### Security Notes
- ⚠️ **Missing fields may be set to null/default** — can cause data loss
- ⚠️ **ID in URL vs ID in body mismatch** — can lead to IDOR
- ⚠️ **No authorization check** — user A can update user B's data

### Testing Tip
```http
PUT /api/users/1  (as User 2)
→ Should return 403 Forbidden
→ If 200 OK = BOLA vulnerability!
```

---

## 4️⃣ PATCH Method

### What it does
Applies partial modifications to a resource.

### Example Request
```http
PATCH /api/users/1 HTTP/1.1
Host: example.com
Content-Type: application/json
Authorization: Bearer eyJhbGci...

{
  "email": "new.email@example.com"
}
```

### Security Notes
- ⚠️ **Mass Assignment is most dangerous here** — developers often forget to whitelist fields
- ⚠️ **JSON Patch format** (`{ "op": "replace", "path": "/role", "value": "admin" }`) can bypass validation

### Testing Tip
```json
// Try changing read-only fields
{
  "id": 999,
  "role": "admin",
  "password": "hacked",
  "created_at": "2010-01-01"
}
```

---

## 5️⃣ DELETE Method

### What it does
Deletes a specified resource.

### Example Request
```http
DELETE /api/users/1 HTTP/1.1
Host: example.com
Authorization: Bearer eyJhbGci...
```

### Example Response
```http
HTTP/1.1 204 No Content
```

### Security Notes
- ⚠️ **No confirmation required** — one request = permanent deletion
- ⚠️ **Missing authorization** — anyone can delete anything
- ⚠️ **Cascade deletion** — deleting user may delete all their data

### Testing Tip
```http
DELETE /api/users/1  (as User 2)
→ Should return 403
→ If 204 = Critical vulnerability!

DELETE /api/admin/users/1
→ Should return 403 for normal user
→ If 204 = BFLA vulnerability!
```

---

## 6️⃣ OPTIONS Method

### What it does
Returns the HTTP methods that the server supports for a specified URL.

### Example Request
```http
OPTIONS /api/users HTTP/1.1
Host: example.com
```

### Example Response
```http
HTTP/1.1 204 No Content
Allow: GET, POST, HEAD, OPTIONS
Access-Control-Allow-Methods: GET, POST, PUT, DELETE
```

### Security Notes
- ℹ️ **Information Disclosure** — reveals which methods are allowed
- ℹ️ **CORS Preflight** — browsers send OPTIONS before actual request
- ⚠️ **Misconfigured CORS** — `Access-Control-Allow-Origin: *` with credentials

### Testing Tip
```http
OPTIONS /api/admin/users
→ If DELETE is in Allow list = check authorization!
```

---

## 🎯 Method-Based Access Control Testing

Sometimes APIs check authorization for GET but forget for other methods:

```http
GET /api/users/1 → 200 OK (you can read)
PUT /api/users/1 → 200 OK? (can you modify?)
DELETE /api/users/1 → 204? (can you delete?)
PATCH /api/users/1 → 200 OK? (can you partially update?)
```

**If GET requires auth but POST/PUT/PATCH/DELETE doesn't = CRITICAL BUG**

---

## 📝 My Practice Log

### Day 1 — GET Practice

<img width="2560" height="1368" alt="image" src="https://github.com/user-attachments/assets/808a33ed-10ff-45ab-9361-d046bfa1922d" />

**Request:**
```
GET https://jsonplaceholder.typicode.com/posts/1
```

**Response:**
```json
{
  "userId": 1,
  "id": 1,
  "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
  "body": "quia et suscipit\nsuscipit recusandae..."
}
```

- **Target:** https://jsonplaceholder.typicode.com
- **GET /posts/1** → Status: 200, Response time: 650 ms

**Key Observations:**
- GET retrieves existing data
- Response is in JSON format
- No body is sent in the request
- Data appears in the URL (not for sensitive info)

---

### Day 2 — POST Practice

<img width="1280" height="684" alt="image" src="https://github.com/user-attachments/assets/da9294b9-b58d-4950-8216-0a6190cfd4e1" />

**Request:**
```http
POST https://jsonplaceholder.typicode.com/posts
Content-Type: application/json

{
  "userId": 1,
  "title": "Learning Postman",
  "body": "Understanding HTTP METHODS and API testing with Postman"
}
```

**Response:**
```json
{
  "userId": 1,
  "title": "Learning Postman",
  "body": "Understanding HTTP METHODS and API testing with Postman",
  "id": 101
}
```

**Status Code:** `201 Created`  
**Response Time:** `655 ms`  
**Size:** `1.33 KB`

**Key Observations:**
- POST creates a new resource
- Data is sent in the request body (JSON format)
- Server assigns a new `id` (101) to the created resource
- Status code `201` confirms successful creation
- Body data is NOT visible in the URL (safe for sensitive data)

---


### Day 3 — PUT Practice

<img width="1280" height="684" alt="Screenshot 2026-09-03 050322" src="https://github.com/user-attachments/assets/4fc0845d-76ec-443c-8027-9b20ed7d01f3" />


**Request:**
```http
PUT https://jsonplaceholder.typicode.com/posts/10
Content-Type: application/json

{
  "userId": 1,
  "title": "Postman Basics",
  "body": "Learning HTTP methods: GET, POST, PUT, DELETE"
}
```

**Response:**
```json
{
  "userId": 1,
  "title": "Postman Basics",
  "body": "Learning HTTP methods: GET, POST, PUT, DELETE",
  "id": 10
}
```

**Status Code:** `200 OK`  
**Response Time:** `1.10 s`  
**Size:** `1.2 KB`

**Key Observations:**
- PUT replaces the **entire** resource
- All fields must be sent in the body
- The `id` remains the same (10)
- Response returns the fully updated object

**Security Notes:**
- ⚠️ **IDOR Risk:** If User A can PUT to `/posts/11` (User B's post), that's unauthorized modification
- ⚠️ **Missing fields:** Some APIs reset missing fields to null — always verify what happens to fields you don't send
- ⚠️ **Auth bypass:** If PUT doesn't check ownership, anyone can overwrite data

---

### Day 4 — PATCH Practice

<img width="1280" height="684" alt="Screenshot 2026-09-03 051517" src="https://github.com/user-attachments/assets/aa5f7a78-6e77-40bb-bfb3-e504c1958ce3" />

**Request:**
```http
PATCH https://jsonplaceholder.typicode.com/posts/10
Content-Type: application/json

{
  "title": "Postman Basics & API testing"
}
```

**Response:**
```json
{
  "userId": 1,
  "id": 10,
  "title": "Postman Basics & API testing",
  "body": "quo et expedita modi cum officia vel magni\ndoloribus qui repudiandae\nvero nisi sit\nquos veniam quod sed accusamus veritatis error"
}
```

**Status Code:** `200 OK`  
**Response Time:** `1.10 s`  
**Size:** `1.27 KB`

**Key Observations:**
- PATCH updates **only** the `title` field I sent
- The `body` field remained unchanged from before
- `userId` and `id` stayed the same
- Much safer than PUT for small updates

**Security Notes:**
- ⚠️ **Mass Assignment Risk:** Developers often forget to whitelist allowed fields in PATCH
- ⚠️ Try sending extra fields like `"role": "admin"` or `"isAdmin": true` to test for privilege escalation
- ⚠️ JSON Patch format (`{ "op": "replace", "path": "/role", "value": "admin" }`) can bypass validation

---


### Day 5 — PATCH Practice
<img width="1280" height="684" alt="Screenshot 2026-09-03 052246" src="https://github.com/user-attachments/assets/24fab316-2699-4c3c-b56a-2650f55d1f2b" />

**Request:**
```http
DELETE https://jsonplaceholder.typicode.com/posts/10
```

**Response:**
```json
{}
```

**Status Code:** `200 OK`  
**Response Time:** `974 ms`  
**Size:** `1.08 KB`

**Key Observations:**
- DELETE removes the resource
- No request body is needed
- Response body is empty `{}`
- The resource is permanently deleted

**Security Notes:**
- ⚠️ **CRITICAL:** No confirmation required — one request = permanent deletion
- ⚠️ **Authorization:** Always check if the user owns the resource before allowing DELETE
- ⚠️ **Cascade Delete:** Deleting a user might delete all their posts, comments, etc.
- ⚠️ **Test for BFLA:** Can a normal user DELETE `/admin/posts/1`?

---

### Day 3 — OPTIONS & Method Testing
- **OPTIONS /posts** → Allow: GET, POST, HEAD, OPTIONS
- **Observation:** PUT and DELETE not listed in Allow header

---

## 🔗 References

- [MDN HTTP Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
- [RFC 7231 - HTTP/1.1 Semantics](https://tools.ietf.org/html/rfc7231)
- [OWASP API Top 10 - API5 Broken Function Level Auth](https://owasp.org/www-project-api-security/)

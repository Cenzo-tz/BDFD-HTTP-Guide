# Bdfd-https-
Complete free guide of bdfd $http functions with examples # 🌐 HTTP Functions

> Learn how to communicate with APIs using BDFD. These functions power AI bots, economy systems, transcripts, welcome cards, databases, and much more.

---

## 🚀 `$httpPost[]`

Sends data to an API.

```bdfd
$httpPost[https://bdfdapi.xyz/api/example;
{
  "username":"cenzo",
  "message":"Hello from BDFD"
}
]
```

> 💡 Everything inside `{ }` is sent to the API.

### Common Uses

```diff
+ AI Chatbots
+ Economy Systems
+ Database Storage
+ Ticket Systems
+ User Data
```

---

## 📥 `$httpGet[]`

Gets data from an API.

```bdfd
$httpGet[https://bdfdapi.xyz/api/quote]
```

Get the response:

```bdfd
$httpResult
```

### Common Uses

```diff
+ Quotes
+ Search APIs
+ Weather APIs
+ User Profiles
+ Public Data
```

---

## ✏️ `$httpPut[]`

Replaces or updates existing data.

```bdfd
$httpPut[https://bdfdapi.xyz/api/user;
{
  "username":"cenzo",
  "coins":500
}
]
```

```yaml
Used when updating entire records.
```

---

## 🔧 `$httpPatch[]`

Updates only specific values.

```bdfd
$httpPatch[https://bdfdapi.xyz/api/user;
{
  "coins":1000
}
]
```

```yaml
Used when editing only a few fields.
```

---

## 🗑️ `$httpDelete[]`

Deletes data from an API.

```bdfd
$httpDelete[https://bdfdapi.xyz/api/user]
```

### Common Uses

```diff
- Delete User Data
- Remove Warnings
- Delete Economy Accounts
```

---

## 🔐 `$httpAddHeader[]`

Adds extra information to requests.

```bdfd
$httpAddHeader[Authorization;Bearer cenzo-secret-key]
```

Another common example:

```bdfd
$httpAddHeader[Content-Type;application/json]
```

```ini
[Required]
Most private APIs require headers.
```

---

## ❌ `$httpRemoveHeader[]`

Removes a previously added header.

```bdfd
$httpRemoveHeader[Authorization]
```

---

## 📊 `$httpStatus`

Returns the status code from the last request.

```bdfd
$httpGet[https://bdfdapi.xyz/api/quote]

Status: $httpStatus
```

### Common Status Codes

```diff
+ 200 = Success
+ 201 = Created

! 400 = Bad Request
! 401 = Unauthorized
! 403 = Forbidden
! 404 = Not Found

- 429 = Rate Limited
- 500 = Server Error
```

---

## 📄 `$httpResult`

Returns the full response from the last request.

```bdfd
$httpGet[https://bdfdapi.xyz/api/quote]

$httpResult
```

Example output:

```json
{
  "quote":"Stay hungry, stay foolish.",
  "author":"Steve Jobs"
}
```

---

## 🎯 `$httpResult[]`

Returns a specific value from JSON.

Example response:

```json
{
  "username":"cenzo",
  "website":"bdfdapi.xyz",
  "coins":500
}
```

Get username:

```bdfd
$httpResult[username]
```

Get website:

```bdfd
$httpResult[website]
```

Get coins:

```bdfd
$httpResult[coins]
```

```diff
+ Perfect when you only need one value.
```

---

## 📨 `$httpGetHeader[]`

Gets a header from the API response.

```bdfd
$httpGet[https://bdfdapi.xyz/api/quote]

$httpGetHeader[Content-Type]
```

Example output:

```http
application/json
```

Common headers:

```http
Content-Type
Cache-Control
Server
Date
```

---

# 💎 Most Used Functions

If you're new to APIs, learn these first:

```bdfd
$httpGet[]
$httpPost[]
$httpAddHeader[]
$httpResult[]
$httpStatus
```

```diff
+ Master these 5 functions
+ Use almost any API
+ Build AI, economy, transcripts, tickets, and more
```

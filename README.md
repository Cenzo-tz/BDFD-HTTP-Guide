# Bdfd-https-
Complete free guide of bdfd $http functions with examples 
# HTTP Functions

There are a few API supported functions in BDFD. These allow your bot to communicate with APIs such as bdfdapi.xyz.

# $httpPost[] (My Favourite)

Sends data to an API.

```bdfd
$httpPost[https://bdfdapi.xyz/api/example;
{
  "username":"cenzo",
  "message":"Hello from BDFD"
}
]
```

Everything inside `{ }` gets sent to the API.

---

# $httpGet[]

Gets data from an API.

```bdfd
$httpGet[https://bdfdapi.xyz/api/quote]
```

After making the request you can use:

```bdfd
$httpResult
```

to see the response.

---

# $httpPut[]

Updates existing data on an API.

```bdfd
$httpPut[https://bdfdapi.xyz/api/user;
{
  "username":"cenzo",
  "coins":500
}
]
```

Mostly used when you want to replace or update stored data.

---

# $httpPatch[]

Updates only specific parts of existing data.

```bdfd
$httpPatch[https://bdfdapi.xyz/api/user;
{
  "coins":1000
}
]
```

Similar to `$httpPut[]`, but only changes the values you provide.

---

# $httpDelete[]

Deletes data from an API.

```bdfd
$httpDelete[https://bdfdapi.xyz/api/user]
```

Useful when removing data from a database.

---

# $httpAddHeader[]

Adds extra information to a request.

```bdfd
$httpAddHeader[Authorization;Bearer cenzo-secret-key]
```

Another common example:

```bdfd
$httpAddHeader[Content-Type;application/json]
```

Many APIs require headers for authentication.

---

# $httpRemoveHeader[]

Removes a header that was added earlier.

```bdfd
$httpRemoveHeader[Authorization]
```

---

# $httpStatus

Returns the status code from the last request.

```bdfd
$httpGet[https://bdfdapi.xyz/api/quote]

Status: $httpStatus
```

Common status codes:

```text
200 = Success
404 = Not Found
500 = Server Error
```

---

# $httpResult

Returns the full response from the last request.

```bdfd
$httpGet[https://bdfdapi.xyz/api/quote]

$httpResult
```

---

# $httpResult[]

Returns a specific value from a JSON response.

Example response:

```json
{
  "username":"cenzo",
  "website":"bdfdapi.xyz",
  "coins":500
}
```

Get the username:

```bdfd
$httpResult[username]
```

Get the website:

```bdfd
$httpResult[website]
```

Get the coins:

```bdfd
$httpResult[coins]
```

---

# $httpGetHeader[]

Gets a header from the API response.

```bdfd
$httpGet[https://bdfdapi.xyz/api/quote]
$httpGetHeader[Content-Type]
```
Example output:
```text
application/json
```

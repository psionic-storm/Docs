# Sign Up

### Method & Endpoint
```
POST /api/signUp
```
### Parameters
*In : header, path, query, body

|Name|Type|In|Description|
|-|-|-|-|
|loginId|string|body|login id|
|password|string|body|password|
|nickname|string|body|nickname|

### Default Response
```
Status: 201 Created
```

```json
34
```
### Conflict
```
Status: 409 Conflict
```
```json
{ 
    "message": "이미 있는 아이디"
}
```

# Sign In
### Method & Endpoint
```
GET /api/signIn
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|loginId|string|body|login id|
|password|string|body|password|

### Default Response
```
Status: 200 OK
```
```json
{
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJsb2dpbklkIjoibXlJZDUzMTU0MjU1IiwiaWF0IjoxNjE1NzA5MzcwfQ.mI_3WXnutL39Z8im68Kx6Rhi0AYMi-atEEO_yv1VJZw"
}
```

### Unauthorized
```
Status: 401 Unauthorized
```
```json
Unauthorized
```

# Get My UserInfo
### Method & Endpoint
```
GET /api/user
```
### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|accessToken|string|header|login id|

### Default Response
```
Status: 200 OK
```

```json
{
    "id": 33,
    "login_id": "jungcome7",
    "nickname": "Granzort"
}
```


### Space

### Salon

### Book

### Review

### Quote
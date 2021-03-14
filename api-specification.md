# API Specification
|Category|Desc|Method|Endpoint|
|-|-|-|-|
|Auth|[Sign Up](#sign-up)|POST|`/api/user/signUp`|
|Auth|[Sign In](#sign-in)|POST|`/api/user/signIn`|
|Auth|[Get My UserInfo](#get-my-userinfo)|GET|`/api/user`|

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
34 (User Id)
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
|Authorization|string|header|accessToken|

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


# Get a Space
### Method & Endpoint
```
GET /api/space/[spaceId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|

### Default Response
```
Status: 200 OK
```
```json
    "owner_id": "jungcome7",
    "owner_nickname": "Granzort",
    "books": [
        {
            "title": "Also Sprach Zarathustra",
            "author": "Friedrich Nietzsche",
            "description": "Long time ago..."
        }
    ]
```

# Get a Salon

### Method & Endpoint
```
POST /api/salon/[salonId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|

### Default Response
```
Status: 200 OK
```
```json
{
    "name": "MadoKing Granzort",
    "owner_id": "jungcome7",
    "owner_nickname": "Granzort",
    "participants": [
        { "login_id": "mooncrystalpwr", "nickname": "Poseidon" },
        { "login_id": "fouriertrf", "nickname": "Zarathustra" }
    ],
    "books": [
        {
            "title": "Also Sprach Zarathustra",
            "author": "Friedrich Nietzsche",
            "description": "Long time ago..."
        }
    ]
```

### Modify a Space
### Method & Endpoint
```
PATCH /api/space/[spaceId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|name|string|body|new space name|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "modified successfully"
}
```
# Create a Salon
### Method & Endpoint
```
POST /api/salon
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|name|string|body|salon name|

### Default Response
```
Status: 201 Created
```
```json
34 (Salon Id)
```

### Modify a Salon
### Method & Endpoint
```
PATCH /api/salon/[salonId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|name|string|body|new salon name|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "modified successfully"
}
```

### Delete a Salon
### Method & Endpoint
```
GET /api/salon/[salonId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "deleted successfully"
}
```

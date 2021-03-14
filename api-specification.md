# API Specification
|Category|Desc|Method|Endpoint|
|-|-|-|-|
|User|[Sign Up](#sign-up)|POST|`/api/user/signUp`|
|User|[Sign In](#sign-in)|POST|`/api/user/signIn`|
|User|[Get My UserInfo](#get-my-userinfo)|GET|`/api/user`|
|User|[Get My Books, Reviews and Quotes]()||``|
|Square|[Get All Reviews]()||``|
|Square|[Get All Quotes]()||``|
|Space|[Get a Space](#get-a-space)|GET|`/api/space/[spaceId]`|
|Space|[Modify a Space](#modify-a-space)|PATCH|`/api/space/[spaceId]`|
|Salon|[Get a Salon](#get-a-salon)|GET|`/api/salon/[salonId]`|
|Salon|[Modify a Salon](#modify-a-salon)|PATCH|`/api/salon/[salonId]`|
|Salon|[Delete a Salon](#delete-a-salon)|DELETE|`/api/salon/[salonId]`|
|Book|[Get a Book]()|GET|`/api`|
|Book|[Add a Book to My space]()|GET|`/api`|
|Book|[Add a Book to Salon]()|GET|`/api`|
|Book|[Delete a Book from My space]()|GET|`/api`|
|Book|[Delete a Book from Salon]()|GET|`/api`|
|Review|[Get all Reviews in a Book]()|GET|`/api`|
|Review|[Get a Review]()|GET|`/api`|
|Review|[Create a Review]()|GET|`/api`|
|Review|[Modify a Review]()|GET|`/api`|
|Review|[Delete a Review]()|GET|`/api`|
|Review Comment|[Get all Review Comments in a Review]()|GET|`/api`|
|Review Comment|[Create a Review Comment]()|GET|`/api`|
|Review Comment|[Modify a Review Comment]()|GET|`/api`|
|Review Comment|[Delete a Review Comment]()|GET|`/api`|
|Quote|[Get all Quotes in a Book]()|GET|`/api`|
|Quote|[Get a Quote]()|GET|`/api`|
|Quote|[Create a Quote]()|GET|`/api`|
|Quote|[Modify a Quote]()|GET|`/api`|
|Quote|[Delete a Quote]()|GET|`/api`|
|Quote Comment|[Get all Quote Comments in a Quote]()|GET|`/api`|
|Quote Comment|[Create a Quote Comment]()|GET|`/api`|
|Quote Comment|[Modify a Quote Comment]()|GET|`/api`|
|Quote Comment|[Delete a Quote Comment]()|GET|`/api`|

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

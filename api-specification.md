# API Specification
|Category|Desc|Method|Endpoint|
|-|-|-|-|
|User|[Sign Up](#user---sign-up)|POST|`/api/user/signUp`|
|User|[Sign In](#user---sign-in)|POST|`/api/user/signIn`|
|User|[Get My UserInfo](#user---get-my-userinfo)|GET|`/api/user`|
|Square|[Get All Reviews](#square---get-all-reviews)|GET|`/api/square/reviews`|
|Square|[Get All Quotes](#square---get-all-quotes)|GET|`/api/square/quotes`|
|Space|[Get a Space](#space---get-a-space)|GET|`/api/space/[spaceId]`|
|Space|[Modify a Space](#space---modify-a-space)|PATCH|`/api/space/[spaceId]`|
|Space|[Get a Book in the Space](#space---get-a-book-in-the-space)|GET|`/api/space/[spaceId]/book/[bookId]`|
|Space|[Add a Book to My space](#space---add-a-book-to-my-space)|POST|`/api/space/[spaceId]/book`|
|Space|[Delete a Book from My space](#space---delete-a-book-from-my-space)|DELETE|`/api/space/[spaceId]/book/[bookId]`|
|Salon|[Get a Salon](#salon---get-a-salon)|GET|`/api/salon/[salonId]`|
|Salon|[Modify a Salon](#salon---modify-a-salon)|PATCH|`/api/salon/[salonId]`|
|Salon|[Delete a Salon](#salon---delete-a-salon)|DELETE|`/api/salon/[salonId]`|
|Salon|[Get a Book in the Salon](#salon---get-a-book-in-the-salon)|GET|`/api/salon/[salonId]/book/[bookId]`|
|Salon|[Add a Book to the Salon](#salon---add-a-book-to-the-salon)|POST|`/api/salon/[salonId]/book`|
|Salon|[Delete a Book from Salon](#salon---delete-a-book-from-the-salon)|DELETE|`/api/salon/[salonId]/book/[bookId]`|
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

# User - Sign Up

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

# User - Sign In
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

# User - Get My UserInfo
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

# Square - Get All Reviews

### Method & Endpoint
```
GET /api/square/reviews
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|-|-|-|-|

### Default Response
```
Status: 200 OK
```
```json
{
    "reviews": [
        {
            "title": "I am Zarathustra..",
            "content": "this is..",
            "reviewer": "Granzort",
            "created_at": "2020-01-02",
            "updated_at": "2020-01-02",
            "book_title": "Also Sprach Zarathustra",
            "book_author": "Also Sprach Zarathustra",
            "salon": "null",
            "space": "Granzort's space",
        }
    ]
}
```

# Square - Get All Quotes

### Method & Endpoint
```
GET /api/square/quotes
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|-|-|-|-|

### Default Response
```
Status: 200 OK
```
```json
{
    "quotes": [
        {
            "title": "I am Zarathustra..",
            "content": "this is..",
            "quoter": "Granzort",
            "created_at": "2020-01-02",
            "updated_at": "2020-01-02",
            "book_title": "Also Sprach Zarathustra",
            "book_author": "Also Sprach Zarathustra",
            "salon": "null",
            "space": "Granzort's space",
        }
    ]
}
```

# Space - Get a Space
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
    "name": "Granzort's space",
    "books": [
        {
            "title": "Also Sprach Zarathustra",
            "author": "Friedrich Nietzsche",
            "description": "Long time ago..."
        }
    ]
```

# Space - Modify a Space
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


# Space - Get a Book in the Space
### Method & Endpoint
```
GET /api/space/[spaceId]/book/[bookId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|

### Default Response
```
Status: 200 OK
```
```json
{
    "title": "Also Sprach Zarathustra",
    "author": "Friedrich Nietzsche",
    "description": "Long time ago...",
    "reviews": [
        {
            "title": "I am Zarathustra..",
            "content": "this is..",
            "reviewer": "Granzort",
            "created_at": "2020-01-02",
            "updated_at": "2020-01-02",
            "book_title": "Also Sprach Zarathustra",
            "book_author": "Also Sprach Zarathustra",
            "salon": "null",
            "space": "Granzort's space",
        }
    ],
    "quotes": [
        {
            "title": "I am Zarathustra..",
            "content": "this is..",
            "quoter": "Granzort",
            "created_at": "2020-01-02",
            "updated_at": "2020-01-02",
            "book_title": "Also Sprach Zarathustra",
            "book_author": "Also Sprach Zarathustra",
            "salon": "null",
            "space": "Granzort's space",
        }
    ]
}
```


# Space - Add a Book to My Space
### Method & Endpoint
```
POST /api/space/[spaceId]/book
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|title|string|body|book title|
|author|string|body|book author|
|description|string|body|book description|

### Default Response
```
Status: 201 Created
```
```json
365 (Book Id)
```
# Space - Delete a Book from My Space
### Method & Endpoint
```
DELETE /api/space/[spaceId]/book/[bookId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|

### Default Response
```
Status: 200 OK
```
```json
{ "message": "deleted successfully" }
```
# Salon - Get a Salon

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

# Salon - Create a Salon
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

# Salon - Modify a Salon
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

### Salon - Delete a Salon
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

# Salon - Get a Book in the Salon
### Method & Endpoint
```
GET /api/salon/[salonId]/book/[bookId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path| salon id|
|bookId|string|path|book id|

### Default Response
```
Status: 200 OK
```
```json
{
    "title": "Also Sprach Zarathustra",
    "author": "Friedrich Nietzsche",
    "description": "Long time ago...",
    "reviews": [
        {
            "title": "I am Zarathustra..",
            "content": "this is..",
            "reviewer": "Granzort",
            "created_at": "2020-01-02",
            "updated_at": "2020-01-02",
            "book_title": "Also Sprach Zarathustra",
            "book_author": "Also Sprach Zarathustra",
            "salon": "null",
            "space": "Granzort's space",
        }
    ],
    "quotes": [
        {
            "title": "I am Zarathustra..",
            "content": "this is..",
            "quoter": "Granzort",
            "created_at": "2020-01-02",
            "updated_at": "2020-01-02",
            "book_title": "Also Sprach Zarathustra",
            "book_author": "Also Sprach Zarathustra",
            "salon": "null",
            "space": "Granzort's space",
        }
    ]
}
```
# Salon - Add a Book to the Salon
### Method & Endpoint
```
POST /api/salon/[salonId]/book
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|title|string|body|book title|
|author|string|body|book author|
|description|string|body|book description|

### Default Response
```
Status: 201 Created
```
```json
365 (Book Id)
```
# Salon - Delete a Book from the Salon
### Method & Endpoint
```
DELETE /api/salon/[salonId]/book/[bookId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|bookId|string|path|book id|

### Default Response
```
Status: 200 OK
```
```json
{ "message": "deleted successfully" }
```
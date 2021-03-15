# API Specification
|Category|Desc|Method|Endpoint|
|:-:|:-|:-:|:-|
|🧔 User|[Sign Up](#user---sign-up)|POST|`/api/user/signUp`|
|🧔 User|[Sign In](#user---sign-in)|POST|`/api/user/signIn`|
|🧔 User|[Get My UserInfo](#user---get-my-userinfo)|GET|`/api/user`|
|🏛 Square|[Get All Reviews](#square---get-all-reviews)|GET|`/api/square/reviews`|
|🏛 Square|[Get All Quotes](#square---get-all-quotes)|GET|`/api/square/quotes`|
|📂 Space|[Get a Space](#space---get-a-space)|GET|`/api/space/[spaceId]`|
|📂 Space|[Modify a Space](#space---modify-a-space)|PATCH|`/api/space/[spaceId]`|
|📂 Space|[Get a Book in the Space](#space---get-a-book-in-the-space)|GET|`/api/space/[spaceId]/book/[bookId]`|
|📂 Space|[Add a Book to My space](#space---add-a-book-to-my-space)|POST|`/api/space/[spaceId]/book`|
|📂 Space|[Delete a Book from My space](#space---delete-a-book-from-my-space)|DELETE|`/api/space/[spaceId]/book/[bookId]`|
|📂 Space|[Create a Review](#space---create-a-review)|POST|`/api/space/[spaceId]/book/[bookId]/review`|
|📂 Space|[Modify a Review](#space---modify-a-review)|PATCH|`/api/space/[spaceId]/book/[bookId]/review/[reviewId]`|
|📂 Space|[Delete a Review](#space---delete-a-review)|DELETE|`/api/space/[spaceId]/book/[bookId]/review/[reviewId]`|
|📂 Space|[Get all Review Comments in a Review](#space---get-all-review-comments-in-a-review)|GET|`/api/space/[spaceId]/book/[bookId]/review/[reviewId]/comment`|
|📂 Space|[Create a Review Comment](#space---create-a-review-comment)|POST|`/api/space/[spaceId]/book/[bookId]/review/[reviewId]/comment`|
|📂 Space|[Modify a Review Comment](#space---modify-a-review-comment)|PATCH|`/api/space/[spaceId]/book/[bookId]/review/[reviewId]/comment/[commentId]`|
|📂 Space|[Delete a Review Comment](#space---delete-a-review-comment)|DELETE|`/api/space/[spaceId]/book/[bookId]/review/[reviewId]/comment/[commentId]`|
|📂 Space|[Create a Quote](#space---create-a-quote)|POST|`/api/space/[spaceId]/book/[bookId]/quote`|
|📂 Space|[Modify a Quote](#space---modify-a-quote)|PATCH|`/api/space/[spaceId]/book/[bookId]/quote/[quoteId]`|
|📂 Space|[Delete a Quote](#space---delete-a-quote)|DELETE|`/api/space/[spaceId]/book/[bookId]/quote/[quoteId]`|
|📂 Space|[Get all Quote Comments in a Quote](#space---get-all-quote-comments-in-a-quote)|GET|`/api/space/[spaceId]/book/[bookId]/quote/[quoteId]/comment`|
|📂 Space|[Create a Quote Comment](#space---create-a-quote-comment)|POST|`/api/space/[spaceId]/book/[bookId]/quote/[quoteId]/comment`|
|📂 Space|[Modify a Quote Comment](#space---modify-a-quote-comment)|PATCH|`/api/space/[spaceId]/book/[bookId]/quote/[quoteId]/comment/[commentId]`|
|📂 Space|[Delete a Quote Comment](#space---delete-a-quote-comment)|DELETE|`/api/space/[spaceId]/book/[bookId]/quote/[quoteId]/comment/[commentId]`|
|💒 Salon|[Get a Salon](#salon---get-a-salon)|GET|`/api/salon/[salonId]`|
|💒 Salon|[Modify a Salon](#salon---modify-a-salon)|PATCH|`/api/salon/[salonId]`|
|💒 Salon|[Delete a Salon](#salon---delete-a-salon)|DELETE|`/api/salon/[salonId]`|
|💒 Salon|[Get a Book in the Salon](#salon---get-a-book-in-the-salon)|GET|`/api/salon/[salonId]/book/[bookId]`|
|💒 Salon|[Add a Book to the Salon](#salon---add-a-book-to-the-salon)|POST|`/api/salon/[salonId]/book`|
|💒 Salon|[Delete a Book from Salon](#salon---delete-a-book-from-the-salon)|DELETE|`/api/salon/[salonId]/book/[bookId]`|
|💒 Salon|[Create a Review](#salon---create-a-review)|POST|`/api/salon/[salonId]/book/[bookId]/review`|
|💒 Salon|[Modify a Review](#salon---modify-a-review)|PATCH|`/api/salon/[salonId]/book/[bookId]/review/[reviewId]`|
|💒 Salon|[Delete a Review](#salon---delete-a-review)|DELETE|`/api/salon/[salonId]/book/[bookId]/review/[reviewId]`|
|💒 Salon|[Get all Review Comments in a Review](#salon---get-all-review-comments-in-a-review)|GET|`/api/salon/[salonId]/book/[bookId]/review/[reviewId]/comment`|
|💒 Salon|[Create a Review Comment](#salon---create-a-review-comment)|POST|`/api/salon/[salonId]/book/[bookId]/review/[reviewId]/comment`|
|💒 Salon|[Modify a Review Comment](#salon---modify-a-review-comment)|PATCH|`/api/salon/[salonId]/book/[bookId]/review/[reviewId]/comment/[commentId]`|
|💒 Salon|[Delete a Review Comment](#salon---delete-a-review-comment)|DELETE|`/api/salon/[salonId]/book/[bookId]/review/[reviewId]/comment/[commentId]`|
|💒 Salon|[Create a Quote](#salon---create-a-quote)|POST|`/api/salon/[salonId]/book/[bookId]/quote`|
|💒 Salon|[Modify a Quote](#salon---modify-a-quote)|PATCH|`/api/salon/[salonId]/book/[bookId]/quote/[quoteId]`|
|💒 Salon|[Delete a Quote](#salon---delete-a-quote)|DELETE|`/api/salon/[salonId]/book/[bookId]/quote/[quoteId]`|
|💒 Salon|[Get all Quote Comments in a Quote](#salon---get-all-quote-comments-in-a-quote)|GET|`/api/salon/[salonId]/book/[bookId]/quote/[quoteId]/comment`|
|💒 Salon|[Create a Quote Comment](#salon---create-a-quote-comment)|POST|`/api/salon/[salonId]/book/[bookId]/quote/[quoteId]/comment`|
|💒 Salon|[Modify a Quote Comment](#salon---modify-a-quote-comment)|PATCH|`/api/salon/[salonId]/book/[bookId]/quote/[quoteId]/comment/[commentId]`|
|💒 Salon|[Delete a Quote Comment](#salon---delete-a-quote-comment)|DELETE|`/api/salon/[salonId]/book/[bookId]/quote/[quoteId]/comment/[commentId]`|


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
            "id": 1,
            "title": "I am Zarathustra..",
            "content": "this is..",
            "reviewer": "Granzort",
            "created_at": "2020-01-02",
            "updated_at": "2020-01-02",
            "book_title": "Also Sprach Zarathustra",
            "book_author": "Friedrich Nietzsche",
            "salon": null,
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
            "id":1,
            "title": "I am Zarathustra..",
            "content": "this is..",
            "page": 218,
            "quoter": "Granzort",
            "created_at": "2020-01-02",
            "updated_at": "2020-01-02",
            "book_title": "Also Sprach Zarathustra",
            "book_author": "Friedrich Nietzsche",
            "salon": null,
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
{
    "owner_id": "jungcome7",
    "owner_nickname": "Granzort",
    "name": "Granzort's space",
    "books": [
        {
            "id": 1,
            "title": "Also Sprach Zarathustra",
            "author": "Friedrich Nietzsche",
            "description": "Long time ago..."
        }
    ]
}
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
    "salon": null,
    "space": "Granzort's space",
    "reviews": [
        {
            "id":1,
            "title": "I am Zarathustra..",
            "content": "this is..",
            "reviewer": "Granzort",
            "created_at": "2020-01-02",
            "updated_at": "2020-01-02",
            "book_title": "Also Sprach Zarathustra",
            "book_author": "Friedrich Nietzsche",
        }
    ],
    "quotes": [
        {
            "id":1,
            "title": "I am Zarathustra..",
            "content": "this is..",
            "page": 218,
            "quoter": "Granzort",
            "created_at": "2020-01-02",
            "updated_at": "2020-01-02",
            "book_title": "Also Sprach Zarathustra",
            "book_author": "Friedrich Nietzsche",
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

# Space - Create a Review
### Method & Endpoint
```
POST /api/space/[spaceId]/book/[bookId]/review
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|
|title|string|body|review title|
|content|string|body|review content|

### Default Response
```
Status: 201 Created
```
```json
36 (Review Id)
```

# Space - Modify a Review
### Method & Endpoint
```
PATCH /api/space/[spaceId]/book/[bookId]/review/[reviewId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|
|reviewId|string|path|review id|
|title|string|body|new review title|
|content|string|body|new review content|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "modified successfully"
}
```

# Space - Delete a Review
### Method & Endpoint
```
DELETE /api/space/[spaceId]/book/[bookId]/review/[reviewId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|
|reviewId|string|path|review id|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "deleted successfully"
}
```

# Space - Get all Review Comments in a Review
### Method & Endpoint
```
GET /api/space/[spaceId]/book/[bookId]/review/[reviewId]/comment
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|
|reviewId|string|path|review id|

### Default Response
```
Status: 200 OK
```
```json
{
    "review_comments": [
        {
            "comment": "this is..",
            "commenter": "Granzort",
            "created_at": "2020-01-02",
            "updated_at": "2020-01-02",
        }
    ]
}
```


# Space - Create a Review Comment
### Method & Endpoint
```
POST /api/space/[spaceId]/book/[bookId]/review/[reviewId]/comment
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|
|comment|string|body|review comment|

### Default Response
```
Status: 201 Created
```
```json
36 (Review Comment Id)
```

# Space - Modify a Review Comment
### Method & Endpoint
```
PATCH /api/space/[spaceId]/book/[bookId]/review/[reviewId]/comment/[commentId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|
|reviewId|string|path|review id|
|commentId|string|path|comment id|
|comment|string|body|review comment|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "modified successfully"
}
```

# Space - Delete a Review Comment
### Method & Endpoint
```
DELETE /api/space/[spaceId]/book/[bookId]/review/[reviewId]/comment/[commentId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|
|reviewId|string|path|review id|
|commentId|string|path|comment id|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "deleted successfully"
}
```

# Space - Create a Quote
### Method & Endpoint
```
POST /api/space/[spaceId]/book/[bookId]/quote
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|
|content|string|body|quote content|
|page|string|body|quote page|

### Default Response
```
Status: 201 Created
```
```json
36 (quote Id)
```

# Space - Modify a Quote
### Method & Endpoint
```
PATCH /api/space/[spaceId]/book/[bookId]/quote/[quoteId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|
|quoteId|string|path|quote id|
|content|string|body|new quote content|
|page|string|body|new quote page|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "modified successfully"
}
```

# Space - Delete a Quote
### Method & Endpoint
```
DELETE /api/space/[spaceId]/book/[bookId]/quote/[quoteId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|
|quoteId|string|path|quote id|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "deleted successfully"
}
```

# Space - Get all quote Comments in a Quote
### Method & Endpoint
```
GET /api/space/[spaceId]/book/[bookId]/quote/[quoteId]/comment
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|
|quoteId|string|path|quote id|

### Default Response
```
Status: 200 OK
```
```json
{
    "quote_comments": [
        {
            "comment": "this is..",
            "commenter": "Granzort",
            "created_at": "2020-01-02",
            "updated_at": "2020-01-02",
        }
    ]
}
```


# Space - Create a Quote Comment
### Method & Endpoint
```
POST /api/space/[spaceId]/book/[bookId]/quote/[quoteId]/comment
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|
|comment|string|body|quote comment|

### Default Response
```
Status: 201 Created
```
```json
36 (quote Comment Id)
```

# Space - Modify a Quote Comment
### Method & Endpoint
```
PATCH /api/space/[spaceId]/book/[bookId]/quote/[quoteId]/comment/[commentId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|
|quoteId|string|path|quote id|
|commentId|string|path|comment id|
|comment|string|body|quote comment|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "modified successfully"
}
```

# Space - Delete a Quote Comment
### Method & Endpoint
```
DELETE /api/space/[spaceId]/book/[bookId]/quote/[quoteId]/comment/[commentId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|spaceId|string|path|space id|
|bookId|string|path|book id|
|quoteId|string|path|quote id|
|commentId|string|path|comment id|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "deleted successfully"
}
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
            "book_author": "Friedrich Nietzsche",
            "salon": null,
            "space": "Granzort's space",
        }
    ],
    "quotes": [
        {
            "title": "I am Zarathustra..",
            "content": "this is..",
            "page": 218,
            "quoter": "Granzort",
            "created_at": "2020-01-02",
            "updated_at": "2020-01-02",
            "book_title": "Also Sprach Zarathustra",
            "book_author": "Friedrich Nietzsche",
            "salon": null,
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


# Salon - Create a Review
### Method & Endpoint
```
POST /api/salon/[salonId]/book/[bookId]/review
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|bookId|string|path|book id|
|title|string|body|review title|
|content|string|body|review content|

### Default Response
```
Status: 201 Created
```
```json
36 (Review Id)
```

# Salon - Modify a Review
### Method & Endpoint
```
PATCH /api/salon/[salonId]/book/[bookId]/review/[reviewId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|bookId|string|path|book id|
|reviewId|string|path|review id|
|title|string|body|new review title|
|content|string|body|new review content|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "modified successfully"
}
```

# Salon - Delete a Review
### Method & Endpoint
```
DELETE /api/salon/[salonId]/book/[bookId]/review/[reviewId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|bookId|string|path|book id|
|reviewId|string|path|review id|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "deleted successfully"
}
```

# Salon - Get all Review Comments in a Review
### Method & Endpoint
```
GET /api/salon/[salonId]/book/[bookId]/review/[reviewId]/comment
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|bookId|string|path|book id|
|reviewId|string|path|review id|

### Default Response
```
Status: 200 OK
```
```json
{
    "review_comments": [
        {
            "comment": "this is..",
            "commenter": "Granzort",
            "created_at": "2020-01-02",
            "updated_at": "2020-01-02",
        }
    ]
}
```

# Salon - Create a Review Comment
### Method & Endpoint
```
POST /api/salon/[salonId]/book/[bookId]/review/[reviewId]/comment
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|bookId|string|path|book id|
|comment|string|body|review comment|

### Default Response
```
Status: 201 Created
```
```json
36 (Review Comment Id)
```

# Salon - Modify a Review Comment
### Method & Endpoint
```
PATCH /api/salon/[salonId]/book/[bookId]/review/[reviewId]/comment/[commentId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|bookId|string|path|book id|
|reviewId|string|path|review id|
|commentId|string|path|comment id|
|comment|string|body|review comment|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "modified successfully"
}
```

# Salon - Delete a Review Comment
### Method & Endpoint
```
DELETE /api/salon/[salonId]/book/[bookId]/review/[reviewId]/comment/[commentId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|bookId|string|path|book id|
|reviewId|string|path|review id|
|commentId|string|path|comment id|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "deleted successfully"
}
```
# Salon - Create a Quote
### Method & Endpoint
```
POST /api/salon/[salonId]/book/[bookId]/quote
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|bookId|string|path|book id|
|content|string|body|quote content|
|page|string|body|quote page|

### Default Response
```
Status: 201 Created
```
```json
36 (quote Id)
```

# Salon - Modify a Quote
### Method & Endpoint
```
PATCH /api/salon/[salonId]/book/[bookId]/quote/[quoteId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|bookId|string|path|book id|
|quoteId|string|path|quote id|
|content|string|body|new quote content|
|page|string|body|new quote page|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "modified successfully"
}
```

# Salon - Delete a Quote
### Method & Endpoint
```
DELETE /api/salon/[salonId]/book/[bookId]/quote/[quoteId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|bookId|string|path|book id|
|quoteId|string|path|quote id|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "deleted successfully"
}
```

# Salon - Get all quote Comments in a Quote
### Method & Endpoint
```
GET /api/salon/[salonId]/book/[bookId]/quote/[quoteId]/comment
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|bookId|string|path|book id|
|quoteId|string|path|quote id|

### Default Response
```
Status: 200 OK
```
```json
{
    "quote_comments": [
        {
            "comment": "this is..",
            "commenter": "Granzort",
            "created_at": "2020-01-02",
            "updated_at": "2020-01-02",
        }
    ]
}
```


# Salon - Create a Quote Comment
### Method & Endpoint
```
POST /api/salon/[salonId]/book/[bookId]/quote/[quoteId]/comment
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|bookId|string|path|book id|
|comment|string|body|quote comment|

### Default Response
```
Status: 201 Created
```
```json
36 (quote Comment Id)
```

# Salon - Modify a Quote Comment
### Method & Endpoint
```
PATCH /api/salon/[salonId]/book/[bookId]/quote/[quoteId]/comment/[commentId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|bookId|string|path|book id|
|quoteId|string|path|quote id|
|commentId|string|path|comment id|
|comment|string|body|quote comment|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "modified successfully"
}
```

# Salon - Delete a Quote Comment
### Method & Endpoint
```
DELETE /api/salon/[salonId]/book/[bookId]/quote/[quoteId]/comment/[commentId]
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|salonId|string|path|salon id|
|bookId|string|path|book id|
|quoteId|string|path|quote id|
|commentId|string|path|comment id|

### Default Response
```
Status: 200 OK
```
```json
{
    "message": "deleted successfully"
}
```
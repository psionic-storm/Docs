# API Specification

## User 
|Description|Method|Endpoint|
|:-|:-|:-|
|[Sign Up](#user---sign-up)|POST|`/api/user/sign-up`|
|[Sign In](#user---sign-in)|POST|`/api/user/sign-in`|
|[Get My UserInfo](#user---get-my-userinfo)|GET|`/api/user`|
|[Refresh Tokens](#user---get-my-userinfo)|POST|`/api/user/silent-refresh`|


## User
### Sign Up
```
POST /api/user/sign-up
```

#### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|email|string|body|email|
|password|string|body|password|

### Response
`
Status: 201 Created
`
```
{
    "email": "jungcome7@gmail.com",
    "nickname": "jungcome7"
}
```


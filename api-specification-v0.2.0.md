# API Specification

## 😇 User 
|Description|Method|Endpoint|
|:-|:-|:-|
|[Sign Up](#sign-up)|POST|`/api/user/sign-up`|
|[Sign In](#sign-in)|POST|`/api/user/sign-in`|
|[Get My UserInfo](#get-my-userinfo)|GET|`/api/user`|
|[Refresh Tokens](#refresh-tokens)|POST|`/api/user/silent-refresh`|


# 😇 User
## Sign Up
```
POST /api/user/sign-up
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|email|string|body|email|
|password|string|body|password|

### Response
```
Status: 201 Created
```
```
{
    "email": "jungcome7@gmail.com",
    "nickname": "jungcome7"
}
```


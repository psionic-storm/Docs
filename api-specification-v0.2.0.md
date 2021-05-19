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

## Sign In
```
POST /api/user/sign-in
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|email|string|body|email|
|password|string|body|password|

### Response
```
Status: 200 Ok
```
```
{
    "accessToken": "eyJadsfR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJqdW5nY29tZTasdfdd29tIiwibmlja25hbWUiOiJqdW5nY29tZTciLdasfadfQiOjE2MjE0MTdsafafV4cCI6MTYyMTQxNDgyNn0.buryuSzgeUasdfasfafdfd1qsl1MMilkJE31U"
}
```

## Get My UserInfo
```
GET /api/user
```


### Response
```
Status: 200 Ok
```
```
{
    "id": 1,
    "email": "jungcome7@gmail.com",
    "nickname": "jungcome7"
}
```

## Refresh Tokens
```
POST /api/user/slient-refresh
```

### Parameters
|Name|Type|In|Description|
|-|-|-|-|
|refreshToken|string|header(cookie)|refresh token|

### Response
```
Status: 200 Ok
```
```
{
    "accessToken": "eyJadsfR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJqdW5nY29tZTasdfdd29tIiwibmlja25hbWUiOiJqdW5nY29tZTciLdasfadfQiOjE2MjE0MTdsafafV4cCI6MTYyMTQxNDgyNn0.buryuSzgeUasdfasfafdfd1qsl1MMilkJE31U"
}
```

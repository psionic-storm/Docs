# API Specification
## Sign Up

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

## Sign In


### Space

### Salon

### Book

### Review

### Quote
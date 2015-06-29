---
current_menu: auth
---

# Authentication

Before used API, you need to authenticate. With your bealder's plateform account (email and password), you will get Token.

	POST https://api.bealder.com/v2/auth

## 	Parameters

| Name    	| Type      | Description                        |
|-----------|-----------|------------------------------------|
| email	  	| String	|  Your Email						 |
| password  | String    |  Your password					 |

##	Success Response

```json
{
    "status": "success",
    "session": {
        "token": "e3af52364f769c73f826c2fccdae57c9",
        "email": "YOUR_MAIL",
        "valid": "2015-06-24T15:03:31+0200"
    },
    "code": 200,
}
```

##	Error Response

```json
{
    "status": "error",
    "error_message": "no user found",
    "code": 404
}
```

## Use TOKEN

**Use this token for all call to API**
---
current_menu: profile
---

# Profile

This section helps you to get/update your profile on bealder platform.


## Get profile

	GET https://api.bealder.com/v2/profile

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your session token						 |


### Example

```bash
curl -X GET https://api.bealder.com/v2/profile
 -H "content-Type:application/json" 
 -H "x-bealder-key:example@bealder.com"
 -H "x-bealder-token:528afea53e678b6b4b9acfd947c24381"
```

###	Success Response

```json
{  
   "id":1,
   "email":"example@bealder.com",
   "name":"John DOE",
   "fonction":"Salesman",
   "active":true,
   "company":{  
      "id":1,
      "name":"Example Company",
      "image":"/path/to/my/image.png",
      "description":"Company Description",
      "active":true,
      "create_on":"2015-06-07T00:00:00+0200",
   },
   "permission":{  
      "profile":2,
      "campaign":2,
      "device":0,
      "analytic":2,
      "region":2,
      "beacon":2,
      "realtime":0,
      "nfc":0,
      "qrcode":2,
      "tag":0,
      "connector":0,
      "fidelity":0,
      "form":0,
      "crm":2
   }
}
```

###	Error Response

```json
{
	"status":"error",
	"message":"no session",
	"code":401
}
```


## Get applications

	GET https://api.bealder.com/v2/profile/application

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


### Example

```bash
curl -X GET https://api.bealder.com/v2/profile/application
 -H "content-Type:application/json"
 -H "x-bealder-key:kevin@bealder.com"
 -H "x-bealder-token:20f586ec4b244e00a81d00bca91b7d7f"
```


###	Success Response

```json
[  
   {  
      "id":1,
      "name":"Bealder Android",
      "type":"android",
      "api_key":"45e400d31369618b5f823050c1d63c5n",
      "api_id":"87",
      "active":true,
      "expire_on":"2014-07-22T18:44:00+0200"
   },
   {  
      "id":4,
      "name":"Bealder iOS",
      "type":"ios",
      "api_key":"648130d0d2a37ec8b05d98fa17f4ec12",
      "api_id":"",
      "active":true,
      "expire_on":"2022-08-07T00:00:00+0200"
   }
]
```


To get your token, go to [authentication](authentication.html).
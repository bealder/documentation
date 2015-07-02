---
current_menu: connector
---

# Connector

This section allows you to configure a connector to your own api. 

This way you can organize the following workflow : 
	- Register your api
	- Create a campaign and select 'connector' format

Every time a beacon is detected, a cloud to cloud call is done between Bealder API and your API.

This way you can easily make your own segmentation in addition to Bealder segmentation for push notification content.

## GET connector

	GET https://api.bealder.com/v2/connector


### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

### Example

```bash
curl -X GET https://api.bealder.com/v2/connector -H "content-Type:application/json" -H "x-bealder-key:example@bealder.com" -H "x-bealder-token:ec311746cf596d94cabea9f9d261eb3a"
```

### Success Response

```json
{  
   "id":2,
   "name":"My company CRM",
   "url":"http:\/\/.api.mycompany.com\/beacon",
   "auth":"GET",
   "method":"POST",
   "parameters":"[{\"key\":\"Authentication\",\"value\":\"23533TT3Y64F24\"}]"
}
```
## Update connector

	PUT https://api.bealder.com/v2/connector

### PUT Parameters

| Name    		| Type      | Require | Description              |
|---------------|-----------|---------|--------------------------|
| name	  		| String	|  true   | name of connector				 		 |
| url	  		| String	|  true   | url of webservice				 		 |
| method	  	| String	|  true   | method to send (POST, GET)				 |
| parameters  	| String	|  true   | Parameters to authenticate				 |
| auth	  		| String	|  true   | Send parameters method	(header, get)	 |


### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |



### Example

```bash
curl -X PUT https://api.bealder.com/v2/connector -H "content-Type:application/json" -H "x-bealder-key:example@bealder.com" -H "x-bealder-token:ec311746cf596d94cabea9f9d261eb3a"
-d '{  
   "id":2,
   "name":"My company CRM Bis",
   "url":"http:\/\/.api.mycompany.com\/beacon",
   "auth":"GET",
   "method":"POST",
   "parameters":"[{\"key\":\"Authentication\",\"value\":\"23533TT3Y64F24\"},
   {\"key\":\"Email\",\"value\":\"example@bealder.com\"}]"
}'
```

### Success Response

```json
{  
   "id":2,
   "name":"My company CRM Bis",
   "url":"http:\/\/.api.mycompany.com\/beacon",
   "auth":"GET",
   "method":"POST",
   "parameters":"[{\"key\":\"Authentication\",\"value\":\"23533TT3Y64F24\"},
   {\"key\":\"Email\",\"value\":\"example@bealder.com\"}]"
}
```

To get your token, go to [authentication](authentication.html).
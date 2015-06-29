---
current_menu: connector
---

# Connector

## get connector

	GET https://api.bealder.com/v2/connector

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


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

To get your token, go to [authentication](authentication.html).
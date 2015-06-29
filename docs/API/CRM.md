---
current_menu: crm
---

# CRM

## Get all devices

	GET https://api.bealder.com/v2/crm

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


## get one device

	GET https://api.bealder.com/v2/crm/{id}

### GET Parameters

| Name    	| Type      | Description                        |
|-----------|-----------|------------------------------------|
| id	  	| String	|  id device						 |

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


## Update one device

	PUT https://api.bealder.com/v2/crm/{id}

### GET Parameters

| Name    	| Type      | Description                        |
|-----------|-----------|------------------------------------|
| id	  	| String	|  id device						 |

### PUT Parameters

| Name    	| Type      | Description                        |
|-----------|-----------|------------------------------------|
| datas	  	| array		|  list of datas for this device	 |

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

To get your token, go to [authentication](authentication.html).
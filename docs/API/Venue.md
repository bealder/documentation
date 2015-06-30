

# Venue

## Create new venue

	POST https://api.bealder.com/v2/region

### POST Parameters

| Name    	| Type      | Require   | Description                        |
|-----------|-----------|-----------|------------------------------------|
| name	  	| String	|  true		|  Name of venue					 |
| address  	| String    |  true		|  Address 							 |
| active	| boolean	|  true		|  1 if venue is active	or 0		 |
| with  	| integer   |  			|  with (meter) 					 |
| height	| integer	|  			|  height (meter)					 |
| image		| String	|  			|  map of venues					 |

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

### Example

```bash
CURL -X POST https://api.bealder.com/v2/venue
 -H "content-Type:application/json"
 -H "x-bealder-key:example@bealder.com"
 -H "x-bealder-token:20f586ec4b244e00a81d00bca91b7d7f"
 -d '{  
   "name":"NewVenue",
   "address":"23 Av Albert Einstein 69100 Villeurbanne",
   "width":200,
   "height":200,
   "map":"https:\/\/img.bealder.com\/img\/\/259169-Selection_Niveau3_SET_2.PNG",
   "active":true
}'
```

## Edit venue

	PUT https://api.bealder.com/v2/region/{id}

### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |

### PUT Parameters

| Name    	| Type      | Require   | Description                        |
|-----------|-----------|-----------|------------------------------------|
| name	  	| String	|  true		|  Name of venue					 |
| address  	| String    |  true		|  Address 							 |
| active	| boolean	|  true		|  1 if venue is active	or 0		 |
| with  	| integer   |  			|  with (meter) 					 |
| height	| integer	|  			|  height (meter)					 |
| image		| String	|  			|  map of venues					 |

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


## Get all venues

	GET https://api.bealder.com/v2/region

###	HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


## Get one venue

	GET https://api.bealder.com/v2/region/{id}

### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |


### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


## Delete venue

	DELETE https://api.bealder.com/v2/region/{id}

###	HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


To get your token, go to [authentication](authentication.html).
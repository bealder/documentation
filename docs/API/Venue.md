

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
# Beacon

If you want to add a new beacon to your company, you must know the three following components of the beacon hardware which makes it unique :
	- uuid
	- major
	- minor

If you have no idea of how to get these, please contact us on our [website](www.bealder.com).

## Create new beacon

	POST https://api.bealder.com/v2/region/{id}/beacon

### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| venue ID			 |


### POST Parameters

| Name    			|  Require 	|  Description                       |
|-------------------|-----------|------------------------------------|
| name	  			|  true 	|   Beacon name						 		|
| uuid  			|  true 	|   Beacon UUID				 				|
| major	  			|  true 	|   Beacon major 					 		|
| minor  			|  true 	|   Beacon minor					 		|
| active	  		|  true 	|   if active, set 1, else 0		 		|
| proximity	  		|  true 	|   define default proximity to trigger (immediate, near, far)	    |
| x  				|   		|   Beacon horizontal axis on map	 		|
| y  				|   		|   Beacon vertical axis on map	 			|
| color  			|  		 	|   view color on map						|


### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


### Example 

```bash
curl -X POST https://api.bealder.com/v2/region/1/beacon
 -H "content-Type:application/json"
 -H "x-bealder-key:example@bealder.com"
 -H "x-bealder-token:20f586ec4b244e00a81d00bca91b7d7f"
 -d '{  
      "id":13,
      "name":"MiniBeacon 1.2",
      "uuid":"E2CE67A05-DFEB-48A2-B060-D0F5761096E0",
      "major":1,
      "minor":2,
      "x":294,
      "y":217,
      "proximity":"near",
      "color":"yellow",
      "active":true,
      "tags":[  
         {  
            "id":3,
            "name":"Fitness"
         },
         {  
            "id":4,
            "name":"Beauté"
         }
      ]
   }'
```

## Edit beacon

	PUT https://api.bealder.com/v2/region/{id}/beacon/{uid}

### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| Venue ID			 |
| uid	  			|  true 	| Beacon ID			 |


### PUT Parameters

| Name    			|  Require 	|  Description                       |
|-------------------|-----------|------------------------------------|
| name	  			|  true 	|   Beacon name						 		|
| uuid  			|  true 	|   Beacon UUID					 		|
| major	  			|  true 	|   Beacon major					 		|
| minor  			|  true 	|   Beacon minor					 		|
| color  			|  		 	|   view color on map				 		|
| active	  		|  true 	|   if active, set 1, else 0		 		|
| proximity	  		|  true 	|   define default proximity to trigger	    |


### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


## List Beacon

	GET https://api.bealder.com/v2/region/{id}/beacon

### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| Venue ID			 |


### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

## Delete beacon

	DELETE https://api.bealder.com/v2/region/{id}/beacon/{uid}


### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| Venue ID			 |
| uid	  			|  true 	| Beacon ID			 |


###	HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


To get your token, go to [authentication](authentication.html).
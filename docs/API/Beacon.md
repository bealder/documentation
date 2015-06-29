# Beacon

## Create new beacon

	POST https://api.bealder.com/v2/region/{id}/beacon

### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |


### POST Parameters

| Name    			|  Require 	|  Description                       |
|-------------------|-----------|------------------------------------|
| name	  			|  true 	|   Beacon name						 		|
| uuid  			|  true 	|   uuid of beacon					 		|
| major	  			|  true 	|   major of beacon					 		|
| minor  			|  true 	|   minor of beacon					 		|
| color  			|  		 	|   view color on map				 		|
| active	  		|  true 	|   if active, set 1, else 0		 		|
| proximity	  		|  true 	|   define default proximity to trigger	    |


### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


## Edit beacon

	PUT https://api.bealder.com/v2/region/{id}/beacon/{uid}

### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |
| uid	  			|  true 	| id of beacon			 |


### PUT Parameters

| Name    			|  Require 	|  Description                       |
|-------------------|-----------|------------------------------------|
| name	  			|  true 	|   Beacon name						 		|
| uuid  			|  true 	|   uuid of beacon					 		|
| major	  			|  true 	|   major of beacon					 		|
| minor  			|  true 	|   minor of beacon					 		|
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
| id	  			|  true 	| id of venue			 |


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
| id	  			|  true 	| id of venue			 |
| uid	  			|  true 	| id of beacon			 |


###	HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


To get your token, go to [authentication](authentication.html).
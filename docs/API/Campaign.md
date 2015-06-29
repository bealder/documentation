# Campaign

## Create new campaign

	POST https://api.bealder.com/v2/lieu/{id}/campaign

### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |


### POST Parameters

| Name    			|  Require 	|  Description                       |
|-------------------|-----------|------------------------------------|
| name	  			|  true 	|   Campaign name						 |
| push  			|  true 	|   Nofitication content		 	 	 |
| title	  			|  true 	|   Notificaiton title					 |
| template  		|  		 	|   Template (use wysiwyg Bealder)		 |
| url  				|  		 	|   a link		 						 |
| format	  		|  true 	|   choise between (template, url, html) |
| html	  			|  		 	|   source code html/css 	    		 |
| cache  			|  true	 	|   delay between 2 send campaign		 |
| start  			|  true	 	|   campaign start			 			 |
| end	  			|  true 	|   campaign end 						 |
| start_time 		|  true	 	|   start begin of day 	    		 	 |
| end_time 			|  true		|   stop end of day 	    		 	 |
| active 			|  true		|   active campaign with 1, else 0 	 	 |

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


## Get one campaign

	GET https://api.bealder.com/v2/lieu/{id}/campaign/{uid}

### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |
| uid	  			|  true 	| id of campaign		 |

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

## Edit one campaign

	PUT https://api.bealder.com/v2/lieu/{id}/campaign/{id}

### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |
| uid	  			|  true 	| id of campaign		 |


### PUT Parameters

| Name    			|  Require 	|  Description                       |
|-------------------|-----------|------------------------------------|
| name	  			|  true 	|   Campaign name						 |
| push  			|  true 	|   Nofitication content		 	 	 |
| title	  			|  true 	|   Notificaiton title					 |
| template  		|  		 	|   Template (use wysiwyg Bealder)		 |
| url  				|  		 	|   a link		 						 |
| format	  		|  true 	|   choise between (template, url, html) |
| html	  			|  		 	|   source code html/css 	    		 |
| cache  			|  true	 	|   delay between 2 send campaign		 |
| start  			|  true	 	|   campaign start			 			 |
| end	  			|  true 	|   campaign end 						 |
| start_time 		|  true	 	|   start begin of day 	    		 	 |
| end_time 			|  true		|   stop end of day 	    		 	 |
| active 			|  true		|   active campaign with 1, else 0 	 	 |

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

## List campaign

	GET https://api.bealder.com/v2/lieu/{id}/campaign

### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |


### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

## Delete campaign

	DELETE https://api.bealder.com/v2/lieu/{id}/campaign/{uid}


### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |
| uid	  			|  true 	| id of campaign		 |


###	HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


To get your token, go to [authentication](authentication.html).
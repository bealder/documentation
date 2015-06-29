# API Bealder

- [Authentication](#authentication)
- [Profile](#profile)
	- [Get profile](#get-profile)
	- [Edit profile](#edit-profile)
	- [Get applications](#get-applications)
- [CRM](#crm)
	- [List all devices](#list-all-devices)
	- [Get one device](#get-one-device)
	- [Update one device](#update-one-device)
- [Connector](#crm)
	- [Get connector information](#get-connector)
	- [Edit connector](#edit-connector)
- [Venue](#venue)
	- [List all venues](#list-all-venues)
	- [Create new venue](#create-new-venue)
	- [Get venue](#get-venue)
	- [Edit venue](#edit-venue)
	- [Delete venue](#delete-venue)
- [Beacon](#beacon)
	- [List all beacons](#list-all-beacons)
	- [Create new beacon](#create-new-beacon)
	- [Get beacon](#get-beacon)
	- [Edit beacon](#edit-beacon)
	- [Delete beacon](#delete-beacon)
- [Campaign](#campaign)
	- [List all campaigns](#list-all-campaigns)
	- [Create new campaign](#create-new-campaign)
	- [Get campaign](#get-campaign)
	- [Edit campaign](#edit-campaign)
	- [Delete campaign](#delete-campaign)






## Venue

### Create new venue

	POST https://api.bealder.com/v2/region

#### POST Parameters

| Name    	| Type      | Require   | Description                        |
|-----------|-----------|-----------|------------------------------------|
| name	  	| String	|  true		|  Name of venue					 |
| address  	| String    |  true		|  Address 							 |
| active	| boolean	|  true		|  1 if venue is active	or 0		 |
| with  	| integer   |  			|  with (meter) 					 |
| height	| integer	|  			|  height (meter)					 |
| image		| String	|  			|  map of venues					 |

#### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


### Edit venue

	PUT https://api.bealder.com/v2/region/{id}

#### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |

#### PUT Parameters

| Name    	| Type      | Require   | Description                        |
|-----------|-----------|-----------|------------------------------------|
| name	  	| String	|  true		|  Name of venue					 |
| address  	| String    |  true		|  Address 							 |
| active	| boolean	|  true		|  1 if venue is active	or 0		 |
| with  	| integer   |  			|  with (meter) 					 |
| height	| integer	|  			|  height (meter)					 |
| image		| String	|  			|  map of venues					 |

#### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


### Get all venues

	GET https://api.bealder.com/v2/region

####	HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


### Get one venue

	GET https://api.bealder.com/v2/region/{id}

#### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |


#### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


### Delete venue

	DELETE https://api.bealder.com/v2/region/{id}

####	HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


## Beacon

### Create new beacon

	POST https://api.bealder.com/v2/region/{id}/beacon

#### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |


#### POST Parameters

| Name    			|  Require 	|  Description                       |
|-------------------|-----------|------------------------------------|
| name	  			|  true 	|   Beacon name						 		|
| uuid  			|  true 	|   uuid of beacon					 		|
| major	  			|  true 	|   major of beacon					 		|
| minor  			|  true 	|   minor of beacon					 		|
| color  			|  		 	|   view color on map				 		|
| active	  		|  true 	|   if active, set 1, else 0		 		|
| proximity	  		|  true 	|   define default proximity to trigger	    |


#### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


### Edit beacon

	PUT https://api.bealder.com/v2/region/{id}/beacon/{uid}

#### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |
| uid	  			|  true 	| id of beacon			 |


#### PUT Parameters

| Name    			|  Require 	|  Description                       |
|-------------------|-----------|------------------------------------|
| name	  			|  true 	|   Beacon name						 		|
| uuid  			|  true 	|   uuid of beacon					 		|
| major	  			|  true 	|   major of beacon					 		|
| minor  			|  true 	|   minor of beacon					 		|
| color  			|  		 	|   view color on map				 		|
| active	  		|  true 	|   if active, set 1, else 0		 		|
| proximity	  		|  true 	|   define default proximity to trigger	    |


#### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


### List Beacon

	GET https://api.bealder.com/v2/region/{id}/beacon

#### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |


#### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

### Delete beacon

	DELETE https://api.bealder.com/v2/region/{id}/beacon/{uid}


#### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |
| uid	  			|  true 	| id of beacon			 |


####	HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

## Campaign

### Create new campaign

	POST https://api.bealder.com/v2/lieu/{id}/campaign

#### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |


#### POST Parameters

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

#### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


### Get one campaign

	GET https://api.bealder.com/v2/lieu/{id}/campaign/{uid}

#### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |
| uid	  			|  true 	| id of campaign		 |

#### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

### Edit one campaign

	PUT https://api.bealder.com/v2/lieu/{id}/campaign/{id}

#### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |
| uid	  			|  true 	| id of campaign		 |


#### PUT Parameters

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

#### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

### List campaign

	GET https://api.bealder.com/v2/lieu/{id}/campaign

#### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |


#### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

### Delete campaign

	DELETE https://api.bealder.com/v2/lieu/{id}/campaign/{uid}


#### GET Parameters

| Name    			|  Require 	|	Description          |
|-------------------|-----------|------------------------|
| id	  			|  true 	| id of venue			 |
| uid	  			|  true 	| id of campaign		 |


####	HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

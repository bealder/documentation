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
| title	  			|  true 	|   Notification title					 |
| template  		|  		 	|   Template (use wysiwyg Bealder)		 |
| url  				|  		 	|   a link for 'url' format		 						 |
| format	  		|  true 	|   choose between (template, url, html, connector) |
| html	  			|  		 	|   source code html/css for 'html' format 	    		 |
| cache  			|  true	 	|   delay between 2 send campaign		 |
| start   			|  true	 	|   campaign start			 			 |
| end	  			|  true 	|   campaign end 						 |
| start_time 		|  true	 	|   start begin of day 	    		 	 |
| end_time 			|  true		|   stop end of day 	    		 	 |
| active 			|  true		|   active campaign with 1, else 0 	 	 |
| monday 			|  true		|   Campaign sent on monday 	 	 |
| thuesday 			|  true		|   Campaign sent on thuesday 	 	 |
| wednesday 			|  true		|   Campaign sent on wednesday 	 	 |
| thursday 			|  true		|   Campaign sent on thursday 	 	 |
| friday 			|  true		|   Campaign sent on friday 	 	 |
| saturday 			|  true		|   Campaign sent on saturday 	 	 |
| sunday 			|  true		|   Campaign sent on sunday 	 	 |


For format='connector' choice, nothing else must be specified.
We will just use the one configured for your company

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

### Example 

```bash
curl -X POST https://api.bealder.com/v2/lieu/13/campaign
 -H "content-Type:application/json"
 -H "x-bealder-key:example@bealder.com"
 -H "x-bealder-token:20f586ec4b244e00a81d00bca91b7d7f"
 -d '{  
   "name":"Notification envoyé le jeudi",
   "hash":"62d6cad47a7d4eff4ea46794b9cd825d",
   "push":"Entre 11 et 19h",
   "title":"On est jeudi!",
   "format":"url",
   "start":"2015-03-05T00:00:00+0100",
   "end":"2020-01-01T00:00:00+0100",
   "monday":false,
   "url": "http://www.bealder.com",
   "tuesday":false,
   "wednesday":false,
   "thursday":true,
   "friday":false,
   "saturday":false,
   "sunday":false,
   "cache":"hour",
   "active":true,
   "start_time":"11:00",
   "end_time":"19:00",
   "beacons":[  
      {  
         "id":184,
         "name":"BEACON ESTIMOTE",
         "uuid":"B9407F30-F5F8-466E-AFF9-25556B57FE6D",
         "major":43417,
         "minor":32638,
         "x":436,
         "y":178,
         "proximity":"near",
         "color":"blue",
         "active":true,
         "tags":[  

         ]
      }
   ],
   "nfcs":[  

   ],
   "qrcodes":[  

   ],
   "tags":[  

   ]
}'	
```

### Success response

```json
{  
   "id":212,
   "name":"Notification envoyé le jeudi",
   "hash":"62d6cad47a7d4eff4ea46794b9cd825d",
   "push":"Entre 11 et 19h",
   "title":"On est jeudi!",
   "format":"url",
   "start":"2015-03-05T00:00:00+0100",
   "end":"2020-01-01T00:00:00+0100",
   "monday":false,
   "tuesday":false,
   "wednesday":false,
   "thursday":true,
   "friday":false,
   "saturday":false,
   "sunday":false,
   "url": "http://www.bealder.com",
   "cache":"hour",
   "active":true,
   "start_time":"11:00",
   "end_time":"19:00",
   "beacons":[  
      {  
         "id":184,
         "name":"BEACON ESTIMOTE",
         "uuid":"B9407F30-F5F8-466E-AFF9-25556B57FE6D",
         "major":43417,
         "minor":32638,
         "x":436,
         "y":178,
         "proximity":"near",
         "color":"blue",
         "active":true,
         "tags":[  

         ]
      }
   ],
   "nfcs":[  

   ],
   "qrcodes":[  

   ],
   "tags":[  

   ]
}
```

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

### Example 

```bash
curl -X GET https://api.bealder.com/v2/lieu/13/campaign/212
 -H "content-Type:application/json"
 -H "x-bealder-key:example@bealder.com"
 -H "x-bealder-token:20f586ec4b244e00a81d00bca91b7d7f"
```

### Success response

```json
{  
   "id":212,
   "name":"C'est jeudi, c'est jeudizza",
   "hash":"62d6cad47a7d4eff4ea46794b9cd825d",
   "push":"Viens choisir ta pizza ! Maintenant et avant 12h12 !",
   "title":"C'est jeudi, c'est jeudizza",
   "background":"#6cddd1",
   "color":"#ffffff",
   "format":"url",
   "start":"2015-03-05T00:00:00+0100",
   "end":"2020-01-01T00:00:00+0100",
   "monday":false,
   "tuesday":false,
   "wednesday":false,
   "thursday":true,
   "friday":false,
   "saturday":false,
   "sunday":false,
   "url": "http://pizza.dominos.fr/la-carte/nos-pizzas"
   "cache":"hour",
   "active":true,
   "start_time":"11:00",
   "end_time":"19:00",
   "beacons":[  
      {  
         "id":184,
         "name":"BEACON ESTIMOTE",
         "uuid":"B9407F30-F5F8-466E-AFF9-25556B57FE6D",
         "major":43417,
         "minor":32638,
         "x":436,
         "y":178,
         "proximity":"near",
         "color":"blue",
         "active":true,
         "tags":[  

         ]
      }
   ],
   "nfcs":[  

   ],
   "qrcodes":[  

   ],
   "tags":[  

   ]
}
```


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
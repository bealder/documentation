---
current_menu: crm
---

# CRM

In this section, you will get all informations concerning your users devices, beacon detection & push notification reception.

## Get all devices

	GET https://api.bealder.com/v2/crm

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

### Example 

```bash
curl -X GET https://api.bealder.com/v2/crm
 -H "content-Type:application/json"
 -H "x-bealder-key:example@bealder.com"
 -H "x-bealder-token:20f586ec4b244e00a81d00bca91b7d7f"
```

### Success response

```json
[  
   {  
      "nb_beacon":765,
      "nb_campaign":182,
      "id":882,
      "token_push":"3d9a63eff63d7328730a5fbb4eb64840eca922",
      "name":"iPhone OS",
      "version":"8.3",
      "model":"iPhone",
      "id_connector":1,
      "create_on":"2015-06-10T17:13:34+0200",
      "update_on":"2015-06-30T09:10:23+0200",
      "test":false
   },
   {  
      "nb_beacon":23,
      "nb_campaign":3,
      "id":917,
      "udid":"aabd28506b94df78",
      "name":"android",
      "version":"5.0.1",
      "model":"samsung SM-N910F",
      "create_on":"2015-06-18T18:10:58+0200",
      "update_on":"2015-06-29T17:57:37+0200",
      "test":false
   },
   {  
      "nb_beacon":139,
      "nb_campaign":78,
      "id":789,
      "udid":"24ceb7ae1a6175e2",
      "name":"android",
      "version":"4.3",
      "model":"samsung GT-I9300",
      "create_on":"2015-05-28T17:03:32+0200",
      "update_on":"2015-06-01T14:41:26+0200",
      "test":false
   }
]
```
 ### Response description

This request render a list of device with beacon & campaign relative informations

 + `nb_beacon` :  Number of Bealder's beacon detection by the device
 + `nb_campaign` : Number of push notification linked to a campaign reception by the device
 + `model` : "Phone model"
 + `name` : "OS type"
 + `version` : "OS version"
 + `test` : "Field that determines weither if the device is a test device or not. The important thing here is that test device are not included in stats. 
 This way, the event organizer or shop manager won't mislead stats results"

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

### Example 

```bash
curl -X GET https://api.bealder.com/v2/crm/917
 -H "content-Type:application/json"
 -H "x-bealder-key:example@bealder.com"
 -H "x-bealder-token:20f586ec4b244e00a81d00bca91b7d7f"
```

### Success response

```json
{  
   "device":[  
      {  
         "nb_beacon":23,
         "nb_campaign":3,
         "id":917,
         "udid":"aabd28506b94df78",
         "name":"android",
         "version":"5.0.1",
         "model":"samsung SM-N910F",
         "create_on":"2015-06-18T18:10:58+0200",
         "update_on":"2015-06-29T17:57:37+0200",
         "test":false
      }
   ],
   "auth":[  
      {  
         "id":11326,
         "create_on":"2015-06-18T18:11:00+0200",
         "ip":"192.000.00.00"
      },
      {  
         "id":11327,
         "create_on":"2015-06-18T18:11:20+0200",
         "ip":"192.000.00.00"
      },
      {  
         "id":11328,
         "create_on":"2015-06-18T18:14:43+0200",
         "ip":"192.000.00.00"
      }
   ],
   "beacon":[  
      {  
         "lieu":"Awelty",
         "lieu_id":208,
         "id":307064,
         "beacon":{  
            "id":329,
            "name":"aime",
            "uuid":"B9407F30-F788-4623-AFF9-25544B57FE6D",
            "major":33217,
            "minor":923081,
            "proximity":"near",
            "color":"blue",
            "active":true,
            "tags":[  
               {  
                  "id":3,
                  "name":"football"
               },
               {  
                  "id":15,
                  "name":"tennis"
               }
            ]
         },
         "status":"near",
         "create_on":"2015-06-18T18:10:58+0200",
         "ip":"192.000.00.00"
      }
   ]
}
```

 ### Response description

This request render a list of device with beacon & campaign relative informations

 + `device` :  Details on your user device, beacon detection & campaign reception on device 
 + `auth` : "Trace of user authentification on application"
 + `beacon` "Trace of device's beacon detection"

## Update one device

	PUT https://api.bealder.com/v2/crm/{id}

This method's main purpose is to edit device test attribute for testing devices. But you can also 

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

### Example

```bash
curl -X PUT https://api.bealder.com/v2/crm/917 
-H "content-Type:application/json" 
-H "x-bealder-key:kevin@bealder.com" 
-H "x-bealder-token:ea7c4b01fd135550497b4633328a5d65" 
-d '{  
   "device":[  
      {  
         "nb_beacon":23,
         "nb_campaign":3,
         "id":234,
         "udid":"aabd28506b94df78",
         "name":"android",
         "version":"5.0.1",
         "model":"samsung SM-N910F",
         "create_on":"2015-06-18T18:10:58+0200",
         "update_on":"2015-06-29T17:57:37+0200",
         "test":"true"
      }
   ],
   "auth":[  
      {  
         "id":11326,
         "create_on":"2015-06-18T18:11:00+0200",
         "ip":"192.000.00.00"
      },
      {  
         "id":11327,
         "create_on":"2015-06-18T18:11:20+0200",
         "ip":"192.000.00.00"
      },
      {  
         "id":11328,
         "create_on":"2015-06-18T18:14:43+0200",
         "ip":"192.000.00.00"
      }
   ],
   "beacon":[  
      {  
         "lieu":"Awelty",
         "lieu_id":208,
         "id":307064,
         "beacon":{  
            "id":329,
            "name":"aime",
            "uuid":"B9407F30-F788-4623-AFF9-25544B57FE6D",
            "major":33217,
            "minor":923081,
            "proximity":"near",
            "color":"blue",
            "active":true,
            "tags":[  
               {  
                  "id":3,
                  "name":"football"
               },
               {  
                  "id":15,
                  "name":"tennis"
               }
            ]
         },
         "status":"near",
         "create_on":"2015-06-18T18:10:58+0200",
         "ip":"192.000.00.00"
      }
   ]
}'
```


To get your token, go to [authentication](authentication.html).
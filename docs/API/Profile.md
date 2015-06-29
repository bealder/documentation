---
current_menu: profile
---

# Profile

## Get profile

	GET https://api.bealder.com/v2/profile

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


## Edit profile

	PUT https://api.bealder.com/v2/profile

### PUT Parameters

| Name    	| Type      | Description                        |
|-----------|-----------|------------------------------------|
| email	  	| String	|  Your email						 |
| name  	| String    |  Your name 						 |
| function	| String	|  Your function					 |

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |


## Get applications

	GET https://api.bealder.com/v2/profile/application

### HEADER Parameters

| Name    			|  Description                       |
|-------------------|------------------------------------|
| x-bealder-key	  	|  Your email						 |
| x-bealder-token  	|  Your token						 |

To get your token, go to [authentication](authentication.html).
# popguide
development guide for pop platform

# SYSTEM DESIGN
## INTERGRATION FLOW
## API Scheme and terms
There are two  kind of API, Rest API, Redirect API.
     REST API:       call by server side.
     REDIRECT API:    init by server side but redirect from browser. usually using Location or HTTP 302 Method. The API information.
![image](https://github.com/mmhuang/popguide/raw/master/assests/images/direct%20api%20sequence.png)
![image](https://github.com/mmhuang/popguide/raw/master/assests/images/redirect%20api%20sequence.png)

APP ID:  	generated by Platform side. Offline handling.
    APP KEY:       generated by Platform side. Offline handling

USER ID:      generated by platform from API, binding with app.
USER KEY:  generated by platform from API,


REQUEST CONTENT: base64(json_encode(request body))
                    Request body: { method:””, parameter1:””,parameter2:””}
                             Note:  value only allow string and float or Integer.
Empty string for null;

REQUEST TIMESTAMP: request would expired with in 15 min. Using Unix timestamp

    REQUEST HASH:  sha_256(timestamp+request content, key) the key would be api key or user key, depend on the method.


RESPON FORMAT: JSON
    result: integer number, like error code. 0 for success.
    msg: usually for error message or notice. 
    data:  respond content, 
    


# APIs
## backBinding


### Request

#### Request URL

UAT: https://a2u.dev.paravers.com/index.php?action=backBinding&requestbody=requestbody 
LIVE: https://association.asen2u.com/index.php?action=backBinding 

#### Url parameter
|No	|Parameter	|Description	|Length	| Example|
| - |:---------:| -----------:|------:|------:|
|1	|appid			 |-----------|------|------|
|2	|requestbody				|-----------|------|------|
|3	|requesthash				|-----------|------|------|
|4	|timestamp				|-----------|------|------|
					


### Respond
### Example

## frontBinding

### Request
### Respond
### Example

## getUserInfo

### Request
### Respond
### Example

## goto

### Request
### Respond
### Example



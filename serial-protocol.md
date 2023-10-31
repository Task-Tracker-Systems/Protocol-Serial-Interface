# Protocol v0.0.1

Client-Server communication

TDD = Task Tracker Device
App = Desktop Applikacion

- Server = TTD
- Client = App

## Limitations
- Strings MUST NOT have line breaks
- String parameter MUST have double-quotes
- Numeric parameters MUST NOT have quotes
- Numeric parameters MUST be integers
- Parameters CAN be sent in arbitrary order
- Strings MUST use ASCII characters only
- Protocol version MUST be semver 2.0.0

## see also

https://quicktype.io/

## "welcome message" from server

prints the response of "get protocol version"



## get protocol version
### Sending 

    info
    
### Receiving

`<string>` is s.th. like 1.2.3 

JSON:

    {
      "protocolVersion": <string>
    }

## list tasks

### Sending 

Client sends:

    list
    
Server responds:

### Receiving

JSON:

    {
      "tasks": [
        {
        "id": <number>,
        "name": <string>,
        "duration": <number>
        }
      ]
    }

JSON Schema:

```
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "Generated schema for Task Tracker Systems",
  "type": "object",
  "properties": {
    "tasks": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "number"
          },
          "name": {
            "type": "string"
          },
          "duration": {
            "type": "number"
          },
        },
        "required": [
          "id",
          "name",
          "duration"
        ]
      }
    }
  },
  "required": [
    "tasks"
  ]
}
``` 
    
    

## edit task


### Sending 

Client sends:

    edit --id <id> [--name "<new name>"] [--duration duration] 
    
Server responds:

### Receiving

JSON:

    {
      "task":
        {
        "id": <number>,
        "name": <string>,
        "duration": <number>
        }
    }

## create task 

### Sending 

Client sends:

    add --id <id> --name "<new name>" [--duration <duration>]
    
Server responds:

### Receiving

JSON:

    {
      "task":
        {
        "id": <number>,
        "name": <string>,
        "duration": <number>
        }
    }


## delete task

### Sending 

Client sends:

    delete --id <id>
    
Server responds:

### Receiving

JSON:

    {
      "task":
        {
        "id": <number>
        }
    }






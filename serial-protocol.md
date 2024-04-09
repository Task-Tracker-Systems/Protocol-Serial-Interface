# Protocol v0.1.0

Client-Server communication

TDD = Task Tracker Device  
App = Desktop Applikacion

- Server = TTD
- Client = App


## Limitations
- Strings MUST NOT have line breaks
- String parameter containing whitespace MUST have double-quotes
- Numeric parameters MUST be integers
- Parameters CAN be sent in arbitrary order
- Strings MUST use ASCII characters only


## "welcome message" from server

prints the response of "get protocol version": [version info][SCHEMA_VER]


## get protocol version

- Sending: `info`
- Receiving: [version info][SCHEMA_VER]


## list tasks

- Sending: `list`
- Receiving: [task list][SCHEMA_LIST]


## edit task

- Sending: `edit --id <id> [--name "<new name>"] [--duration duration]`
- Receiving: [task description][SCHEMA_TASK]


## create task

- Sending: `add --id <id> --name "<new name>" [--duration <duration>]`
- Receiving: [task description][SCHEMA_TASK]


## delete task

- Sending: `delete --id <id>`
- Receiving: [task id][SCHEMA_DEL]


[SCHEMA_DEL]: deleted-task-object.schema.json
[SCHEMA_VER]: protocol-version-object.schema.json
[SCHEMA_LIST]: task-list.schema.json
[SCHEMA_TASK]: task-object.schema.json


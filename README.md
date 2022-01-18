When any error occur for npm libraries, renovate bot abruptly stops and no PR is raised for other dependencies as well. 
To avoid this, we tried using "abortOnError: false" for "npm" hostType, but this seems to be not working. 
Still the renovate bot is stopping with the error message  - "External host error causing abort - skipping"

```
Relevant Logs:

17:45:45   WARN: Host error (repository=bprachi29/testRepo1)
17:45:45         "hostType": "npm",
17:45:45         "lookupName": "grunt-cachebuster",
17:45:45         "err": {
17:45:45           "name": "RequestError",
17:45:45           "code": "ECONNRESET",
17:45:45           "timings": {
17:45:45             "start": 1641989745619,
17:45:45             "socket": 1641989745619,
17:45:45             "lookup": 1641989745620,
17:45:45             "connect": 1641989745650,
17:45:45             "error": 1641989745678,
17:45:45             "phases": {"wait": 0, "dns": 1, "tcp": 30, "total": 59}
17:45:45           },
17:45:45           "message": "read ECONNRESET",
17:45:45           "stack": "RequestError: read ECONNRESET\n    at ClientRequest.<anonymous> (/usr/src/app/node_modules/got/dist/source/core/index.js:962:111)\n    at Object.onceWrapper (events.js:520:26)\n    at ClientRequest.emit (events.js:412:35)\n    at ClientRequest.emit (domain.js:475:12)\n    at ClientRequest.origin.emit (/usr/src/app/node_modules/@szmarczak/http-timer/dist/source/index.js:43:20)\n    at TLSSocket.socketErrorListener (_http_client.js:475:9)\n    at TLSSocket.emit (events.js:400:28)\n    at TLSSocket.emit (domain.js:475:12)\n    at emitErrorNT (internal/streams/destroy.js:106:8)\n    at emitErrorCloseNT (internal/streams/destroy.js:74:3)\n    at processTicksAndRejections (internal/process/task_queues.js:82:21)\n    at TLSWrap.onStreamRead (internal/stream_base_commons.js:209:20)",
17:45:45           "options": {
17:45:45             "headers": {
17:45:45               "user-agent": "RenovateBot/31.19.0 (https://github.com/renovatebot/renovate)",
17:45:45               "accept": "application/json",
17:45:45               "accept-encoding": "gzip, deflate, br"
17:45:45             },
17:45:45             "url": "https://registry.npmjs.org/grunt-cachebuster",
17:45:45             "hostType": "npm",
17:45:45             "username": "",
17:45:45             "password": "",
17:45:45             "method": "GET",
17:45:45             "http2": false
17:45:45           }
17:45:45         }
17:45:45   INFO: External host error causing abort - skipping (repository=bprachi29/testRepo1)

```

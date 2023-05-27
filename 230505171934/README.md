# Building A WebServer from scratch

* Difference between import http = require('http'); and import * as http from 'http';?

[Answers](https://stackoverflow.com/a/35739633/13916430)

You'll have to put this in your package.json,
it will allow to use import/export statements :

```json
"type": "module"
```


# cube.js dremio driver

> fork form official driver 

## Usage

* .env

```code
CUBEJS_DB_HOST=<>
CUBEJS_DB_PORT=<>
CUBEJS_DB_NAME=<>
CUBEJS_DB_USER=<>
CUBEJS_DB_PASS=<>
CUBEJS_WEB_SOCKETS=true
CUBEJS_DEV_MODE=true
CUBEJS_DB_TYPE=mydremio
```


* cube.js

```code
const {DremioDriver,DremioQuery} = require("@dalongrong/mydremio-driver")
module.exports = {
    dialectFactory: (dataSource) => {
        // need config  datasource  for multitenant env
        return DremioQuery
    },
    dbType: ({ dataSource } = {}) => {
        return "mydremio"
    },
    driverFactory: ({ dataSource } = {}) => {
        return new DremioDriver({})
    }
};
```
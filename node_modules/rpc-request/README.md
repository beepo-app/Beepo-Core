# rpc-request ![CI Status](https://github.com/vansergen/rpc-request/workflows/CI/badge.svg) [![Coverage Status](https://coveralls.io/repos/github/vansergen/rpc-request/badge.svg)](https://coveralls.io/github/vansergen/rpc-request) ![GitHub version](https://badge.fury.io/gh/vansergen%2Frpc-request.svg) ![Node version](https://img.shields.io/node/v/rpc-request) [![Known Vulnerabilities](https://snyk.io/test/github/vansergen/rpc-request/badge.svg)](https://snyk.io/test/github/vansergen/rpc-request) ![NPM license](https://img.shields.io/npm/l/rpc-request) ![npm downloads](https://img.shields.io/npm/dt/rpc-request) ![GitHub top language](https://img.shields.io/github/languages/top/vansergen/rpc-request)

`rpc-request` is a simple wrapper of the [`request-promise-native`](https://github.com/request/request-promise-native) library in a class.

## Installation

```bash
npm install rpc-request
```

## Usage

Please refer to the [`request` documentation](https://github.com/request/request#requestdefaultsoptions) for the full list of all supported options you can pass to the constructor.

```javascript
import { RPC } from "rpc-request";
class MyClass extends RPC {
  constructor() {
    super({ uri: "http://worldtimeapi.org/api/ip", json: true });
  }
}
const myClass = new MyClass();
myClass
  .get()
  .then((data) => console.log(data))
  .catch((error) => console.error(error));
```

- [`request`](https://github.com/request/request#requestoptions-callback)

```javascript
await rpc.request(options);
```

The following convenience methods correspond to HTTP request methods.

- `get`

```javascript
await rpc.get(options);
```

- `post`

```javascript
await rpc.post(options);
```

- `put`

```javascript
await rpc.put(options);
```

- `patch`

```javascript
await rpc.patch(options);
```

- `delete`

```javascript
await rpc.delete(options);
```

- `head`

```javascript
await rpc.head(options);
```

- `options`

```javascript
await rpc.options(options);
```

The following static methods are also available to manage cookies:

- [`cookie`](https://github.com/request/request/#requestcookie)

```javascript
// creates a new cookie.
const key = "key";
const value = "value";
const myCookie = RPC.cookie(key, value);
```

- [`jar`](https://github.com/request/request/#requestjar)

```javascript
// creates a new cookie jar.
const myJar = RPC.jar();
```

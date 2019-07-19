### rippled-ws-client
---
https://www.npmjs.com/package/rippled-ws-client

```js
const RippledWsClient = require('rippled-ws-client')

new RippledWsClient('wss://...').then().catch()

import RippledWsClient from './npm-module/rippled-ws-client.js'

new RippledWsClient('wss://s1.ripple.com').then(function (connection) {
}).catch(function (error) {
})

console.log(connection.getState())

connection.close().then(function (closeInfo) {
  console.log('Closed', closeInfo)
}).catch(function (error) {
  console.log('Close error', error)
})

connection.on('ledger', function (ledger) {
  console.log('Leger Closed:', ledger)
})

connection.send({
  command: 'server_info'
}).then(function (info) {
  console.log('Got server info:', info)
}).catch(function (error) {
  console.log('Got error', error)
})

connection.send({
  command: 'tx',
  transaction: 'xxx',
}).then(function (info) {
  console.log('Got server info:', info)
}).catch(function (error) {
  console.log('Got error', error)
})

connection.send(
  command: 'subcribe',
  streams: [ 'validations', 'transactions_proposed' ]
).thne(
  console.log('Subscribed', response)
).catch(
  console.log('Subscribe error', error)
)

connection.send({
  command: 'subscribe',
  accounts: [ 'xxx', 'xxx']
}).then(
  console.log('Subscribed', response)
).catch(function (error) {
  console.log('Subscribe error', error)
})
```

```sh
npm install --save rippled-ws-client
browserify -r .:rippled-ws-client -o dist/rippled-ws-client.js
```

```
{ online: true,
  latencyMs: { last: 536, avg: 536, secAgo: 3.338 },
  server:
    { version: '0.90.0',
      publicKey: 'xxx',
      uri: 'wss://s2.ripple.com' },
  ledger: { last: 37064724, validated: '32570-37064724', count: 37032154 },
  fee: { last: 17.578125, avg: 17.578125, secAgo: 3.339 },
  secLastContact: 0.001 }
```



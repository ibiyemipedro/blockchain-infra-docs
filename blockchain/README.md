## How to check an archival node

---

The approach is : for EVM chains, you usually request data from a really old block

POA XDAI archival check:

- request example:

`curl 'http://poa-xdai.localhost:3000/v1/60676c9f7cbbfe002f0b9cbe' -H 'content-type: application/json' --data '{"method":"eth_getBalance","params":["0x02DAEF2227295c34DA992521AEb76cC28c9cAd3a", "0x1"],"id":1,"jsonrpc":"2.0"}'`

- failure response example:

`[{"error":{"code":-32000,"message":"This request is not supported because your node is running with state pruning. Run with --pruning=archive."},"id":1,"jsonrpc":"2.0"}]`

---

### FUSE archival check

- request example:

`curl 'http://fuse-mainnet.localhost:3000/v1/60676c9f7cbbfe002f0b9cbe' -H 'content-type: application/json' --data '{"method":"eth_getBalance","params":["0x02DAEF2227295c34DA992521AEb76cC28c9cAd3a", "0x1"],"id":1,"jsonrpc":"2.0"}'`

- failure response example:

`[{"error":{"code":-32000,"message":"This request is not supported because your node is running with state pruning. Run with --pruning=archive."},"id":1,"jsonrpc":"2.0"}]`

---

### Ethereum archival check:

- request example:

` curl 'http://eth-mainnet.localhost:3000/v1/60676c9f7cbbfe002f0b9cbe' -H 'content-type: application/json' --data '{"method":"eth_getBalance","params":["0x02DAEF2227295c34DA992521AEb76cC28c9cAd3a", "0x1"],"id":1,"jsonrpc":"2.0"}'`

- failure response example:

`[{"error":{"code":-32000,"message":"missing trie node d67e4d450343046425ae4271474353857ab860dbc0a1dde64b41b5cd3a532bf3 (path )"},"id":1,"jsonrpc":"2.0"}]`

---

### BSC archival check:

- request example:

`curl 'http://bsc-mainnet.localhost:3000/v1/60676c9f7cbbfe002f0b9cbe' -H 'content-type: application/json' --data '{"method":"eth_getBalance","params":["0x02DAEF2227295c34DA992521AEb76cC28c9cAd3a", "0x1"],"id":1,"jsonrpc":"2.0"}'`

- failure response example:

`{"jsonrpc":"2.0","id":1,"error":{"code":-32000,"message":"missing trie node 1db428ea79cb2e8cc233ae7f4db7c3567adfcb699af668a9f583fdae98e95588 (path )"}}%'`

---

### NEAR block height check:

`curl -X POST --data '{ "jsonrpc": "2.0", "id": "dontcare", "method": "status", "params": [] }' -H 'content-type:application/json;' http://near:6ChMDr507RK7mWoMse54@near-altruist.us-east.thunderstake.io`

### Avalanche archival check:

Possibly the first block on avax : 0x56ce38b18e185b3574b8d6e620029449309707c31663236245d5d53f6b4e8549

- request example:

`curl -X POST --data '{"method":"eth_getBalance","params":["0x02DAEF2227295c34DA992521AEb76cC28c9cAd3a", "0x1"],"id":1,"jsonrpc":"2.0"}' -H 'content-type:application/json;' 127.0.0.1:9650/ext/bc/C/rpc`

- failure response example:

`{"jsonrpc":"2.0","id":1,"error":{"code":-32000,"message":"missing trie node 2a545a17d06ece9d68bbc3eed9c5386765e01bb569580993fd78b9c947b26d99 (path )"}}`

---

- sample curl request:

`curl -X POST --data '{ "jsonrpc":"2.0", "id" :1, "method" :"platform.getBlockchains", "params" :{} }' -H 'content-type:application/json;' 127.0.0.1:9650/ext/P`

{ "jsonrpc": "2.0", "id": "dontcare", "method": "status", "params": [] }

`curl 'https://optimism-mainnet.gateway.pokt.network/v1/lb/62a249fe123e6f00394af5c1' -H 'content-type: application/json' --data '{"method":"eth_getBalance","params":["0x02DAEF2227295c34DA992521AEb76cC28c9cAd3a", "0x1"],"id":1,"jsonrpc":"2.0"}'`

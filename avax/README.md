### Check if avax node is healthy

`curl -X POST --data '{ "jsonrpc":"2.0", "id" :1, "method" :"platform.getBlockchains", "params" :{} }' -H 'content-type:application/json;' 127.0.0.1:9650/ext/P`

If it returns true it means the chain is up and in sync 

### Check if avax bootstrapped

request:

`curl -X POST --data '{ "jsonrpc":"2.0", "id" :1, "method" :"info.isBootstrapped","params": { "chain":"X" } }' -H 'content-type:application/json;' 127.0.0.1:9650/ext/info `

response: 

`{
    "jsonrpc": "2.0",
    "result": {
        "isBootstrapped": true
    },
    "id": 1
}`
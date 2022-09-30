# SpacesVM Postman Collection

Postman collection for the [SpacesVM](https://github.com/ava-labs/spacesvm).

## Installation

1. Download [Postman](https://postman.com)
1. Import SpacesVM Postman Collection. Import -> Upload Files -> `SpacesVM.postman_collection.json`
1. Import the Example SpacesVM Postman Environment. Settings -> Import -> Choose Files -> `Example_SpacesVM_Environment.postman_environment.json`
1. Call any SpacesVM RPC endpoint

## Contributing

If you're able to help improve the SpacesVM Postman Collection in any way, first create a feature branch by branching off of `main`, next make the improvements on your feature branch and lastly create a [pull request](https://github.com/ava-labs/spacesvm-postman-collection/pulls) to merge your work back in to `main`.

## RPC Calls

### ping

#### Request

```zsh
curl --location --request POST 'http://localhost:9650/ext/bc/y3ujdFWFofgbTtmXAxQxf5NfHYQU3qCfupjdV2vcLJa15tV93/public' \
--header 'Content-Type: application/json' \
--data-raw '{
  "jsonrpc": "2.0",
  "method": "spacesvm.ping",
  "params":{},
  "id": 1
}'
```

#### Response

```zsh
{
    "jsonrpc": "2.0",
    "result": {
        "success": true
    },
    "id": 1
}
```

### network

#### Request

```zsh
curl --location --request POST 'http://localhost:9650/ext/bc/y3ujdFWFofgbTtmXAxQxf5NfHYQU3qCfupjdV2vcLJa15tV93/public' \
--header 'Content-Type: application/json' \
--data-raw '{
  "jsonrpc": "2.0",
  "method": "spacesvm.network",
  "params":{},
  "id": 1
}'
```

#### Response

```zsh
{
    "jsonrpc": "2.0",
    "result": {
        "networkId": 1337,
        "subnetId": "2RfXmXFuo8LoVyQ4YSkvBMjroQER9ZVi55j1dkLNqsNt9fFh9r",
        "chainId": "y3ujdFWFofgbTtmXAxQxf5NfHYQU3qCfupjdV2vcLJa15tV93"
    },
    "id": 1
}
```

### genesis

#### Request

```zsh
curl --location --request POST 'http://localhost:9650/ext/bc/y3ujdFWFofgbTtmXAxQxf5NfHYQU3qCfupjdV2vcLJa15tV93/public' \
--header 'Content-Type: application/json' \
--data-raw '{
  "jsonrpc": "2.0",
  "method": "spacesvm.genesis",
  "params":{},
  "id": 1
}'
```

#### Response

```zsh
{
    "jsonrpc": "2.0",
    "result": {
        "genesis": {
            "magic": 1,
            "baseTxUnits": 1,
            "valueUnitSize": 1024,
            "maxValueSize": 204800,
            "valueExpiryDiscount": 10,
            "claimLoadMultiplier": 5,
            "minClaimFee": 100,
            "spaceDesirabilityMultiplier": 5,
            "spaceRenewalDiscount": 10,
            "claimReward": 2654208000,
            "claimExpiryUnits": 100,
            "lotteryRewardMultipler": 50,
            "minPrice": 1,
            "lookbackWindow": 60,
            "targetBlockRate": 1,
            "targetBlockSize": 225,
            "maxBlockSize": 246,
            "blockCostEnabled": true,
            "customAllocation": [
                {
                    "address": "0x8db97c7cece249c2b98bdc0226cc4c2a57bf52fc",
                    "balance": 1000000
                }
            ],
            "airdropHash": "",
            "airdropUnits": 0
        }
    },
    "id": 1
}
```

### lastAccepted

#### Request

```zsh
curl --location --request POST 'http://localhost:9650/ext/bc/y3ujdFWFofgbTtmXAxQxf5NfHYQU3qCfupjdV2vcLJa15tV93/public' \
--header 'Content-Type: application/json' \
--data-raw '{
  "jsonrpc": "2.0",
  "method": "spacesvm.lastAccepted",
  "params":{},
  "id": 1
}'
```

#### Response

```zsh
{
    "jsonrpc": "2.0",
    "result": {
        "height": 0,
        "blockId": "VdytaLTtNqJaXvfQvVGYoHvtyXzgrJUoUiPUkCySXceYUWES7"
    },
    "id": 1
}
```

### claimed

#### Request

```zsh
curl --location --request POST 'http://localhost:9650/ext/bc/y3ujdFWFofgbTtmXAxQxf5NfHYQU3qCfupjdV2vcLJa15tV93/public' \
--header 'Content-Type: application/json' \
--data-raw '{
  "jsonrpc": "2.0",
  "method": "spacesvm.claimed",
  "params":{
    "space":"gabriel"
  },
  "id": 1
}'
```

#### Response

```zsh
{
    "jsonrpc": "2.0",
    "result": {
        "claimed": false
    },
    "id": 1
}
```

### info

#### Request

```zsh
curl --location --request POST 'http://localhost:9650/ext/bc/y3ujdFWFofgbTtmXAxQxf5NfHYQU3qCfupjdV2vcLJa15tV93/public' \
--header 'Content-Type: application/json' \
--data-raw '{
  "jsonrpc": "2.0",
  "method": "spacesvm.info",
  "params":{
    "space": "gabriel"
  },
  "id": 1
}'
```

#### Response

```zsh
{
    "jsonrpc": "2.0",
    "error": {
        "code": -32000,
        "message": "space missing",
        "data": null
    },
    "id": 1
}
```

### recentActivity

#### Request

```zsh
curl --location --request POST 'http://localhost:9650/ext/bc/y3ujdFWFofgbTtmXAxQxf5NfHYQU3qCfupjdV2vcLJa15tV93/public' \
--header 'Content-Type: application/json' \
--data-raw '{
  "jsonrpc": "2.0",
  "method": "spacesvm.recentActivity",
  "params":{},
  "id": 1
}'
```

#### Response

```zsh
{
    "jsonrpc": "2.0",
    "result": {
        "activity": []
    },
    "id": 1
}
```

### suggestedRawFee

#### Request

```zsh
curl --location --request POST 'http://localhost:9650/ext/bc/y3ujdFWFofgbTtmXAxQxf5NfHYQU3qCfupjdV2vcLJa15tV93/public' \
--header 'Content-Type: application/json' \
--data-raw '{
  "jsonrpc": "2.0",
  "method": "spacesvm.suggestedRawFee",
  "params":{},
  "id": 1
}'
```

#### Response

```zsh
{
    "jsonrpc": "2.0",
    "result": {
        "price": 1,
        "cost": 0
    },
    "id": 1
}
```

### suggestedFee

#### Request

```zsh
curl --location --request POST 'http://localhost:9650/ext/bc/y3ujdFWFofgbTtmXAxQxf5NfHYQU3qCfupjdV2vcLJa15tV93/public' \
--header 'Content-Type: application/json' \
--data-raw '{
  "jsonrpc": "2.0",
  "method": "spacesvm.suggestedFee",
  "params":{
    "input":{
      "type":"claim", 
      "space":"gabriel"
    }
  },
  "id": 1
}'
```

#### Response

```zsh
{
    "jsonrpc": "2.0",
    "result": {
        "typedData": {
            "types": {
                "EIP712Domain": [
                    {
                        "name": "name",
                        "type": "string"
                    },
                    {
                        "name": "magic",
                        "type": "uint64"
                    }
                ],
                "claim": [
                    {
                        "name": "space",
                        "type": "string"
                    },
                    {
                        "name": "price",
                        "type": "uint64"
                    },
                    {
                        "name": "blockID",
                        "type": "string"
                    }
                ]
            },
            "primaryType": "claim",
            "domain": {
                "name": "Spaces",
                "magic": "1"
            },
            "message": {
                "blockID": "VdytaLTtNqJaXvfQvVGYoHvtyXzgrJUoUiPUkCySXceYUWES7",
                "price": "1",
                "space": "gabriel"
            }
        },
        "totalCost": 1250
    },
    "id": 1
}
```

### owned

#### Request

```zsh
curl --location --request POST 'http://localhost:9650/ext/bc/y3ujdFWFofgbTtmXAxQxf5NfHYQU3qCfupjdV2vcLJa15tV93/public' \
--header 'Content-Type: application/json' \
--data-raw '{
  "jsonrpc": "2.0",
  "method": "spacesvm.owned",
  "params":{
    "address": "0x8db97c7cece249c2b98bdc0226cc4c2a57bf52fc"
  },
  "id": 1
}'
```

#### Response

```zsh
{
    "jsonrpc": "2.0",
    "result": {
        "spaces": []
    },
    "id": 1
}
```

### balance

#### Request

```zsh
curl --location --request POST 'http://localhost:9650/ext/bc/y3ujdFWFofgbTtmXAxQxf5NfHYQU3qCfupjdV2vcLJa15tV93/public' \
--header 'Content-Type: application/json' \
--data-raw '{
  "jsonrpc": "2.0",
  "method": "spacesvm.balance",
  "params":{
    "address": "0x8db97c7cece249c2b98bdc0226cc4c2a57bf52fc"
  },
  "id": 1
}'
```

#### Response

```zsh
{
    "jsonrpc": "2.0",
    "result": {
        "balance": 1000000
    },
    "id": 1
}
```

### issueTx

#### Request

```zsh
curl --location --request POST 'http://localhost:9650/ext/bc/y3ujdFWFofgbTtmXAxQxf5NfHYQU3qCfupjdV2vcLJa15tV93/public' \
--header 'Content-Type: application/json' \
--data-raw '{
  "jsonrpc": "2.0",
  "method": "spacesvm.issueTx",
  "params":{
    "typedData":{
  "types": {
    "EIP712Domain": [
      {
        "name": "name",
        "type": "string"
      },
      {
        "name": "magic",
        "type": "uint64"
      }
    ],
    "claim": [
      {
        "name": "space",
        "type": "string"
      },
      {
        "name": "price",
        "type": "uint64"
      },
      {
        "name": "blockID",
        "type": "string"
      }
    ]
  },
  "primaryType": "claim",
  "domain": {
    "name": "Spaces",
    "magic": "1"
  },
  "message": {
    "blockID": "VdytaLTtNqJaXvfQvVGYoHvtyXzgrJUoUiPUkCySXceYUWES7",
    "price": "1",
    "space": "gabriel"
  }
},
    "signature": "0x83e014ab907058463dddce9e35858152353ae507cc88f4548f5deefa2ff2f3511f7d2c8b225492e71267c4ce4d61eee7ce2aefd789190d9b1e78f6ad9a369c7d1c"
  },
  "id": 1
}'
```

#### Response

```zsh
{
    "jsonrpc": "2.0",
    "error": {
        "code": -32000,
        "message": "invalid balance: bal=0, addr=0xC7cAc8aD145736E85164387441762d85b50f8555, add=false, prev=0, change=1250",
        "data": null
    },
    "id": 1
}
```

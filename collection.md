# deploy
### POST /v3/drc20/new
```shell
curl --location --request POST 'curl --location '127.0.0.1:1087/v3/drc20/new' \
--header 'Content-Type: application/json' \
--data '{"p":"drc-20","rate_fee":"214745466","receive_address":"DFuiFPeur2G9wEFr9vZsiLEtck9kxzzf5Y","lim":"1000000000000","max":"100000000000000","tick":"LITEYS","op":"deploy"}'
```

### Description of handling fee
```shell
The handling fee needs to be charged in 3 parts
1. 100 transaction service fee, fixed charge
2. Flat fee of 0.0001 inscription
3. Doge transaction fee for the inscription (calculated by multiplying the transaction size by rate_fee, the size is usually 350 - 400 bytes)
```


# mint
### POST /v3/drc20/new
```shell
curl --location --request POST 'curl --location '127.0.0.1:1087/v3/drc20/new' \
--header 'Content-Type: application/json' \
--data '{"p":"drc-20","rate_fee":"214745466","receive_address":"DFuiFPeur2G9wEFr9vZsiLEtck9kxzzf5Y","amt":"350000000000","repeat":14,"tick":"IDOL","op":"mint"}'
```
### Description of handling fee
```shell
The handling fee needs to be charged in 3 parts
1. 0.5 transaction service fee, fixed charge
2. Flat fee of 0.0001 inscription
3. Doge transaction fee for the inscription (calculated by multiplying the transaction size by rate_fee, the size is usually 350 - 400 bytes)
```

# transfer
### POST /v3/drc20/new
```shell
curl --location --request POST 'curl --location '127.0.0.1:1087/v3/drc20/new' \
--header 'Content-Type: application/json' \
--data '{"amt":"10000100000000","op":"transfer","p":"drc-20","rate_fee":"99058105","receive_address":"DFuiFPeur2G9wEFr9vZsiLEtck9kxzzf5Y","tick":"DWAR","to_address":"DDdcQ6ZBDDHiyzENTyawPTxfjHDqaLgYaX"}'
```

### Parameter Description
```shell
p: default
op: default
tick: token name
max: total amount of tokens
lim: the highest token minting time
receive_address: the address of the originator
rate_fee: transaction fee rate (elon per kbyte)
```

### Interface returns
```shell
{
     "code": 200,
     "msg": "success",
     "data": {
         "create_date": 1686986020,
         "fee_address": "ACVFwT9QnXtUyRiuKpDiso4xLFRnfcy8Kf",
         "order_id": "73b37bab-dd27-41ce-a4c0-30db353e1c2e"
     },
     "total": 0
}
```
### Parameter Description
```shell
order_id: order id
fee_address: transfer fee address
create_date: order creation time
```
# swap
### POST /v3/swap/new
```shell
curl --location --request POST 'curl --location '127.0.0.1:1087/v3/swap/new' \
--header 'Content-Type: application/json' \
--data '{"amt0":"17134898","amt1":"54713806","holder_address":"DEMZQAJjdNMM9M3Sk7LAmtPdk8me6SZUm1","liquidityProviderFee":"514046.94","op":"swap","p":"pair-v1","priceImpact":"0.00","swapRecive":"0","tick0":"WOW","tick1":"UNIX","amt1_min":"0"}'
```
### Parameter Description
```shell
p: pair-v1
op: swap
tick: token name
amt: the amount of add or remove drc-20
receive_address: the address of the originator
liquidityProviderFee: amt0 && tick0 ? new BigNumber(amt0).times(0.03).toString() : 0
```
### Interface returns
```shell
{
    "code":200,
    "msg":"success",
    "data":{
        "fee_address":"AEuuCTwK9eEXpy6iobW9rPiJJhYrZPj2B7",
        "order_id":"8602e2e0-214a-46a0-a80d-b9ff37438b56"
    },
    "total":0
}
```
### Parameter Description
```shell
order_id: order id
fee_address: transfer fee address
```

# Sign
### POST https://utxo.unielon.com/utxo
```shell
curl --location --request POST 'curl --location '127.0.0.1:1087/utxo' \
--header 'Content-Type: multipart/form-data' \
--data-raw $'------WebKitFormBoundaryDa2R7Vdj0dK8nbvc\r\nContent-Disposition: form-data; name="address"\r\n\r\nDBQwvSkNeEVKt5vHSsVtAgSRG5WhPMVDSQ\r\n------WebKitFormBoundaryDa2R7Vdj0dK8nbvc\r\nContent-Disposition: form-data; name="amount"\r\n\r\n101.23211645\r\n------WebKitFormBoundaryDa2R7Vdj0dK8nbvc\r\nContent-Disposition: form-data; name="count"\r\n\r\n500\r\n------WebKitFormBoundaryDa2R7Vdj0dK8nbvc--\r\n'
```
### Parameter Description
```shell
address: wallet address
amount: required number of doge
count: number of requests
```
var privateKey = new bitcore.PrivateKey('L1uyy5qTuGrVXrmrsvHWHgVzW9kKdrp27wBC7Vs6nZDTF2BRUVwy');
var utxo = {
  "txId" : "115e8f72f39fad874cfab0deed11a80f24f967a84079fb56ddf53ea02e308986",
  "outputIndex" : 0,
  "address" : "17XBj6iFEsf8kzDMGQk5ghZipxX49VXuaV",
  "script" : "76a91447862fe165e6121af80d5dde1ecb478ed170565b88ac",
  "satoshis" : 50000
};
```shell
import bitcore from 'bitcore-lib'
var privateKey = new bitcore.PrivateKey('L1uyy5qTuGrVXrmrsvHWHgVzW9kKdrp27wBC7Vs6nZDTF2BRUVwy');
var utxo = {
  "txId" : "115e8f72f39fad874cfab0deed11a80f24f967a84079fb56ddf53ea02e308986",
  "outputIndex" : 0,
  "address" : "17XBj6iFEsf8kzDMGQk5ghZipxX49VXuaV",
  "script" : "76a91447862fe165e6121af80d5dde1ecb478ed170565b88ac",
  "satoshis" : 50000
};

var transaction = new bitcore.Transaction()
  .from(utxo)
  .to(fee_address, toAmount)
  .fee(gasfee)
  .change(address)
  .sign(privateKey)
```
### Parameter Description
```shell
fee_address: fee_address returned by the interface
toAmount: required number of doge
address: change address
```
### broadcast

https://unielon.com/v3/tx/broadcast
### POST /v3/tx/broadcast
```shell
curl --location --request POST 'curl --location '127.0.0.1:1087/v3/tx/broadcast' \
--header 'Content-Type: application/json' \
--data '{"tx_hex":"010000000159611359b88c9a876d7b5b1ea2e793ad6a47a7064245a42ffddcb00aeb3391d1000000006a47304402206dc09fb627583572b82860f5273505e0ee8f6a689018d41f18761a320a03176202206b6baa1e75a662a1ab91c9584d6fc62c1db457fb55a8a97062c9f0d06414c9a0012103de9b39a56ca16f07af5c6e5aeac4d5d09b87b2e4e75ee5c7355dfe24bf6928a4ffffffff0100e1f505000000001976a91435ddbb6e5e46e6cfec23857d4e03f41e0e4170ee88ac00000000"}'
```
### Interface returns
```shell
{
    "code":200,
    "msg":"success",
    "data":{
        "tx_hash":"ee914a99e78176e8237f92619e0307a0026a45a6b8e7d1e097309e696af118aa"
    }
}
```
### Parameter Description
```shell
tx_hash: Transaction hash
```

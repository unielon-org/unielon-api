Transfer interface

```jsx
curl --location 'https://unielon.com/v3/drc20/new' \
--header 'Content-Type: application/json' \
--data '{"p":"drc-20","op":"transfer","tick":"VAN", "amt": "10000", "receive_address":"DNG7tJ8LPmuk3J8568m5yypWbHX9pBvvTi", "to_address" :"DJvVkiu8foZMMUBMoHWE1V8gYGBJitDtRW", "rate_fee": "100000000"}'

-- Parameter Description

p: default
op: default
tick: token name
amt: transfer amount
receive_address: the address of the originator
to_address: the recipient's address
rate_fee: transaction fee rate (elon per kbyte)

-- Interface returns
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

-- Parameter Description

order_id: order id
fee_address: transfer fee address
create_date: order creation time

-- Description of handling fee

The handling fee needs to be charged in 3 parts
1. 0.01 transaction service fee, fixed charge
2. Flat fee of 0.001 inscription
3. Doge transaction fee for the inscription (calculated by multiplying the transaction size by rate_fee, the size is usually 350 - 400 bytes)

```

## Order Tracking

```jsx
curl --location 'https://unielon.com/v3/orders/id' \
--data '{"order_id":"8a70718b-d66b-438e-8ae1-a8bdfddf3caf"}'

---- Parameter Description
order_id: order id

---- Return parameter description

{
     "code": 200,
     "msg": "success",
     "data": {
         "order_id": "8a70718b-d66b-438e-8ae1-a8bdfddf3caf",
         "p": "drc-20",
         "op": "transfer",
         "tick": "BONE",
         "amt": 1800,
         "max": 0,
         "lim": 0,
         "dec": 0,
         "burn": "",
         "func": "",
         "rate_fee": 86041533,
         "repeat": 1,
         "fee_tx_hash": "98d09538dca5fbab4cb34f072ff80b762f0be3e731b357d7cf115f46c7eb5a2f",
         "drc20_tx_hash": "d708704865159e5272718835945e0ded2fc4209d75403756fdd5e018c3bee867",
         "block_hash": "bd35161791d8e69329f5acb6a48fe6f610a750a97ed40607af248c5228c9e616",
         "block_confirmations": 2,
         "receive_address": "DKJZsxQ49xwewPyphaqW4fe6XG8LBqJFNe",
         "to_address": "DDAWHWv93iVpqjh1D9QTkgJUzYyka4JKGu",
         "fee_address": "ABQRWERBiYzQW2vUFbwHW7FN9dJJdFSoX7",
         "order_status": 0,
         "create_date": 1687165358
     },
     "total": 0
}

p, op, tick, amt, max, lim, dec, burn, func: all are inscription information

rate_fee: transaction fee rate (elon per kbyte)
repeat: number of times (for mint)
fee_tx_hash: Whether to receive the transaction fee transfer, if there is information, it means to get it
drc20_tx_hash: inscribed transaction
block_hash: the block information of the inscription transaction
block_confirmations: number of block confirmations
receive_address: the address of the originator
to_address: the recipient's address
fee_address: Receive fee address
order_status: For Mint, depoly is valid
create_date: creation time

```



## Order Tracking By Hash

```jsx
curl --location 'https://unielon.com/v3/orders/hash' \
--data '{"hash": "f5230c3dabdd594603acf5d957bab237b71a81d5093c803a96bba682fb85f7eb"}'

---- Return parameter description

{
    "code": 200,
    "msg": "success",
    "data": {
        "order_id": "cfef1cb8-228e-4d78-8db0-ed251dffaa14",
        "p": "drc-20",
        "op": "transfer",
        "tick": "DWAR",
        "amt": 6000000,
        "max": 0,
        "lim": 0,
        "dec": 0,
        "burn": "",
        "func": "",
        "rate_fee": null,
        "repeat": 1,
        "fee_tx_hash": "",
        "drc20_tx_hash": "f5230c3dabdd594603acf5d957bab237b71a81d5093c803a96bba682fb85f7eb",
        "block_hash": "4855c394e2b8bec7b84982338b65004b843fac59d7f58a3208caccf422855072",
        "block_confirmations": 0,
        "receive_address": "D666DYyVmVAg1sUnacmJGtYHKs41x1oAXE",
        "to_address": "DQ7thPBoM4qYmxsRGbdxEsJdt6Y3u3vbAU",
        "fee_address": "",
        "order_status": 0,
        "create_date": 1689122878
    },
    "total": 0
}

p, op, tick, amt, max, lim, dec, burn, func: all are inscription information

rate_fee: transaction fee rate (elon per kbyte)
repeat: number of times (for mint)
fee_tx_hash: Whether to receive the transaction fee transfer, if there is information, it means to get it
drc20_tx_hash: inscribed transaction
block_hash: the block information of the inscription transaction
block_confirmations: number of block confirmations
receive_address: the address of the originator
to_address: the recipient's address
fee_address: Receive fee address
order_status: For Mint, depoly is valid
create_date: creation time

```






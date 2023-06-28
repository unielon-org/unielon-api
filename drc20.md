## Query the brief information of drc20 tokens

```jsx

curl --location 'https://unielon.com/v3/drc20/all' \
--header 'Content-Type: application/json' \
--data '{"limit": 10, "offset":0}'

returned messages
{
     "code": 200,
     "msg": "success",
     "data": [
         {
             "tick": "MILK",
             "mint_amt": 2250000,
             "max_amt": 21000000,
             "dec": 0,
             "lim": 15000,
             "holders": 5,
             "transactions": 5,
             "deploy_time": 1687902658,
             "last_mint_time": null,
             "deploy_by": "",
             "inscription": "0640a31752f73f53bd542667d2d3abdc404388d4a3eb4b27087130d6ec7094f9"
         }
     ],
     "total": 976
}
```

## Query the detailed information of a single drc20

```jsx

curl --location 'https://unielon.com/v3/drc20/tick' \
--header 'Content-Type: application/json' \
--data '{"tick":"MEME"}'

return parameter
{
     "code": 200,
     "msg": "success",
     "data": {
         "tick": "MEME",
         "mint_amt": 133063191,
         "max_amt": 210000000,
         "dec": 18,
         "lim": 1000,
         "holders": 2445,
         "transactions": 5680,
         "deploy_time": 1685772340,
         "last_mint_time": 1687916716,
         "deploy_by": "DD8K1hQiDGSEaES5k6fP1LNNuJEsggiLFN",
         "inscription": "069bbbfe0c06bbc0afc8d9db85c4bc46f190d813600c70c7547f42987056d424"
     },
     "total": 0
}
```

## Query the currency holding address under the drc20 token

```jsx
curl --location 'https://unielon.com/v3/drc20/holders' \
--header 'Content-Type: application/json' \
--data '{"tick":"D20", "limit": 1, "offset":0}'

return parameter

{
     "code": 200,
     "msg": "success",
     "data": [
         {
             "address": "D8bZTF8fir2fsDu3hmqwdZyPkqWHT8puNP",
             "amt": 8932000000
         }
     ],
     "total": 14603
}
```

## Query the drc20 balance under the address

```jsx
curl --location 'https://unielon.com/v3/drc20/address' \
--header 'Content-Type: application/json' \
--data'{
     "receive_address": "DBQwvSkNeEVKt5vHSsVtAgSRG5WhPMVDSQ",
     "limit": 1,
     "offset": 0
}'

return parameter
{
     "code": 200,
     "msg": "success",
     "data": [
         {
             "tick": "0X69",
             "amt": 201000
         }
     ],
     "total": 55
}
```

## Query the order information of the current address

```jsx
curl --location 'https://unielon.com/v3/orders/address' \
--header 'Content-Type: application/json' \
--data '{"receive_address": "DBQwvSkNeEVKt5vHSsVtAgSRG5WhPMVDSQ","limit": 1, "offset":0}'

return parameter
{
     "code": 200,
     "msg": "success",
     "data": [
         {
             "order_id": "00ed3eb4-576f-4c22-a32f-11fe181fd83f",
             "p": "drc-20",
             "op": "mint",
             "tick": "MEME",
             "amt": 1000,
             "max": 0,
             "lim": 0,
             "dec": 0,
             "burn": "",
             "func": "",
             "rate_fee": 214745466,
             "repeat": 30,
             "fee_tx_hash": "36efe3263a2bba4ab8b685a82b797164d7d71c4c423a51bb5002c997d042fda4",
             "drc20_tx_hash": "9ce3b03ac2ce45b148cc814258214514c4db0ff3d4881f2d66251818ca81842c",
             "block_hash": "4940967d563b88ebbf1e0305602377e5670989ed5942e7e96ef4458ea0fe53b5",
             "block_confirmations": 2,
             "receive_address": "DBQwvSkNeEVKt5vHSsVtAgSRG5WhPMVDSQ",
             "to_address": "",
             "fee_address": "9uwm7EZNtL19cTQwN7KfuPnmW7yeicfdjd",
             "order_status": 0,
             "create_date": 1687866432
         }
     ],
     "total": 126
}
```

## Query order information by order number

```jsx
curl --location 'https://unielon.com/v3/orders/id' \
--header 'Content-Type: application/json' \
--data '{"order_id":"8a70718b-d66b-438e-8ae1-a8bdfddf3caf"}'

return parameter
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
```

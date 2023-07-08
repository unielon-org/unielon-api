**deploy**

```jsx
curl --location 'https://unielon.com/v3/drc20/new' \
--header 'Content-Type: application/json' \
--data '{"p":"drc-20","op":"deploy","tick":"VAN", "max": "10000", "lim":"1" ,"receive_address":"DNG7tJ8LPmuk3J8568m5yypWbHX9pBvvTi", "rate_fee": "100000000"}'

-- Parameter Description

p: default
op: default
tick: token name
max: total amount of tokens
lim: the highest token minting time
receive_address: the address of the originator
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
1. 100 transaction service fee, fixed charge
2. Flat fee of 0.0001 inscription
3. Doge transaction fee for the inscription (calculated by multiplying the transaction size by rate_fee, the size is usually 350 - 400 bytes)
```

**Mint**

```jsx
curl --location 'https://unielon.com/v3/drc20/new' \
--header 'Content-Type: application/json' \
--data '{"p":"drc-20","op":"mint","tick":"VAN", "amt": "10000", "receive_address":"DNG7tJ8LPmuk3J8568m5yypWbHX9pBvvTi", "rate_fee" : "100000000"}'

-- Parameter Description

p: default
op: default
tick: token name
amt: number of mint
receive_address: the address of the originator
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
1. 0.5 transaction service fee, fixed charge
2. Flat fee of 0.0001 inscription
3. Doge transaction fee for the inscription (calculated by multiplying the transaction size by rate_fee, the size is usually 350 - 400 bytes)
```

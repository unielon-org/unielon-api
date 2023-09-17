## liquidity

```jsx

https://unielon.com/v3/swap/liquidity

{ 
  "p": "pair-v1",
  "op": "create",
  "tick0": "wow",
  "tick1": "doge",
  "amt0":"1",
  "amt1":"1",
  "holder_address": "Dxxxxxxxx"
}

-- Parameter Description
p: default
op: create, add, remove
tick: token name
amt: the amount of add or remove drc-20
receive_address: the address of the originator

```

## swap

```jsx
https://unielon.com/v3/swap/new

{ 
  "p": "pair-v1",
  "op": "swap",
  "tick0": "wow",
  "tick1": "doge",
  "amt0":"1",
  "amt1":"1",
  "holder_address": "Dxxxxxxxx"
}

-- Parameter Description
p: default
op: create, add, remove
tick: token name
amt: the amount of add or remove drc-20
receive_address: the address of the originator

```

## **getreserves**

```jsx
https://unielon.com/v3/swap/getreserves

-- Result 
{
   "reserve0": "1",
   "reserve1": "1",
}
```

## **withdraw**

```jsx
https://unielon.com/v3/dogew/withdraw

{ 
	"amt":"1"
}

-- Parameter Description
amt: Extract quantity

-- Result 
{
	"tx_hash": ""
}

```

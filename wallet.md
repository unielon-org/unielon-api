# Connect Wallet
```javascript
unielon.requestAccounts()
```

# Mint Transfer
```javascript
unielon.sendDogecoin(to_address, amt, {feeRate: rate_fee, type: 'mint'})
```
-- Parameter Description

to_address: the recipient's address

amt: transfer amount

rate_fee: transaction fee rate (elon per kbyte)


# Drc20 Transfer
```javascript
unielon.sendDogecoin(fee_address, fee_address_rate_fee, {feeRate: rate_fee, transferAddress: to_address, ticker: tick, sendAmount: amt, type: 'transfer'})
```
-- Parameter Description

fee_address: receive fee address

rate_fee: transaction fee rate (elon per kbyte)

to_address: the recipient's address

tick: token name

amt: transfer amount

fee_address_rate_fee: receive fee address's fee rate

# Connect Wallet
```javascript
unielon.requestAccounts()
```

# Send Dogecoin
```javascript
unielon.sendDoge({toAddress: 'DKyVNmxcvFmnSqfD9nZ9vEfQTXPLP3mtU4', sendAmount: 1.2})
```
-- Parameter Description

toAddress: the recipient's address

sendAmount: transfer amount

```javascript
success return
{
    "code":200,
    "data":{
        "tx_hash":"61a8c758faf748a34847d5f5c61252efc896c999ab5b398e6b16b67b64d3499c"
    },
    "msg":"success"
}
```

```javascript
failed return
{
    "code":xxx,
    "msg":"xxxx"
}
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

# DOGE Transfer
```shell
import bitcore from 'bitcore-lib'
var privateKey = new bitcore.PrivateKey('QTUQZtPC7GY2BfDR4DHYAmnJhmsimuczXKW9m1THE9UdoDeDbudZ');
var utxo = {
  "txId" : "115e8f72f39fad874cfab0deed11a80f24f967a84079fb56ddf53ea02e308986",
  "outputIndex" : 0,
  "address" : "DChPUv3c4MQXKgMdMpWB9ENVSxoHYupRGz",
  "script" : "76a91447862fe165e6121af80d5dde1ecb478ed170565b88ac",
  "satoshis" : 50000
};

var transaction = new bitcore.Transaction()
  .from(utxo)
  .to(transferAddress, transferQuantity)
  .fee(transactionFee)
  .change(changeAddress)
  .sign(privateKey)
```

-- Parameter Description

transferAddress: Transfer address

transferQuantity: Transfer quantity

transactionFee: Mining fees

changeAddress: Change address

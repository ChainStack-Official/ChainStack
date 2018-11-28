# Guide for Command line

## Launch the command line
```
The Chainstack command line lies under the directory of GOBIN, namely "~/go/bin/chainstackcli"  
When starting the node, to use the wallet already created, you need to specify the wallet path and the corresponding wallet password.If you do not specify a wallet path, the default path is used: ~/.chainstack/    
chainstackcli --node_type [type] --soft_wallet_pwd [password]  
use  
chainstackcli -h   
for more detail of startup  

As a miner, you can use  
--is_start_mine [value]   
to determine whether you participate in mining. The fault parameter is 0 and means not starting mining.  
For exemple,  
to start local node without starting mining, use  
chainstackcli --node_type 1 --soft_wallet_pwd 123  
to start local node with starting mining, use  
chainstackcli --node_type 1 --soft_wallet_pwd 123 --is_start_mine 1    
If the startup encounters an error, it's probable that the local chain data is out of sync with chain status, and you need to delete the local data.
cd ~  
rm .chainstack -fr  
and restart the commandline  
```

## Command Line Tool Operation
The model for command line operation is like this: rpc -m [MethodName] -p [parameters]. Use ',' to seperate multiple parameters  

### CurrentBalance
```
To get the balance of the address:
rpc -m CurrentBalance -p [address]  
e.g.  
rpc -m CurrentBalance -p 0x0000e447B8B7851D3FBD5C6A03625D288cfE9Bb5eF0E
```

### CurrentBlock
```
To get the current block:
rpc -m CurrentBlock
```

### GetGenesis
```
To get the genesis block:
rpc -m GetGenesis
```
### GetBlockByNumber
```
To get the block by block number:
rpc -m GetBlockByNumber -p [blockNumber]   
e.g.  
rpc -m GetBlockByNumber -p 1
```
### GetBlockByHash
```
To get the block by block hash:
rpc -m GetBlockByHash -p [blockHash]  
e.g.  
rpc -m GetBlockByHash -p  0x0f7057ff3e3048ed38c0ac2353e001dad6aded5d825d43fcc924a39221713e4c
```

### StartMine
```
Only for minemaster  
To start mining:
rpc -m StartMine
```

### StopMine
```
Only for minemaster  
To stop mining:
rpc -m StopMine
```

### SetMineCoinBase
```
Only for minemaster   
set the coinbase address:  
rpc -m SetMineCoinBase -p [address] e.g.  
rpc -m SetMineCoinBase -p 0x0000e447B8B7851D3FBD5C6A03625D288cfE9Bb5eF0E
```

### SendTransaction
```
send a normal transaction:
rpc -m SendTransaction [from],[to],[value],[transactionFee],[extradata],[nonce]
where extradata and nonce are not mandatory, e.g.  
rpc -m SendTransaction -p 0x00004179D57e45Cb3b54D6FAEF69e746bf240E287978,0x00007eDe4D5D808DA8a267284b38E00ABccb42889dF2,20000,10
```

### Transaction
```
To inquire transaction information according to txId:  
rpc -m Transaction [TxId], e.g.  
rpc -m Transaction -p 0xf8dd21db65b2adcb5e3ed3c61475eb66a1653d309b1a82354959fdf58852f023
```

### ListWallet
```
To inquire local wallet:
rpc -m ListWallet
```

### ListWalletAccount
```
To inquire wallet account:  
rpc -m ListWalletAccount -p [walletType],[walletPath],[walletName], e.g.  
rpc -m ListWalletAccount -p SoftWallet,/home/qydev/tmp/chainstack_apps/default_v0/CSWallet,CSWallet
```

### EstablishWallet
```
To establish a new wallet:
rpc -m EstablishWallet -p [walletType],[walletPath],[walletName],[password]  
e.g.  
rpc -m EstablishWallet -p SoftWallet,/tmp/TestWallet,TestWallet,123

```
### RestoreWallet
```
To restore a wallet  
rpc -m RestoreWallet -p [walletType],[walletPath],[walletName],[password],[mnemonic],...,[mnemonic]
rpc -m RestoreWallet -p SoftWallet,/tmp/TestWallet2,TestWallet2,123,plastic,balcony,trophy,fuel,vacant,inmate,profit,rival,mimic,cute,hurdle,pig,column,pudding,visit,edge,rhythm,armed,cook,federal,amount,stock,damp,bring
```

### OpenWallet
```
To open a wallet  
rpc -m OpenWallet -p [walletType],[walletPath],[walletName],[password]
e.g.  
rpc -m OpenWallet -p SoftWallet,/tmp/TestWallet3,TestWallet3,123

```

### CloseWallet
```
To close a wallet  
rpc -m CloseWallet -p [walletType],[walletPath],[walletName], e.g.  
rpc -m CloseWallet -p SoftWallet,/tmp/TestWallet3,TestWallet3

```

### AddAccount
```
To add an account  
rpc -m AddAccount -p [walletType],[walletPath],[walletName],[drivationPath]  
drivationPath is not mandatory. In case of absence the default path is used. e.g.  
rpc -m AddAccount -p SoftWallet,/tmp/TestWallet3,TestWallet3
```

### SendRegisterTransaction
```
To send a register transaction  
rpc -m SendRegisterTransaction -p [from],[deposit],[transactionFee],[nonce]
nonce is not mandatory, e.g.  
rpc -m SendRegisterTransaction -p 0x00004179D57e45Cb3b54D6FAEF69e746bf240E287978,100,11
``` 

### SendElectTransaction
```
To send an elect transaction
rpc -m SendElectTransaction -p [from],[transactionFee],[nonce]  
nonce is not mandatory, e.g.  
rpc -m SendElectTransaction -p 0x00004179D57e45Cb3b54D6FAEF69e746bf240E287978,11
``` 

### SendCancelTransaction
```
To send a cancel transaction
rpc -m SendCancelTransaction -p [from],[transactionFee],[nonce]
nonce is not mandatory, e.g.  
rpc -m SendCancelTransaction -p 0x00004179D57e45Cb3b54D6FAEF69e746bf240E287978,11
``` 

### GetVerifiersBySlot
```
To get the verifier information according to the round number  
rpc -m GetVerifiersBySlot -p [round]
round = blocknumber / slotSize 
e.g.  
rpc -m GetVerifiersBySlot -p 2

```

### CurrentStake
```
To get the account deposit
rpc -m CurrentStake -p [address] e.g.
rpc -m CurrentStake -p 0x0000e447B8B7851D3FBD5C6A03625D288cfE9Bb5eF0E

```

### GetCurVerifiers
```
To get current verifiers
rpc -m GetCurVerifiers
```

### GetNextVerifiers
```
To get next verifiers
rpc -m GetNextVerifiers
```

### GetAddressNonceFromWallet
```
To get the nonce value of the wallet
rpc -m GetAddressNonceFromWallet -p [address] 
e.g.  
rpc -m GetAddressNonceFromWallet -p 0x00001c2beC8E0E4caac668cD75d520E41f827092Ce79
```

### GetTransactionNonce
```
To get the nonce value of the chain
rpc -m GetTransactionNonce -p [address] 
e.g.  
rpc -m GetTransactionNonce -p 0x00001c2beC8E0E4caac668cD75d520E41f827092Ce79
```





# Chainstack命令行工具使用说明

## 命令行启动
```
chainstack命令行工具位于$GOBIN目录下,即:"~/go/bin/chainstackcli".
启动节点时若需要使用已创建的钱包，则需指定钱包路径和相应的钱包密码。若不指定钱包路径，则使用系统默认路径：~/.chainstack/
chainstackcli --node_type [type] --soft_wallet_pwd [password]
chainstackcli -h 可查看启动的具体用法
对于矿工节点启动时，可通过 --is_start_mine [value]决定是否需要自动启动挖矿。默认参数为0，不启动挖矿

例：
本地启动矿工(不启动挖矿)　chainstackcli --node_type 1 --soft_wallet_pwd 123
本地启动矿工(启动挖矿)　chainstackcli --node_type 1 --soft_wallet_pwd 123 --is_start_mine 1 
本地启动验证者 chainstackcli --node_type 2 --soft_wallet_pwd 123

若启动chainstackcli报错，则可能是本地链数据与链状态不同步，需要删除本地链数据：
cd ~
rm .chainstack -fr
再次启动命令行
```
## 命令行相关功能操作
命令行相关功能操作如下:
rpc -m [MethodName] -p [parameters]
多个参数的情况下用','分隔

### CurrentBalance
```
获取地址余额:
rpc -m CurrentBalance -p [address] 例:
rpc -m CurrentBalance -p 0x0000e447B8B7851D3FBD5C6A03625D288cfE9Bb5eF0E
```

### CurrentBlock
```
获取当前区块:
rpc -m CurrentBlock
```

### GetGenesis
```
获取创世区块:
rpc -m GetGenesis
```
### GetBlockByNumber
```
根据block number 获取区块:
rpc -m GetBlockByNumber -p [blockNumber] 例:
rpc -m GetBlockByNumber -p 1
```
### GetBlockByHash
```
根据block hash 获取区块:
rpc -m GetBlockByHash -p [blockHash] 例:
rpc -m GetBlockByHash -p  0x0f7057ff3e3048ed38c0ac2353e001dad6aded5d825d43fcc924a39221713e4c
```

### StartMine
```
此功能minmaster使用
启动挖矿:
rpc -m StartMine
```

### StopMine
```
此功能minmaster使用
停止挖矿:
rpc -m StopMine
```

### SetMineCoinBase
```
此功能minmaster使用
设置矿工coinbase地址:
rpc -m SetMineCoinBase -p [address] 例:
rpc -m SetMineCoinBase -p 0x0000e447B8B7851D3FBD5C6A03625D288cfE9Bb5eF0E
```

### SendTransaction
```
发送普通交易:
rpc -m SendTransaction [from],[to],[value],[transactionFee],[extradata],[nonce]
其中extradata和nonce可缺省 例:
rpc -m SendTransaction -p 0x00004179D57e45Cb3b54D6FAEF69e746bf240E287978,0x00007eDe4D5D808DA8a267284b38E00ABccb42889dF2,20000,10
```

### Transaction
```
根据txId查询交易信息:
rpc -m Transaction [TxId] 例:
rpc -m Transaction -p 0xf8dd21db65b2adcb5e3ed3c61475eb66a1653d309b1a82354959fdf58852f023
```

### ListWallet
```
查看本地钱包:
rpc -m ListWallet
```

### ListWalletAccount
```
查看钱包账户
rpc -m ListWalletAccount -p [walletType],[walletPath],[walletName] 例:
rpc -m ListWalletAccount -p SoftWallet,/home/qydev/tmp/chainstack_apps/default_v0/CSWallet,CSWallet
```

### EstablishWallet
```
新建钱包
rpc -m EstablishWallet -p [walletType],[walletPath],[walletName],[password] 例:
rpc -m EstablishWallet -p SoftWallet,/tmp/TestWallet,TestWallet,123

```
### RestoreWallet
```
恢复钱包
rpc -m RestoreWallet -p [walletType],[walletPath],[walletName],[password],[mnemonic],...,[mnemonic]
rpc -m RestoreWallet -p SoftWallet,/tmp/TestWallet2,TestWallet2,123,plastic,balcony,trophy,fuel,vacant,inmate,profit,rival,mimic,cute,hurdle,pig,column,pudding,visit,edge,rhythm,armed,cook,federal,amount,stock,damp,bring
```

### OpenWallet
```
打开钱包
rpc -m OpenWallet -p [walletType],[walletPath],[walletName],[password]  例:
rpc -m OpenWallet -p SoftWallet,/tmp/TestWallet3,TestWallet3,123

```

### CloseWallet
```
关闭钱包
rpc -m CloseWallet -p [walletType],[walletPath],[walletName] 例:
rpc -m CloseWallet -p SoftWallet,/tmp/TestWallet3,TestWallet3

```

### AddAccount
```
增加账户
rpc -m AddAccount -p [walletType],[walletPath],[walletName],[drivationPath]
衍生路径可以缺省,系统使用默认路径. 例:
rpc -m AddAccount -p SoftWallet,/tmp/TestWallet3,TestWallet3
```

### SendRegisterTransaction
```
发送注册交易
rpc -m SendRegisterTransaction -p [from],[deposit],[transactionFee],[nonce]
nonce 可以缺省.例:
rpc -m SendRegisterTransaction -p 0x00004179D57e45Cb3b54D6FAEF69e746bf240E287978,100,11
``` 

### SendElectTransaction
```
发送竞选交易
rpc -m SendElectTransaction -p [from],[transactionFee],[nonce]
nonce 可以缺省.例:
rpc -m SendElectTransaction -p 0x00004179D57e45Cb3b54D6FAEF69e746bf240E287978,11
``` 

### SendCancelTransaction
```
发送注销交易
rpc -m SendCancelTransaction -p [from],[transactionFee],[nonce]
nonce 可以缺省.例:
rpc -m SendCancelTransaction -p 0x00004179D57e45Cb3b54D6FAEF69e746bf240E287978,11
``` 

### GetVerifiersBySlot
```
根据轮获取verifier信息
rpc -m GetVerifiersBySlot -p [round]
round = blocknumber / slotSize 例
rpc -m GetVerifiersBySlot -p 2

```

### CurrentStake
```
获取账户deposit
rpc -m CurrentStake -p [address] 例:
rpc -m CurrentStake -p 0x0000e447B8B7851D3FBD5C6A03625D288cfE9Bb5eF0E

```

### GetCurVerifiers
```
获取当前verifiers
rpc -m GetCurVerifiers
```

### GetNextVerifiers
```
获取下一轮verifiers
rpc -m GetNextVerifiers
```

### GetAddressNonceFromWallet
```
获取钱包中维护的地址nonce值
rpc -m GetAddressNonceFromWallet -p [address] 例:
rpc -m GetAddressNonceFromWallet -p 0x00001c2beC8E0E4caac668cD75d520E41f827092Ce79
```

### GetTransactionNonce
```
获取链上维护的地址nonce值
rpc -m GetTransactionNonce -p [address] 例:
rpc -m GetTransactionNonce -p 0x00001c2beC8E0E4caac668cD75d520E41f827092Ce79
```



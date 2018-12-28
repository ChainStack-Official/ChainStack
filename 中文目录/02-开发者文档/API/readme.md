# ChainStack主链功能接口文档



## CurrentBlock

#### 请求类型
Get

#### 请求字段  

无


#### 请求事例 
URL/CurrentBlock/


#### 响应字段  



| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
| Header| 区块头  | model.Header ||
| Body| 区块实体 | model.Body ||



#### 响应事例  

{   
Header: Header   `json:"header"`  
Body: Body   `json:"body"`   
}
     



## GetBlockByNumber

#### 请求类型
Post

#### 请求字段  


| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|number |  区块高度 | uint64 |是||




#### 请求事例 
URL/GetBlockByNumber/


#### 响应字段  



| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
| Header| 区块头  | model.Header ||
| Body| 区块实体 | model.Body ||


#### 响应事例  

{   
Header: Header   `json:"header"`  
Body: Body   `json:"body"`   
}
   
     
  
## GetBlockByHash

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|hash |  区块哈希 | common.Hash |是||



#### 请求事例 
URL/GetBlockByHash/


#### 响应字段  



| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
| Header| 区块头  | model.Header ||
| Body| 区块实体 | model.Body ||


#### 响应事例  

{   
Header: Header   `json:"header"`  
Body: Body   `json:"body"`   
}




## GetBlockNumber

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|hash |  区块哈希 | common.Hash |是||



#### 请求事例 
URL/GetBlockNumber/


#### 响应字段  



| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
| number| 区块高度  | uint64 ||


#### 响应事例  

{   
number: 35  
}





## GetGenesis

#### 请求类型
Get

#### 请求字段  

无



#### 请求事例 
URL/GetGenesis/


#### 响应字段  



| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
| Header| 区块头  | model.Header ||
| Body| 区块实体 | model.Body ||



#### 响应事例  

{   
Header: Header   `json:"header"`  
Body: Body   `json:"body"`   
}





## GetBlockBody

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|hash |  区块哈希 | common.Hash |是||



#### 请求事例 
URL/GetBlockBody/


#### 响应字段  



| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
| Txs| 交易列表  | model.Transaction ||
| Vers| 验证者列表 | model.AbstractVerification||
| Inters|  |||


#### 响应事例  

{  
	Txs: Txs          `json:"transactions"`  
	Vers: Vers           `json:"commit_msg"`  
	Inters: Inters            `json:"interlinks"`  
}






## CurrentBalance

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|address |  地址 | common.Address |是||



#### 请求事例 
URL/CurrentBalance/


#### 响应字段  



| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
| resp| 余额  | big.Int ||


#### 响应事例  

{   
resp: resp  
}





## Transaction

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|hash |  交易哈希 | common.Hash |是||



#### 请求事例 
URL/Transaction/


#### 响应字段  



| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
| Transaction| 交易结构体  | model.Transaction ||
| BlockHash  | 区块哈希 | common.Hash ||
| BlockNumber| 区块高度 | uint64  ||
| TxIndex    | 交易序号 | uint64  ||


#### 响应事例  

{   
	Transaction: Transaction   `json:"transaction"`  
	BlockHash: BlockHash   `json:"blockHash"`  
	BlockNumber: 105   `json:"blockNumber"`  
	TxIndex:14   `json:"transactionIndex"`  
}  









     
## GetTransactionNonce


#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|addr |  账户地址 | common.Adress |是||


#### 请求事例  
URL/Transaction/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|-----  |
|nonce |  交易nonce |uint64 ||

#### 响应事例  

{  
nonce: 27 
}






## NewTransaction


#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|transactionRlpB | 交易结构体的RLP编码值  | []byte |是||


#### 请求事例  
URL/NewTransaction/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|-----  |
|TxHash |  交易nonce |common.Hash ||

#### 响应事例  

{  
TxHash: 0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421  
}







## SetMineCoinBase


#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|address | 地址  | common.Address |是||


#### 请求事例  
URL/SetMineCoinBase/  


#### 响应字段  

无

#### 响应事例  


无






## StartMine


#### 请求类型
Post

#### 请求字段  

无


#### 请求事例  
URL/StartMine/  


#### 响应字段  

无

#### 响应事例  


无






## StopMine

#### 请求类型
Post

#### 请求字段  

无


#### 请求事例  
URL/StopMine/  


#### 响应字段  

无

#### 响应事例  


无







## EstablishWallet

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|password | 密码  | string |是||
|passPhrase |  口令     |string |是||
|WalletIdentifier |    |accounts.WalletIdentifier|是||


#### 请求事例  
URL/EstablishWallet/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|-----  |
|mnemonic |  助记词 |string ||

#### 响应事例  

{  
mnenonic: mnenomic  
}






## OpenWallet

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|password | 密码  | string |是||
|WalletIdentifier |    |accounts.WalletIdentifier|是||


#### 请求事例  
URL/OpenWallet/  


#### 响应字段  

无

#### 响应事例  

无





## CloseWallet

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|WalletIdentifier |    |accounts.WalletIdentifier|是||


#### 请求事例  
URL/CloseWallet/  


#### 响应字段  

无

#### 响应事例  

无





## RestoreWallet

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|password | 密码  | string |是||
|mnemonic | 助记词| string |是||
|passPhrase |  口令     |string |是||
|WalletIdentifier |    |accounts.WalletIdentifier|是||


#### 请求事例  
URL/RestoreWallet/  


#### 响应字段  

无

#### 响应事例  

无





## ListWallet

#### 请求类型
Post

#### 请求字段  

无

#### 请求事例  
URL/ListWallet/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|-----  |
|walletIdentifier |  钱包列表 |[]accounts.WalletIdentifier ||

#### 响应事例  

{  
walletIdentifier: walletIdentifier 
}






## ListWalletAccount

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|walletIdentifier |   | accounts.WalletIdentifier |是||


#### 请求事例  
URL/ListWalletAccount/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|-----  |
|tmpAccounts |  账户 |[]common.Address ||

#### 响应事例  

{  
tmpAccounts: tmpAccounts
}





## SetWalletAccountAddress

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|address | 地址  | common.Address |是||


#### 请求事例  
URL/SetWalletAccountAddress/  


#### 响应字段  

无

#### 响应事例  

无







## AddAccount

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|derivationPath |   | string |是||
|walletIdentifier |    |accounts.WalletIdentifier|是||


#### 请求事例  
URL/AddAccount/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|-----  |
|account |  账户 |common.Address||

#### 响应事例  

{  
account: account  
}





## SendTransaction

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|from |   | common.Address |是||
|to |    | common.Address|是||
|value|  | big.Int  |是||
|fee|    | big.Int  |是||
|nonce|  | uint64   |是||


#### 请求事例  
URL/SendTransaction/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|-----  |
|txHash |  交易哈希 |common.Hash||


#### 响应事例  

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}






## SendTransactions

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|from |   | common.Address |是||
|rpcTxs|  | model.RpcTransaction |是||

#### 请求事例  
URL/SendTransactions/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
|number |  交易次数 | int ||


#### 响应事例  

{   
number: 4  
}






## SendRegisterTransaction

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|from |   | common.Address |是||
|stake|  | big.Int  |是||
|fee|    | big.Int  |是||
|nonce|  | uint64   |是||

#### 请求事例  
URL/SendRegisterTransaction/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
|txHash|  交易哈希 | common.Hash ||


#### 响应事例  

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}





## SendUnStakeTransaction

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|from |   | common.Address |是||
|fee|    | big.Int  |是||
|nonce|  | uint64   |是||

#### 请求事例  
URL/SendUnStakeTransaction/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
|txHash|  交易哈希 | common.Hash ||


#### 响应事例  

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}





## SendEvidenceTransaction

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|from |   | common.Address |是||
|target|  | common.Address  |是||
|fee|    | big.Int  |是||
|voteA|  | model.Verification|是||
|voteB|  | model.Verification|是||
|nonce|  | uint64   |是||


#### 请求事例  
URL/SendEvidenceTransaction/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
|txHash|  交易哈希 | common.Hash ||


#### 响应事例  

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}






## SendCancelTransaction

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|from |   | common.Address |是||
|fee|    | big.Int  |是||
|nonce|  | uint64   |是||


#### 请求事例  
URL/SendCancelTransaction/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
|txHash|  交易哈希 | common.Hash ||


#### 响应事例  

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}






## GetVerifiersBySlot

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|slotNum |   | uint64 |是||

#### 请求事例  
URL/GetVerifiersBySlot/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
|addresses|  地址列表 | []common.Address ||


#### 响应事例  

{   
addresses: addresses   
}







## GetCurVerifiers

#### 请求类型
Post

#### 请求字段  

无

#### 请求事例  
URL/GetCurVerifiers/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
|addresses|  地址列表 | []common.Address ||


#### 响应事例  

{   
addresses: addresses   
}






## GetNextVerifiers

#### 请求类型
Post

#### 请求字段  

无

#### 请求事例  
URL/GetNextVerifiers/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
|addresses|  地址列表 | []common.Address ||


#### 响应事例  

{   
addresses: addresses   
}







## CurrentStake

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|address | 账户地址  | common.Address |是||

#### 请求事例  
URL/CurrentStake/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
|resp|  押金 | big.Int ||


#### 响应事例  

{   
resp: resp   
}





## GetCurrentConnectPeers

#### 请求类型
get

#### 请求字段  

无

#### 请求事例  
URL/GetCurrentConnectPeers/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
|peersInfo| | []PeerInfoResp||

#### 响应事例  

{     
peersInfo: peersInfo  
}





## GetAddressNonceFromWallet

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|address | 账户地址  | common.Address |是||

#### 请求事例  
URL/GetAddressNonceFromWallet/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|----- |
|nonce|  nonce值 | uint64 ||


#### 响应事例  

{   
nonce:25  
}





## AnnounceERC20

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|from      |   | common.Address |是||
|tokenname |   | string         |是||
|tokensymbol     |   | string  |是||
|amount|    | big.Int  |是||
|decimal|    | int  |是||
|fee|    | big.Int  |是||



#### 请求事例  
URL/AnnounceERC20/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|-----  |
|txHash |  交易哈希 |common.Hash||


#### 响应事例  

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}





## ERC20TotalSupply

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|contract address      |   | common.Address |是||


#### 请求事例  
URL/ERC20TotalSupply/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|-----  |
|total supply |  token总额 |big.Int||


#### 响应事例  

{   
total supply:  100  
}






## ERC20Transfer

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|from      |   | common.Address |是||
|to address |   | common.Address         |是||
|contract address     |   | common.Address  |是||
|amount|    | big.Int  |是||
|fee|    | big.Int  |是||



#### 请求事例  
URL/ERC20Transfer/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|-----  |
|txHash |  交易哈希 |common.Hash||


#### 响应事例  

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}





## ERC20TransferFrom

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|starter      |   | common.Address |是||
|from      |   | common.Address |是||
|to address |   | common.Address         |是||
|contract address     |   | common.Address  |是||
|amount|    | big.Int  |是||
|fee|    | big.Int  |是||



#### 请求事例  
URL/ERC20TransferFrom/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|-----  |
|txHash |  交易哈希 |common.Hash||


#### 响应事例  

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}




## ERC20Allowance

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|contract address      |   | common.Address |是||
|owner address      |   | common.Address |是||
|spender address      |   | common.Address |是||


#### 请求事例  
URL/ERC20Allowance/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|-----  |
|token allowance |  token 限额 |big.Int||


#### 响应事例  

{   
token allowance:  9  
}


## ERC20Approve

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|from      |   | common.Address |是||
|to address |   | common.Address         |是||
|contract address     |   | common.Address  |是||
|amount|    | big.Int  |是||
|fee|    | big.Int  |是||



#### 请求事例  
URL/ERC20Approve/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|-----  |
|txHash |  交易哈希 |common.Hash||


#### 响应事例  

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}


## ERC20Balance

#### 请求类型
Post

#### 请求字段  

| 变量名称 | 含义 | 变量类型 | 是否必填 | 备注 |
|----------|------|----------|----------|------|
|contract address      |   | common.Address |是||
|owner address      |   | common.Address |是||


#### 请求事例  
URL/ERC20Balance/  


#### 响应字段  

| 字段名称 | 含义 | 字段类型 | 说明 |
|----------|------|----------|-----  |
|token balance |  token 限额 |big.Int||


#### 响应事例  

{   
token balance:  9  
}

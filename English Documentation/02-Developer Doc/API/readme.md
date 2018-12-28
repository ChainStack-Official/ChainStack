# ChainStack API documentation


## CurrentBlock

#### Request Method
Get

#### Request Field 

None


#### Request Exemple
URL/CurrentBlock/


#### Response Field 



| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
| Header| Block Header  | model.Header ||
| Body| Block Body | model.Body ||



#### Response Exemple

{   
Header: Header   `json:"header"`  
Body: Body   `json:"body"`   
}
     



## GetBlockByNumber

#### Request Method
Post

#### Request Field  


| Variable | Explanation| Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|number |  Height of Block | uint64 |Yes||




#### Request Exemple
URL/GetBlockByNumber/


#### Response Field



| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
| Header| Block Header  | model.Header ||
| Body| Block Body | model.Body ||


#### Response Exemple

{   
Header: Header   `json:"header"`  
Body: Body   `json:"body"`   
}
   
     
  
## GetBlockByHash

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|hash |  Block Hash | common.Hash |Yes||



#### Request Example 
URL/GetBlockByHash/


#### Response Field 



| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
| Header| Block Header  | model.Header ||
| Body| Block Body | model.Body ||


#### Response Example

{   
Header: Header   `json:"header"`  
Body: Body   `json:"body"`   
}




## GetBlockNumber

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|hash |  Block Hash | common.Hash |Yes||



#### Request Example
URL/GetBlockNumber/


#### Response Field 



| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
| number| Block Height  | uint64 ||


#### Response Example  

{   
number: 35  
}





## GetGenesis

#### Response Method
Get

#### Response Field  

None



#### Request Example
URL/GetGenesis/


#### Response Field 



| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
| Header| Block Header  | model.Header ||
| Body| Block Body | model.Body ||



#### Response Example

{   
Header: Header   `json:"header"`  
Body: Body   `json:"body"`   
}





## GetBlockBody

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|hash |  Block Hash | common.Hash |Yes||



#### Request Example
URL/GetBlockBody/


#### Response Field



| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
| Txs| Transaction List  | model.Transaction ||
| Vers| Verifier List | model.AbstractVerification||
| Inters|  |||


#### Response Example  

{  
	Txs: Txs          `json:"transactions"`  
	Vers: Vers           `json:"commit_msg"`  
	Inters: Inters            `json:"interlinks"`  
}






## CurrentBalance

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|address |  Address | common.Address |Yes||



#### Request Example 
URL/CurrentBalance/


#### Response Field  



| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
| resp| Balance  | big.Int ||


#### Response Example  

{   
resp: resp  
}





## Transaction

#### Request Method
Post

#### Request Field 

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|hash |  Transaction Hash | common.Hash |Yes||



#### Request Example 
URL/Transaction/


#### Response Field  



| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
| Transaction| Transaction Structure  | model.Transaction ||
| BlockHash  | Block Hash | common.Hash ||
| BlockNumber| Block Height | uint64  ||
| TxIndex    | Transaction ID | uint64  ||


#### Response Example 

{   
	Transaction: Transaction   `json:"transaction"`  
	BlockHash: BlockHash   `json:"blockHash"`  
	BlockNumber: 105   `json:"blockNumber"`  
	TxIndex:14   `json:"transactionIndex"`  
}  









     
## GetTransactionNonce


#### Request Method
Post

#### Request Field 

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|addr |  Account Address | common.Adress |Yes||


#### Request Example  
URL/Transaction/  


#### Response Field 

| Field | Explanation | Type | Comment |
|----------|------|----------|-----  |
|nonce |  Transaction Nonce |uint64 ||

#### Response Example 

{  
nonce: 27 
}






## NewTransaction


#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|transactionRlpB | RLP code of Transaction Structure | []byte |是||


#### Request Example
URL/NewTransaction/  


#### Response Field

| Field | Explanation | Type | Comment |
|----------|------|----------|-----  |
|TxHash |  Transaction Nonce |common.Hash ||

#### Response Example  

{  
TxHash: 0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421  
}







## SetMineCoinBase


#### Response Method
Post

#### Response Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|address | Address  | common.Address |Yes||


#### Request Example  
URL/SetMineCoinBase/  


#### Response Field  

None

#### Response Example  


None






## StartMine


#### Request Method
Post

#### Request Field  

None


#### Request Example  
URL/StartMine/  


#### Response Field  

None

#### Response Example


None






## StopMine

#### Request Method
Post

#### Request Field  

None

#### Request Example  
URL/StopMine/  


#### Response Field 

None

#### Response Example  


None







## EstablishWallet

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|password | Password  | string |Yes||
|passPhrase |  Phrase     |string |Yes||
|WalletIdentifier |    |accounts.WalletIdentifier|Yes||


#### Request Example  
URL/EstablishWallet/  


#### Response Field

| Field | Explanation | Type | Comment |
|----------|------|----------|-----  |
|mnemonic |  Mnemonic |string ||

#### Response Example 

{  
mnenonic: mnenomic  
}






## OpenWallet

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|password | Password  | string |Yes||
|WalletIdentifier |    |accounts.WalletIdentifier|Yes||


#### Request Example  
URL/OpenWallet/  


#### Request Field 

None

#### Request Example 

None





## CloseWallet

#### Request Method
Post

#### Request Field

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|WalletIdentifier |    |accounts.WalletIdentifier|Yes||


#### Request Example  
URL/CloseWallet/  


#### Response Field

None

#### Response Example

None





## RestoreWallet

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|password | Password  | string |Yes||
|mnemonic | Mnemonic| string |Yes||
|passPhrase |  passPhrase     |string |Yes||
|WalletIdentifier |    |accounts.WalletIdentifier|Yes||


#### Request Example
URL/RestoreWallet/  


#### Response Field 

None

#### Response Example 

None





## ListWallet

#### Request Method
Post

#### Request Field

None

#### Request Example
URL/ListWallet/  


#### Response Field

| Field | Explanation | Type | Comment |
|----------|------|----------|-----  |
|walletIdentifier |  Wallet List |[]accounts.WalletIdentifier ||

#### Response Example  

{  
walletIdentifier: walletIdentifier 
}






## ListWalletAccount

#### Request Method
Post

#### Request Field

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|walletIdentifier |   | accounts.WalletIdentifier |Yes||


#### Request Example
URL/ListWalletAccount/  


#### Response Field

| Field | Explanation | Type | Comment |
|----------|------|----------|-----  |
|tmpAccounts |  Account |[]common.Address ||

#### Response Example  

{  
tmpAccounts: tmpAccounts
}





## SetWalletAccountAddress

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|address | Address  | common.Address |Yes||


#### Request Example  
URL/SetWalletAccountAddress/  


#### Response Field 

None

#### Response Example

None







## AddAccount

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|derivationPath |   | string |Yes||
|walletIdentifier |    |accounts.WalletIdentifier|Yes||


#### Request Example
URL/AddAccount/  


#### Response Field 

| Field | Explanation | Type | Comment |
|----------|------|----------|-----  |
|account |  Account |common.Address||

#### Response Example  

{  
account: account  
}





## SendTransaction

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|from | Sender's Address   | common.Address |Yes||
|to |  Receiver's Address  | common.Address|Yes||
|value| Transaction Amount | big.Int  |Yes||
|fee|  Transaction Fee  | big.Int  |Yes||
|nonce|  | uint64   |Yes||


#### Request Example  
URL/SendTransaction/  


#### Response Field  

| Field | Explanation | Type | Comment |
|----------|------|----------|-----  |
|txHash |  Transaction Hash |common.Hash||


#### Response Example  

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}






## SendTransactions

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|from |   | common.Address |Yes||
|rpcTxs|  | model.RpcTransaction |Yes||

#### Request Example
URL/SendTransactions/  


#### Response Field 

| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
|number |  Number of transactions | int ||


#### Response Example 

{   
number: 4  
}






## SendRegisterTransaction

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|from |   | common.Address |Yes||
|stake|  | big.Int  |Yes||
|fee|    | big.Int  |Yes||
|nonce|  | uint64   |Yes||

#### Request Example
URL/SendRegisterTransaction/  


#### Response Field

| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
|txHash|  Transaction Hash | common.Hash ||


#### Response Example 

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}






## SendUnStakeTransaction

#### Request Method
Post

#### Request Filed

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|from |   | common.Address |Yes||
|fee|    | big.Int  |Yes||
|nonce|  | uint64   |Yes||

#### Request Example  
URL/SendUnStakeTransaction/  


#### Response Field  

| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
|txHash|  Transaction Hash | common.Hash ||


#### Response Example  

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}





## SendEvidenceTransaction

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|from |   | common.Address |Yes||
|target|  | common.Address  |Yes||
|fee|    | big.Int  |Yes||
|voteA|  | model.Verification|Yes||
|voteB|  | model.Verification|Yes||
|nonce|  | uint64   |Yes||


#### Request Example 
URL/SendEvidenceTransaction/  


#### Response Field  

| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
|txHash|  Transaction Hash | common.Hash ||


#### Response Example  

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}






## SendCancelTransaction

#### Request Method
Post

#### Request Field

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|from |   | common.Address |Yes||
|fee|    | big.Int  |Yes||
|nonce|  | uint64   |Yes||


#### Request Example  
URL/SendCancelTransaction/  


#### Response Field  

| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
|txHash|  Transaction Hash | common.Hash ||


#### Response Example

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}






## GetVerifiersBySlot

#### Request Method
Post

#### Request Field

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|slotNum |   | uint64 |Yes||

#### Request Example
URL/GetVerifiersBySlot/  


#### Response Field  

| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
|addresses|  Address List | []common.Address ||


#### Response Example  

{   
addresses: addresses   
}







## GetCurVerifiers

#### Request Method
Post

#### Request Field

None

#### Request   
URL/GetCurVerifiers/  


#### Response Field

| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
|addresses|  Address List | []common.Address ||


#### Response Example  

{   
addresses: addresses   
}






## GetNextVerifiers

#### Request Method 
Post

#### Request Field 

None

#### Request Example  
URL/GetNextVerifiers/  


#### Response Field

| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
|addresses|  Address List | []common.Address ||


#### Response Example  

{   
addresses: addresses   
}







## CurrentStake

#### Request Method
Post

#### Request Field

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|address | Account Address  | common.Address |是||

#### Request Example
URL/CurrentStake/  


#### Response Field  

| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
|resp|  Stake | big.Int ||


#### Response Example 

{   
resp: resp   
}





## GetCurrentConnectPeers

#### Request Method
get

#### Request Field

None

#### Request Example 
URL/GetCurrentConnectPeers/  


#### Response Field 

| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
|peersInfo| | []PeerInfoResp||

#### Response Example

{     
peersInfo: peersInfo  
}





## GetAddressNonceFromWallet

#### Request Method
Post

#### Request Field

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|address | Account Address  | common.Address |是||

#### Request Field
URL/GetAddressNonceFromWallet/  


#### Response Field

| Field | Explanation | Type | Comment |
|----------|------|----------|----- |
|nonce|  Nonce Value | uint64 ||


#### Response Example

{   
nonce:25  
}








## AnnounceERC20

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|from      |   | common.Address |Yes||
|tokenname |   | string         |Yes||
|tokensymbol     |   | string  |Yes||
|amount|    | big.Int  |Yes||
|decimal|    | int  |Yes||
|fee|    | big.Int  |Yes||



#### Request Example  
URL/AnnounceERC20/  


#### Response Field  

| Field | Explanation | Type | Comment |
|----------|------|----------|-----  |
|txHash |  Transaction Hash |common.Hash||


#### Response Example

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}





## ERC20TotalSupply

#### Request Method
Post

#### Request Field 

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|contract address      |   | common.Address |Yes||


#### Request Example  
URL/ERC20TotalSupply/  


#### Response Field  

| Field | Explanation | Type | Comment |
|----------|------|----------|-----  |
|total supply |  Token Total Supply |big.Int||


#### Response Example  

{   
total supply:  100  
}






## ERC20Transfer

#### Request Method  
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|from      |   | common.Address |Yes||
|to address |   | common.Address         |Yes||
|contract address     |   | common.Address  |Yes||
|amount|    | big.Int  |Yes||
|fee|    | big.Int  |Yes||



#### Request Example  
URL/ERC20Transfer/  


#### Response Field  

| Field | Explanation | Type | Comment |
|----------|------|----------|-----  |
|txHash |  Transaction Hash |common.Hash||


#### Response Example  

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}





## ERC20TransferFrom

#### Request Method 
Post

#### Request Field 

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|starter      |   | common.Address |Yes||
|from      |   | common.Address |Yes||
|to address |   | common.Address         |Yes||
|contract address     |   | common.Address  |Yes||
|amount|    | big.Int  |Yes||
|fee|    | big.Int  |Yes||



#### Request Example  
URL/ERC20TransferFrom/  


#### Response Field

| Field | Explanation | Type | Comment |
|----------|------|----------|-----  |
|txHash |  Transaction Hash |common.Hash||


#### Response Example 

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}




## ERC20Allowance

#### Request Method
Post

#### Request Field 

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|contract address      |   | common.Address |Yes||
|owner address      |   | common.Address |Yes||
|spender address      |   | common.Address |Yes||


#### Request Example   
URL/ERC20Allowance/  


#### Response Field

| Field | Explanation | Type | Comment |
|----------|------|----------|-----  |
|token allowance |  token max limit |big.Int||


#### Response Example   

{   
token allowance:  9  
}


## ERC20Approve

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|from      |   | common.Address |Yes||
|to address |   | common.Address         |Yes||
|contract address     |   | common.Address  |Yes||
|amount|    | big.Int  |Yes||
|fee|    | big.Int  |Yes||



#### Request Example 
URL/ERC20Approve/  


#### Response Field  

| Field | Explanation | Type | Comment |
|----------|------|----------|-----  |
|txHash |  Transaction Hash |common.Hash||


#### Response Example 

{   
txHash:  0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421   
}


## ERC20Balance

#### Request Method
Post

#### Request Field  

| Variable | Explanation | Type | Mandatory | Comment |
|----------|------|----------|----------|------|
|contract address      |   | common.Address |Yes||
|owner address      |   | common.Address |Yes||


#### Request Example  
URL/ERC20Balance/  


#### Response Field  

| Field | Explanation | Type | Comment |
|----------|------|----------|-----  |
|token balance |  Token Balance |big.Int||


#### Response Example   

{   
token balance:  9  
}

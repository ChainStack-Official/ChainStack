## Summary 

ChainStack is a distributed system that provides state consistency for multiple machines and enables reliable value transfer in an untrusted communication environment on the Internet.

ChainStack builds a native multi-chain system which supports multi-industry (digital asset, supply) and multi-form (built-in paradigm on the chain, cloud server, applet, side chain, etc.) decentralized applications through tiered smart contract design, high-frequency transaction paradigm and unlicensed business innovation support, combined with multiple technologies such as native multi-chain/cross-chain/sharding. The layered intelligent contract design separates the business logic from the state consensus, and standardizes the cross-chain interface to achieve cross-chain communication at the telecommunications network level while standardizing the burden on the main chain. ChainStack follows the stacking principle, and each layer is designed as Plug-and-Play (plug-and-play), in which the core modules are replaceable, making ChainStack a simpler and more extensive service.

ChainStack uses an original consensus mechanism to separate the mining and the verification. It keeps the decentralization level of the bitcoin, shortening the time for reaching consensus, and providing the performance to meet the tens of millions of daily activities (DAU).

ChainStack's native multi-chain architecture provides a model for the main chain and sidechain division of labor. Its ultra-light wallet payment verification (CSPV) technology provides strong support for mobile users. CSPV technology allows ultra-light nodes to synchronize data with minimal amounts and does not grow with blockchain growth, and any mobile client or even smart contract code area can support it.


## 1. Blockchain Overview
### 1.1 Background and meaning
Blockchain technology originated from Bitcoin. In 2008, Nakamoto published "Bitcoin -- a peer-to-peer electronic cash system", which explained how to use an encryption algorithm, distributed principle, P2P network, proof of work and other methods to establish a decentralized digital currency system. Based on the example of this paper, Bitcoin was introduced in 2009, showing an electronic money trading system that does not rely on trustable third parties. This system uses a synchronized ledger distributed across all nodes instead of a single ledger on a traditional central server, replacing the subjective "trust" of intermediaries with an objective "consensus" mechanism, enabling reliable value transfer in a non-trusted environment.

Bitcoin did not directly propose the concept of "blockchain". It was later when people summarized the main technical features used in Bitcoin and proposed the more general and abstract meaning of "blockchain". The birth of the blockchain provides a new type of social trust mechanism for human beings, marking the beginning of a truly trustworthy Internet for human beings and forms the foundation of value Internet.

Ethereum's Turing machine has been improved to complete compared to the non-complete script executor of Bitcoin, extending support for executable scripts, enabling developers to deploy smart contracts on Ethereum blockchain platforms to handle more complex service. The creator of the smart contract on Ethereum can set the business logic through code to allow the contract to automatically trigger execution according to the conditions without human intervention, so that the contract is transparent and not tamperable. Since then, blockchain technology has been widely discussed in many aspects such as the issuance of certificates, financial settlement, digital asset trading, anti-counterfeiting traceability and sharing economy.


### 1.2 Problems and Challenges

Based on the emergence of various distributed applications on Ethereum, the success of these open source, decentralized technologies is a useful attempt to apply blockchain technology to vertical industries. However, up to now the issues exposed by these blockchains cannot remain ignored.

- Difficulty to meet performance demand: With the hot blockchain industry, the performance of existing blockchains is difficult to meet the growing needs of users. Whether it is Ethereum or Bitcoin, the congestion of the network and the slow transaction speed are huge problems.

- A dilemma for smart contract applications: Smart contracts face the dilemma of security and flexibility. As an open smart contract, Ethereum provides users with the freedom of coding. But the writing of smart contracts must use their own unique programming language and it raises the technical barrier. In addition, the security of smart contracts is highly dependent on the contract code itself and is vulnerable to hackers.

- Single ecological environment: Most of the current blockchain projects are single main chains without side chains, and the consensus algorithm is unique (or the algorithm is unique at the same time). All kinds of consensus algorithms have their advantages and disadvantages, and their adaptation scenarios are different. Limited by the consensus algorithm, the application scenario on the blockchain network is also like dancing with a cockroach. For projects with sidechains, the chains in the same blockchain network are also difficult to communicate with each other, no need to say cooperations between blockchains. The blockchain communication in the isolated island state greatly limits the space for the blockchain to play, which is also a reason why the current blockchain technology is difficult to land in commercial application scenarios.


## 2. ChainStack design ideas
ChainStack provides solutions to the problems and challenges of existing blockchains. Its design follows the following ideas:

- Meet the performance of the tens of millions of daily applications (DAU): At present, Bitcoin, Ethereum, etc. are limited by the consensus algorithm, and the performance cannot meet the increasing demand. ChainStack provides an innovative consensus algorithm for high-frequency, high-throughput applications with performance to meet the requirements of tens of millions of daily applications (DAU), with TPS reaching millions of levels.

- Structured blockchain system: ChainStack provides an adaptable, unlimited scale-up blockchain system by layering and functionalizing smart contracts. ChainStack pioneered the telecommunications-level cross-chain interworking interface, allowing dApps on different chains to synchronize state and achieve effective cross-chain interaction.

- Parametric high-frequency applications: ChainStack provides built-in paradigm support for high-frequency applications such as ERC20, allowing users to run these high-frequency applications without the need for coding. The support of the built-in paradigm d also avoids contractual vulnerabilities caused by user-side programming errors.

- Broader and easier development support: The dApp is written in any language on ChainStack, allowing application developers to make unlicensed innovations. Developers do not have programming language or application functionality limitations when developing an arbiterary dApp (arbitrary distributed application). ChainStack organizes an open source community to provide the dApp market. Developers can write dApps based on the ChainStack specification.

## 3. ChainStack Technology Framework
### 3.1 ChainStack Overview
ChainStack provides an adaptable blockchain system and a mobile distributed application platform. With the original consensus mechanism and layered smart contract architecture, combined with the original multi-chain system design, the dApp development threshold is lowered. Chain technology penetrates into vertical industry users.

ChainStack also provides an ultra-light wallet payment verification. Users can improve the ChainStack ecosystem by using a series of dApps developed by third-party developers on the mobile terminal such as mobile phones through the wallet of the ChainStack configuration sandbox environment.

### 3.2 ChainStack Technical Features
- Original consensus mechanism


ChainStack expects to design a consensus algorithm that combines high performance with high fairness. The traditional PoW algorithm provides a high degree of decentralization, but the block rate is slow and the throughput is small, which cannot meet the high frequency requirements. The PoS mechanism omits the steps of proof of work calculation, and its block generation is fast and its throughput is high. However, in this algorithm, capital proportion greatly affects the allocation of billing rights, and the DPoS mechanism of its variant algorithm brings hidden dangers of game attack in the process of selecting representatives.
    
    The ChainStack main chain runs a unique consensus mechanism. The consensus mechanism will decentralize and verify decentralization, and use the original Map-Reduce PoW algorithm to ensure fairness while reducing the block generation time. The verification process using the PBFT algorithm shortens the validation time and increases system throughput.

- Layered smart contract architecture

    ChainStack follows a structured design philosophy, stripping business logic and state consensus. Is provides a broader and easier-to-use smart contract development support while reducing the load on the main chain.

ChainStack's smart contract architecture consists of the following three layers:
    * Core state storage layer: Based on MPT technology, it provides an efficient distributed application state storage, while implementing a chain-limited finite state machine. By applying state constraints on the chain of smart contracts and applying boundary definitions to their contracts, the security and performance energy levels of the application and the underlying blockchain are leapfrogged.
    * Enabling layer: Consensus communication layer uses P2P communication technology and pluggable and replaceable consensus algorithm, and integrates high frequency contract paradigm primitives such as ERC20/ERC721, etc. This layer also provides side chain bidirectional anchoring and cross The basic capabilities of chain communication.
    * Application layer: change the state of the application through the interface provided by the state consensus engine. The implementation forms include the chain-based high-frequency, paradigm-based dApp based on configuration parameters, and the cloud server interacting with the consensus engine in the wallet sandbox environment. Run the applet (H5+JS), a custom sidechain generated by one-click provided by ChainStack.

    - Native multi-chain system

    ChainStack provides a native multi-chain system. This is a structured blockchain system, with its main chain and side chain division of labor, each with its distributed network, miners group, consensus mechanism, digital assets and so on. The main chain of ChainStack is responsible for the core operations of the ChainStack system, handling the most important transactions, and maintaining the security and stability of the system. The sidechain of ChainStack uses a polymorphic mechanism to select the appropriate mode according to the characteristics of its application, such as PoW, PoS, DPoS, PBFT, or public chain, alliance chain, private chain, and so on.
    
    ChainStack also provides support for atomic trading between chains, which extends application boundary and provides an ultra-light wallet payment verification (CSPV) to support mobile use.

For more details on the ChainStack architecture and technical details, please refer to the technical white paper.

## 4. Application scenario
ChainStack supports multi-industry, multi-modal decentralized applications. Application scenarios include, but are not limited to, digital assets, smart contracts, supply chains, sharing economies, and public services.
![cwp-1](https://github.com/caiqingfeng/res/blob/master/04-whitepaper/cwp-1.jpg)


### 4.1 Digital Asset Issuance
ChainStack encapsulates and normalizes ERC20. Users can freely set parameters by calling the ERC20 interface provided by ChainStack, so that they can issue their own tokens simply and quickly. These tokens can be proof of the service provided.

When a user wants to create an ERC20 token, he only needs to initiate a transaction through the wallet. This transaction requires the configuration information (name, total amount, etc.) of the ERC20 token, so that the certificate based on the ERC20 standard can be created with one click. No need to worry about the vulnerability of the token code which is susceptible to damage the user's interests. It is safe and reliable, and supports all the defined functions of the ERC20.

It is necessary to initiate a transaction to launch all functions that can change the storage, e.g. the creation of the token, the transfer of the token, the approval of others to withdraw the token, etc. All need to pay a certain fee except the function of the inquiry (check the balance of a certain account, view The name of the pass, etc.) 


### 4.2 Decentralized auction platform
ChainStack offers a paradigm contract based on the ERC721 and auction platform. Through the ERC721 interface and auction contract interface provided by ChainStack, users can freely set parameters to quickly release an auction platform based on ERC721.

The user first initiates a transaction through the wallet, and with the corresponding configuration of the ERC721 token, an ERC721 token can be established. After the ERC721 is successfully created, a transaction is initiated, which brings the relevant information of the auction platform (corresponding to the ERC721 certificate, etc.), and binds the previously created ERC721 certificate to the auction contract, thereby creating an auction platform. Then call the ERC721 contract method to give the trading rights to specify the auction contract.

The default auction method for the ChainStack decentralized auction contract is the Dutch auction. That is, the seller sets a maximum price at the beginning, and the price gradually decreases with time until the price reaches the lowest price set by the seller.

This process is transparent, safe and reliable for both users due to the use of decentralization and irreversible recording of the blockchain and the automation of the contract.

### 4.3 Decentralized data transactions
ChainStack provides a decentralized data transaction that prevents data precipitation. The data consumer can use the push applet to claim the customer object and related data information that he wants and make a quote. The data provider decides whether to provide its own data and information by consulting the contents of the applet and its quotation, and completes the data validation and transaction through the underlying blockchain of the system. During this process, the applet runs in the sandbox environment of the wallet and only sends the analysis results. The user's original data is still stored in their local wallet and will not be compromised.

### 4.4 Automatically triggered insurance claims
ChainStack offers the possibility of an automatically triggered insurance claim. Traditional insurance claims require insurance institutions to fund, invest and settle claims. Especially in terms of claims, the application process is complicated and takes a long time. For weather insurance, delay insurance and other types of insurance that can be confirmed by objective factors, the smart contract can realize the parameterization of the claim conditions, and realize the automatic payment of the policy and the automatic payment of the insurance amount. While reducing the operating costs of insurance institutions, it shortens the time for customers to obtain compensation and reduces the energy required to apply for compensation.

## 5. Founding team

### Zhao Liang(CEO)
Founder of ChainStack, graduated from the strengthened science class of Nanjing University, and obtained a master and a PHD's degree in engineering from the University of Miami. With more than ten years of experience in overseas financial industry, he has accumulated rich practical experience in financial risk pricing and marketing, and has accurate analytical judgment on global financial markets. Formerly head of investment banking at Credit Suisse in Wall Street, New York, responsible for liquidity risk and capital budgeting for global operations. After joining the first capital bank (CapitalOne) as a data scientist, he deeps into the field of data modeling and anti-fraud. He has several patents in the field of algorithms.

### Cai Qingfeng(CTO)
The co-founder of ChainStack, graduated from Wuhan University in 1996, has served as Huawei System Architect, MKT Marketing Manager, Product Planning Manager, MKTG Minister of Northeast Europe Core Network and Director of Converged Communications R&D Department. He has practical experience in leading large teams in the field of Internet. In 2014, he entered the blockchain industry and has accumulated four years' experience in this field.

### Lai Yupeng (COO)
ChainStack COO, successively as Hande FinMaker CCO, Rongshu FinTech CDO, Vice President of UnionPay Consulting. He holds a bachelor's degree from Wuhan University, a master's degree from the University of Tsukuba, Japan, and PhD in Uppsala University, Sweden, and MBA from Indiana University. From 2006 to 2014, he worked for Capital One, responsible for model system construction, strategic construction and customer management for credit card core business. He has provided quantitative solutions and training for more than a dozen organizations and received 10 million consulting revenues.

### Pan Lu(CMO)
ChainStack CMO, graduated from South Central University for Nationalities. 12 years of IPO, brand management, and operational experience. From 2006 to 2015, he worked for Huawei. He was the director of Huawei's core network MKT and the head of Huawei's UAE core network. He was responsible for the product launch, brand and operation of Huawei's converged data center solutions.

### Xu Yang(CSO)
ChainStack CSO, obtained a bachelor's degree from Singapore Management University and a master's degree from Fordham University. Worked at Goldman Sachs (USA), Capital One (USA), and Ernst & Young (Singapore), she has extensive experience in operational leadership, project management and financial analysis.

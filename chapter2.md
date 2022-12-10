### CHAPTER TWO
Ethereum is the system, while ether is the currency represented in ETH.
The value of ether is always represented internally in Ethereum as an unsigned integer value denominated in wei. When you transact 1 ether, the transaction encodes 1000000000000000000 wei as the value(msg.value).

The smallest unit of ethereum is wei represented in 10 ** 18. 
1 ether is 1 * 10**18 

#### Wallet
The term "wallet" refers to a software application that assists you in managing your Ethereum account. A wallet is a piece of software that acts as the primary user interface for Ethereum. In a nutshell, an Ethereum wallet serves as your entry point into the Ethereum system. It has access to your keys and can initiate and broadcast transactions on your behalf. The wallet manages a user's money, manages keys and addresses, tracks the balance, and creates and signs transactions. A wallet  refers to the system used to store and manage a users key. The wallet holds only keys. 

Since a wallet application requires access to your private keys in order to function, it is critical that you only download and use wallet applications from reputable sources.

Trusted wallets include MetaMask, Jaxx, MyEtherWallet (MEW), Emerald Wallet, and others.


#### Accountability
One major aspect is that each Ethereum user can and should control their own private keys, which control access to funds and smart contracts.

#### Diffefence Between an Externally Owned Accounts (EOAs) and Contract Accounts.

Externally owned accounts have a private key; having the private key means having control over your funds while A contract account lacks a private key. It is instead owned (and controlled) by the logic of its smart contract code: the software program recorded on the Ethereum blockchain at the creation of the contract account and executed by the EVM. 

Your EOA is controlled by a private key hence you can initiate transactions (you can start a call and interact with different smart contracts) while A contract account cannot initiate a transaction. 

Msg.sender can be either a contact account or an EOA, while tx.origin can only be an EOA.

An EOA can not have a smart contract code while A contract account can have smart contract code.

###### Similarities
Contracts, like EOAs, have addresses. 
Contracts, like EOAs, can send and receive ether.

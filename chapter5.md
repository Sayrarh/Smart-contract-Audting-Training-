# Chapter 5 - Wallets
A wallet is a piece of software that acts as the primary user interface for Ethereum. The wallet manages a user's money, manages keys and addresses, tracks the balance, and creates and signs transactions.

A wallet is a system for storing and managing a user's key. The wallet only contains keys. Your ethers and tokens are stored on the Ethereum blockchain. Users control the tokens on the network by signing transactions with the wallet's keys. Your wallet provider is not required for your account to exist.

## Misconceptions About Wallet
Ethereum wallets do not contain ether or tokens. In fact, the wallet only contains keys. 
The Ethereum blockchain stores the ether or other tokens. Users have control over the network's tokens by signing transactions with the keys in their wallets. In some ways, an Ethereum wallet is similar to a keychain containing pairs of private and public keys. Users sign transactions with the private keys, thereby proving they own the ether.

## Types of Wallets
1. Nondeterministic wallet: each key is generated independently from a different random number. The keys are unrelated to one another. JBOK (Just a bunch of keys) wallet, for example.

2. Deterministic wallet: is one in which all keys are derived from a single master key known as the seed. They are related and can be generated again if the seed phrase is known. For example, metamask.

Memonic code words are a list of words that you write down and use in the events of an accident.  

### Common standards are:

Mnemonic code words, based on BIP-39 </br>
HD wallets, based on BIP-32 </br>
Multipurpose HD wallet structure, based on BIP-43 </br>
Multicurrency and multiaccount wallets, based on BIP-44 </br>

How is the seed created? </br>
By combining mnemonic + salt('mnemonic' + optional pass), then running it through the PBKDF2 hash function for 2048 rounds, a 512-bit seed is produced.
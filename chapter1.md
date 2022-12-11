##CHAPTER 1:  Ethereum
What is Ethereum? </br>
Ethereum is a decentralized computing infrastructure that allows smart contracts to run. It makes use of a blockchain to integrate and store system state changes (transactions).

### Origin of Ethereum
Ethereum was Founded by Vitalik Buterin in 2013, and built together with Gavin wood.
Ethereum's first block also called the genesis block was mined in July 30, 2015.

### Ethereum's Native currency
Ether, Ethereum's native token, is used for payments and transaction execution costs on the Ethereum blockchain. Ether is designed to be a utility currency used to pay for the use of the Ethereum platform as the world computer. 


### Ethereum's Purpose
Ethereum's primary goal is not to be a digital currency payment network unlike the Bitcoin Blockchain. 
Ethereum's language is Turing complete, which means that it can function as a general-purpose computer.
Turing Complete refers to a machine that, given enough time and memory, as well as the necessary instructions, can solve any computational problem, regardless of how complex it is. Because most modern programming languages are Turing Complete (C++, Python, JavaScript, etc.), the term is commonly used to describe them. For example, Bitcoin is not turing complete and thus cannot be built upon, whereas Ethereum is turing complete and thus can be built upon.


### Turing Completeness and Its Consequences
Turing-complete systems can run in "infinite loops," which presents a challenge in Ethereum: every participating node (client) must validate every transaction, as well as run any smart contracts it invokes. However, as Alan Turing demonstrated, Ethereum cannot predict whether or not a smart contract will terminate or how long it will run without actually running it (possibly running forever). When a node attempts to validate a smart contract, it can run forever, whether by accident or on purpose. This is essentially a denial-of-service attack. 
Gas is a metering mechanism introduced by Ethereum. The EVM carefully accounts for each instruction as it executes a smart contract (computation, data access, etc.).


Ethereum monitors the state transitions of a general-purpose data store, which can hold any data expressible as a key-value tuple. A key-value data store stores arbitrary values, each of which is referenced by a key(like a mapping).Ethereum has memory that stores both code and data, and it tracks how this memory changes over time using the Ethereum blockchain. Ethereum, like a general-purpose stored-program computer, can load and run code, storing the resulting state changes in its blockchain.


### Major components of ethereum blockchain
1. Peer to peer network that connects participants, eliminating the need for an intermediary.
2. Distributed Digital Ledger.
3. Consensus Mechanism: A set of rules for reaching agreement on what defines a transaction and what constitutes a valid state transition.
4. Consensus Algorithm.
5. A virtual machine, consensus-based state machine that processes transaction.
6. Transactions(messages) which represent state changes. Ethereum transactions are network messages that include a sender, recipient, value, and data payload, among other things.
7. Incentivization scheme. For example in the proof of work, Miners get block reward for every successful mined block.
8. Cryptography.
9. Data Structure.
10. Clients, The most prominent interoperable client software implementations for Ethereum are Go-Ethereum (Geth) and Parity.


### Stages of Ethereum development
Ethereum's development was planned in four stages, with significant changes occurring at each stage.
1. Frontier: Ethereum's initial stage also the ethereum genesis block, which lasted from July 30, 2015 to March 2016. 
2. Homestead: The second stage of Ethereum, launched in March 2016. with block number - #1,150,000.
3. Metropolis: Metropolis is Ethereum's third stage. Byzantium, the first part of Metropolis, was released in October 2017, adding low-level functionalities and adjusting the block reward and difficulty. with the block number 4,370,000
4. Serenity: Last stage of ethereum development which entails a significant infrastructure reorganization that will make Ethereum more scalable, secure, and sustainable(Ethereum 2.0).

To date, the intermediate hard forks have been codenamed Ice Age, DAO, Tangerine Whistle, Spurious Dragon, Byzantium, Constantinople/St. Petersburg, Istanbul and Muir Glacier.


### A DApp(DEcentraised Application) is composed of:
 1. Smart contracts on a blockchain
 2. A web frontend user interface


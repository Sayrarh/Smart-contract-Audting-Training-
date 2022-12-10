### ETHEREUM CLIENTS

An Ethereum client is a software application that implements the Ethereum specification and communicates with other Ethereum clients via the peer-to-peer network. Different Ethereum clients can communicate with one another if they follow the reference specification and the standardized communication protocols. While these various clients are implemented by various teams and in various programming languages, they all "speak" the same protocol and adhere to the same rules. As a result, they can all operate on and interact with the same Ethereum network.

Ethereum Networks
Currently, there are six main implementations of the Ethereum protocol, written in six different languages:

Parity, written in Rust

Geth, written in Go

cpp-ethereum, written in C++

pyethereum, written in Python

Mantis, written in Scala

Harmony, written in Java

#### Types Of Node

Full Node: A full node can download and store up to 300 GB of data (as of March 2021, depending on client configuration) on a local hard drive. This data burden grows exponentially each day as new transactions and blocks are added.

Remote Ethereum Clients
Remote clients offer a subset of the functionality of a full client. They do not store the full Ethereum blockchain, so they are faster to set up and require far less data storage.

These clients typically provide the ability to do one or more of the following:

. Manage private keys and Ethereum addresses in a wallet.
. Create, sign, and broadcast transactions.
. Interact with smart contracts, using the data payload.
. Browse and interact with DApps.
. Offer links to external services such as block explorers.
. Convert ether units and retrieve exchange rates from external sources.
. Inject a web3 instance into the web browser as a JavaScript object.
. Use a web3 instance provided/injected into the browser by another client.
. Access RPC services on a local or remote Ethereum node.


#### Running an Ethereum Client

This requires some familiarity with your operating system's command-line interface. Installing these clients is worthwhile, whether you run them as full nodes, testnet nodes, or clients to a local private blockchain.

##### Hardware Requirements for a Full Node

Before we begin, make sure you have a computer with enough resources to run an Ethereum full node. A full copy of the Ethereum blockchain will require at least 300 GB of disk space. If you also want to run a full node on the Ethereum testnet, you'll need at least another 75 GB. It is recommended that you work on a fast internet connection while downloading 375 GB of blockchain data.

It is preferable to have a solid-state drive (SSD) because syncing the Ethereum blockchain requires a significant amount of input/output (I/O).

You will need at least 8 GB of RAM to use as cache if you have a mechanical hard disk drive (HDD). Otherwise, you may find that your system is too slow to keep up and fully sync.

###### Minimum requirements:

CPU with 2+ cores

At least 300 GB free storage space

4 GB RAM minimum with an SSD, 8 GB+ if you have an HDD

8 MBit/sec download internet service

These are the minimum requirements to sync a full (but pruned) copy of an Ethereum-based blockchain.


###### Recommended specifications:

Fast CPU with 4+ cores
16 GB+ RAM
Fast SSD with at least 500 GB free space
25+ MBit/sec download internet service

###### Parity
Parity is an implementation of a full-node Ethereum client and DApp browser. 

###### Go-Ethereum (Geth)
Geth is the Go language implementation that is actively developed by the Ethereum Foundation, so is considered the "official" implementation of the Ethereum client.

###### The JSON-RPC Interface
Ethereum clients provide an application programming interface (API) as well as a set of Remote Procedure Call (RPC) commands encoded in JavaScript Object Notation (JSON). This is known as the JSON-RPC API, and it is an interface that allows us to write programs that use an Ethereum client as a gateway to an Ethereum network and blockchain.
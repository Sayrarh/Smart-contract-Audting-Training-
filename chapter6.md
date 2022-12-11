# Chapter 6 - Transaction in Ethereum
Every activity in the Ethereum system begins with a transaction. Transactions are the "inputs" that cause the Ethereum Virtual Machine to evaluate contracts, update balances, and modify the state of the Ethereum blockchain in general. 
Account transactions are cryptographically signed instructions. An account will initiate a transaction to update the Ethereum network's state. Every Ethereum transaction requires the payment of a fee, which is collected by miners in order for the transaction to be validated. 

A transaction is the only thing that can trigger the state change. 

In Ethereum, fees are charged in the form of a virtual currency known as gas. As part of the transaction, you pay for the gas with ether.


## The structure of a transaction
A submitted transaction includes the following information:
signature: the identifier of the sender. This is generated when the sender's private key signs the transaction and confirms that the sender has authorized this transaction.

1. gasLimit: the maximum amount of gas units that can be consumed by the transaction. Units of gas represent computational steps
2. Nonce: A sequence number, issued by the originating EOA, used to prevent message replay. nonce: A scalar value equal to the number of transactions sent from this address or, in the case of accounts with associated code, the number of contract-creations made by this account.
3. Gas price: The amount of ether (in wei) that the originator is willing to pay for each unit of gas.
4. Recipient: The destination Ethereum address.
5. Value: The amount of ether (in wei) to send to the destination.
6. Data: The variable-length binary data payload.
7. V,r,s: The three components of an ECDSA digital signature of the originating EOA.
 
## Transaction Gas
Ethereum's fuel is gas. Gas is not ether; it is a distinct virtual currency with its own exchange rate relative to ether. Because a transaction will be processed on thousands of computers around the world, Ethereum uses gas to control the amount of resources that a transaction can use. To avoid denial-of-service attacks , the open-ended (Turing-complete) computation model requires some form of metering.

The gasPrice field in a transaction allows the transaction originator to set the price they are willing to pay in exchange for gas. The price is measured in wei per gas unit.

Wallets can change the gasPrice in transactions they initiate in order to achieve faster transaction confirmation. The faster the transaction is likely to be confirmed, the higher the gasPrice.

The second important gas-related field is *gasLimit*. GasLimit specifies the maximum number of units of gas that the transaction originator is willing to purchase in order to complete the transaction. The gas amount required for simple payments, which are transactions that transfer ether from one EOA to another, is fixed at 21,000 gas units. To determine the cost of ether, multiply 21,000 by the gasPrice you are willing to pay.

## Beneficiary of the Transaction
The *to* field specifies the recipient of a transaction. This has a 20-byte Ethereum address in it. An EOA or a contract address can be used. </br>

This field is not validated further by Ethereum. Any 20-byte value is acceptable. The transaction is still valid if the 20-byte value corresponds to an address without a corresponding private key or contract. Ethereum has no way of knowing whether an address was correctly derived from an existing public key (and thus from a private key). You can send to an address that does not have a corresponding private key or contract, effectively "burning" the ether and rendering it unspendable forever. Validation should begin with the user interface.

## Data and Transaction Value
The 'Payload' of a transaction is contained in two fields: </br>
*Value* , and </br>
*Data*. </br>

Transactions can contain both value and data which is a payment as well as an invocation.</br>
A transaction that contain only value is a payment </br>
A transaction that contain only data is an invocation.</br>
A transaction with no value or data is nothing. </br>
All four combinations are correct.</br>

The data payload sent to an ABI-compatible contract (which you can assume all contracts are) is a hex-serialized encoding of:</br>

## Function Selector
The first 4 bytes of the Keccak-256 hash of the function’s prototype. This allows the contract to unambiguously identify which function you wish to invoke.The function signature is also defined as the function selector.


## Function Argument
The function’s arguments, encoded according to the rules for the various elementary types defined in the ABI specification.

## Function Prototype
A function's prototype is defined as the string containing the function's name, followed by the data types of each of its arguments, enclosed in parentheses and separated by commas.
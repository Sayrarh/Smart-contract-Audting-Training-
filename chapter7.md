### Chapter 7 - Smart Contracts and Solidity
A "smart contract" is a program that runs on the Ethereum blockchain. It is a set of code (its functions) and data (its state) stored at a specific address on the Ethereum blockchain. </br>
Smart contracts, like regular contracts, can define rules and automatically enforce them through code. Smart contracts are inherently irreversible and cannot be deleted by default.
Smart contracts are very logical, following an if this then that structure. This means they behave exactly as programmed and cannot be changed.

There's a quote which states that *A smart contract is as smart as the writer*.

All smart contracts in Ethereum are executed, ultimately, because of a transaction initiated from an EOA. A contract can call another contract that can call another contract, and so on, but the first contract in such a chain of execution will always have been called by a transaction from an EOA.

### Points to note about transactions revert and termination
1. Any changes to the global state caused by a transaction are recorded if it is sent from one EOA to another. 

2. Any changes to the global state are recorded if a transaction is sent from an EOA to a contract that does not invoke any other contracts (e.g. account balances, state variables of the contracts). 

3. If a transaction is sent from an EOA to a contract that only invokes other contracts in a way that propagates errors, then any changes to the global state (e.g. account balances, contract state variables) are recorded.

4. If a transaction is sent from an EOA to a contract that invokes other contracts in a way that does not propagate errors, some changes to the global state may be recorded (e.g. account balances, state variables of the non-erroring contracts), but other changes to the global state are not recorded (e.g. state variables of the erroring contracts). If a transaction is reverted, all of its effects (state changes) are "rolled back" as if the transaction never occurred. A failed transaction is still recorded as attempted, and the ether spent on gas for the execution is deducted from the originating account, but it has no other consequences for the contract or account state.
</br>
To deploy a smart contract on the Ethereum network, it must first be compiled into bytecode that the Ethereum Virtual Machine can understand (EVM). This is accomplished with the help of a Solidity compiler such as Solc. The compiled bytecode is then deployed to the Ethereum blockchain, along with the Application Binary Interface (ABI) that defines the contract's functions and variables.

### Smart Contracts ABI(Application Binary Interface)
An ABI specifies how machine code accesses data structures and functions. An ABI's purpose is to define the functions that can be invoked in the contract and to describe how each function will accept arguments and return its result.


### Solidity as a programming language for writing smart contracts

Solidity is an object-oriented, high-level programming language used to implement smart contracts. Solidity is statically typed and, among other things, supports inheritance, libraries, and complex user-defined types.
Solidity was created by Dr. Gavin Wood.</>

### Layout of a Solidity file
A Solidity source file's layout can include an arbitrary number of pragma directives, import directives, and struct/enum/contract definitions. The best practices for contract layout are as follows: </br>
State variables</br>
Events</br>
Modifiers</br>
Constructors, and </br>
Functions. </br>

### Data Types in Solidity
1. Value Types: are types that are passed by value, i.e. they are always copied when they are used as function arguments or in assignments e.g.  Booleans, Integers, Fixed Point Numbers, Address, Contract, Fixed-size Byte Arrays (bytes1, bytes2, …, bytes32), Literals (Address, Rational, Integer, String, Unicode, Hexadecimal), Enums, Functions.

2. Reference Types:They store a reference to where the actual data is stored. Arrays (including dynamically-sized bytes array bytes and strings), Structs, and Mappings are all supported. Every reference type has an additional instance indicating where the data is stored.

### Variable Types in Solidity
1. State Variables: These are variables defined outside of a function. State variables store data permanently on the blockchain. It is costly because it deals with the Ethereum blockchain storage.

2. Local Variables: These are variables declared inside a function, and values declared inside the function cannot be accessed from outside of the function. It is not stored on the blockchain.

3. Global Variables: These are variables that retrieve information about the blockchain, e.g., msg.sender, msg.sig, and msg.value.


### Function Mutability in Solidity
1. View: View functions can read but not modify contract state.
2. Pure: Pure functions cannot read or modify contract state. All data relevant to the pure function is either passed in or declared in the scope of the function. 
3. Payable: This function can be used to receive ether when called and can also read and write to the blockchain state.
4. Non-payable(default): This function can only read and write into the blockchain state but can’t accept ether. </br>

<b>Note</b>: If the behavior of a function is not specified, it will read and modify the state of the block chain by default.


#### Function Modifiers
They allow you to change the behavior of functions declaratively. For example, you can use a modifier to check a condition before executing a function. The control flow of the function continues after the "_" in the preceding modifier. Multiple modifiers are applied to a function in the order presented by specifying them in a whitespace-separated list. If the modifier chooses not to execute the function body, the return variables are set to their default values, just as if the function had an empty body. The symbol can appear multiple times in the modifier. The function body replaces each occurrence. </br>

#### Constructor Function
When a contract is created, its constructor (a function declared with the constructor keyword) is executed once. A constructor is optional and only one constructor is allowed.

# Chapter 13 - The Ethereum Virtual Machine
The Ethereum Virtual Machine (EVM) is the component of Ethereum that handles smart contract deployment and execution. Simple value transfer transactions from one EOA to another do not require it, but everything else will require a state update computed by the EVM. At its most basic, the EVM running on the Ethereum blockchain can be viewed as a global decentralized computer containing millions of executable objects, each with its own permanent data store.
</br>

The EVM is a quasi-Turing-complete state machine; "quasi" because the amount of gas available for any given smart contract execution limits all execution processes to a finite number of computational steps. As a result, the halting problem has been "solved" (all program executions will halt) and the situation where execution might fail has been avoided.
</br>
The EVM has a stack-based architecture, storing all in-memory values on a stack. 
</br>
The job of the EVM is to update the Ethereum state by computing valid state transitions as a result of smart contract code execution, as defined by the Ethereum protocol. 

### Stack operations
Stack, memory, and storage management instructions:

POP     //Remove the top item from the stack </br>
MLOAD   //Load a word from memory </br>
MSTORE  //Save a word to memory </br>
MSTORE8 //Save a byte to memory </br>
SLOAD   //Load a word from storage </br>
SSTORE  //Save a word to storage </br>
MSIZE   //Get the size of the active memory in bytes </br>
PUSHx   //Place x byte item on the stack, where x can be any integer from
        // 1 to 32 (full word) inclusive </br>
DUPx    //Duplicate the x-th stack item, where x can be any integer from
        // 1 to 16 inclusive </br>
SWAPx   //Exchange 1st and (x+1)-th stack items, where x can be any
        // integer from 1 to 16 inclusive
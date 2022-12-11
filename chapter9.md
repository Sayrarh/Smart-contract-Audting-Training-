# Chapter 9 - Smart Contract Security
Smart contracts are self-executing programs that run on a blockchain and handle the automatic execution of the terms and conditions of a contract. Because they are immutable and cannot be changed once deployed, they must be secure and free of errors or vulnerabilities. </br>

A smart contract, like any other program, will do exactly what is written, which is not always what the programmer intended. Furthermore, all smart contracts are open to the public, and any user can interact with them by simply initiating a transaction. Any vulnerability can be exploited, and losses are almost always unrecoverable. As a result, it is critical to adhere to best practices and employ time-tested design patterns.

## Security Best Practices
Here are some best practices for ensuring the security of your smart contracts:

1. Minimize the complexity of your smart contracts: The more complex a smart contract is, with more lines of code and more "features," the more likely it is to contain bugs or have unforeseen effects.

2. Avoid reinventing the wheel and instead try to reuse existing libraries and contracts whenever possible.

3. Ensure that the smart contract is of high quality and free from errors.

4. Smart contract code should be clear and easy to read in order to make it easier to audit.

5. Thorough testing of smart contract code.


##  Security risks and antipatterns in smart contract programming.
####  Reentrancy
Reentrancy refers to the ability of smart contracts to call and utilize code from other external contracts. This can be exploited by attackers, who can force contracts to execute further code, including calls back into themselves. The was used in the DAO Hack.

#### The Vulnerability
Reentrancy occurs when a contract sends ether to an unknown address and an attacker creates a contract at that address with malicious code in the fallback function. When the vulnerable contract sends ether to this address, the malicious code is executed, allowing the attacker to perform unexpected operations on the vulnerable contract. This is known as reentrancy because the external malicious contract calls a function on the vulnerable contract and the path of code execution "reenters" it.
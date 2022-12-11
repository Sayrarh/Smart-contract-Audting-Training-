# Review Of Five Topics Of Secureum Solidity 201
## 1. Address Zero Checks
Address(0), which is 20 bytes of zeros, is treated differently in Solidity contracts because the private key corresponding to this address is unknown. Ether and tokens sent to this address are unrecoverable, and assigning access control roles to this address is also ineffective (no private key to sign transactions). As a result, zero addresses should be used with caution, and checks for user-supplied address parameters should be implemented.

## 2. OpenZeppelin Counters
These counters can only be increased or decreased by one. This can be used to track the number of elements in a mapping, issue ERC721 ids, or count request ids, among other things. Functions include:

uint256 current(struct Counters.Counter counter) </br>

increment(struct Counters.Counter counter) </br>

decrement(struct Counters.Counter counter) </br>

```
// SPDX-License-Identifier: MIT
// OpenZeppelin Contracts v4.4.1 (utils/Counters.sol)

pragma solidity ^0.8.0;

library Counters {
    struct Counter {
        uint256 _value; // default: 0
    }

    function current(Counter storage counter) internal view returns (uint256) {
        return counter._value;
    }

    function increment(Counter storage counter) internal {
        unchecked {
            counter._value += 1;
        }
    }

    function decrement(Counter storage counter) internal {
        uint256 value = counter._value;
        require(value > 0, "Counter: decrement overflow");
        unchecked {
            counter._value = value - 1;
        }
    }

    function reset(Counter storage counter) internal {
        counter._value = 0;
    }
}
```

## 3. Storage Layout Packing
 The size in bytes of each state variable is determined by its type. If possible, multiple, contiguous items that require less than 32 bytes are packed into a single storage slot according to the following rules:</br>

Lower-order aligned storage is used for the first item in a storage slot. </br>

Value types use only the bytes required to store them.</br>

If a value type does not fit in the remaining space in a storage slot, it is stored in the following storage slot.

```
/ SPDX-License-Identifier: MIT
// OpenZeppelin Contracts v4.4.1 (utils/Counters.sol)

pragma solidity ^0.8.0;

contract SlotPacking{
    uint8 num; //slot 0 (takes 1 byte)
    uint64 a; //slot 0 (takes another 8 bytes)
    address admin; //slot 0 (takes 20 bytes)
    uint256 num2; //slot 1 (takes whole 32 bytes)
}
```

## 4. Library Restrictions
 In comparison to contracts, libraries are restricted in the following ways:

They cannot have state variables
</br>
They cannot inherit nor be inherited
</br>
They cannot receive Ether
</br>
They cannot be destroyed
</br>
It can only access state variables of the calling contract if they are explicitly supplied (it would have no way to name them, otherwise)
</br>
Library functions can only be called directly (i.e. without the use of DELEGATECALL) if they do not modify the state (i.e. if they are view or pure functions), because libraries are assumed to be stateless.


## 5. EVM Storage
 Storage is a key-value store that maps 256-bit words to 256-bit words and can be accessed using the SSTORE/SLOAD instructions in EVM. All storage locations are reset to zero.
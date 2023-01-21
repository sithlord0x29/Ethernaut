Claim ownership of the contract below to complete this level.

https://www.notonlyowner.com/ethernaut/telephone-challenge-solution/

-Up until now, we've only seen and used msg.sender to reference the caller's address.
-public functions can be called both from 'outside' the blockchain (i.e. from an externally owned account) 
or 'inside' the blockchain (from another contract's code)
-all transactions are originated by an EOA, contracts can send messages to each other, those messages being all 
included in the same transaction
-msg.sender references the actual caller (the last caller in the call chain) of the function
-tx.origin indicates the address of the EOA that gave origin to the whole transaction.

Example: EOA 'A' alls a function in contract 'B' which calls a function in contract 'C'
-This super complex call chain results in: A -> B -> C
-In B's code: tx.origin ('A') and msg.sender ('A') would be the same
-In C's code, tx.origin ('A') and msg.sender ('B') would be different

Solution:
-to become the owner of Telephone, an attacker cannot simply call the changeOwner public 
function from his/her EOA. 
-tx.origin would always equal msg.sender (your address), thus the if clause would never be true.
-solution relies on deploying a new 'proxy' contract, controlled by the attacker (us), which will 
be in charge of calling the changeOwner function of Telephone contract and become its 
owner on the attacker's behalf.

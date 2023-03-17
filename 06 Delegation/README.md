The goal of this level is for you to claim ownership of the instance you are given.

Look into Solidity's documentation on the delegatecall low level function, how it works, how it can be used to delegate operations to on-chain libraries, and what implications it has on execution scope.

Fallback methods

Method ids

https://www.notonlyowner.com/ethernaut/delegation-challenge-solution/

- the contract only has one function that we can interact with, which happens to be its fallback function. 
- delegatecall is just another type of message that smart contracts can send to each other - with some peculiarities, but a message at the end of the day  ;
- https://docs.soliditylang.org/en/v0.4.24/introduction-to-smart-contracts.html#delegatecall-callcode-and-libraries
- 

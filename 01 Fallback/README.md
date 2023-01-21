/*
https://solidity-by-example.org/sending-ether/
https://solidity-by-example.org/payable/


~Modifier:~
In Solidity, there is the uncommon instruction _; . _; is used inside a modifier 
to specify when the function should be executed. 

~address(this).balance.~
refers to balance in the address of the Contract. 


https://www.notonlyowner.com/ethernaut/fallback-challenge-solution/
The fallback function

-Transactions made to EOA's do not execute any EVM code (no code)
-However, contracts do have code, so transactions made to them do execute code
-In every Ethereum transaction, there's a field called 'data'
-'data' field specifies the function to be executed with the necessary parameters
-otherwise EVM would have no idea of what do we want to do with that contract
-send empty data field (no functions, no arguments):
  a) gnomes open this transaction, match the 'data' field to the functions defined in the contract
  b) find out that the data field does not match to any function known in the contract, 
  they just try to fallback to the fallback function
  c) fallback function must be defined so it can 'store' to contract balance, otherwise reverted 100%

https://stermi.medium.com/ethernaut-challenge-1-solution-fallback-23ee62909b39

-Solidity compiler version used is < 0.8.x. 
This mean that the contract would be prone to math underflow and overflow bugs
OpenZeppelin SafeMath library (only needed with Solidity < 0.8)

-This contract is importing and using OpenZeppelin SafeMath library, but they are not using it
There is still no way to exploit it by overflow













*/

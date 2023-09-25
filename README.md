## Ownership Contract
This Solidity program is a simple ownership contract that demonstrates the basic syntax and functionality of ownership control in Solidity. It allows the owner of the contract to have exclusive access to certain functions, which can be used to implement access control in smart contracts.

## Description:

This Solidity program is a simple ownership contract that demonstrates the basic syntax and functionality of ownership control in Solidity.. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to get a feel for how to implement ownership control in their smart contracts.The contract has three functions: onlyOwner(), onwerHere(), and Owner(), which can only be called by the owner of the contract.

## Brief code Explanation
The code you provided is a simple Solidity contract that implements ownership. It has one state variable, owner, which stores the address of the current owner of the contract.

The constructor of the contract sets the owner state variable to the address of the deployer of the contract. This means that the person who deploys the contract is automatically the owner.

The contract has three functions:

onlyOwner(): This function can only be called by the owner of the contract. It uses the msg.sender variable to check the address of the caller and reverts if the caller is not the owner.

onwerHere(): This function is similar to onlyOwner(), but it uses an if statement instead of a require() statement. This means that the function will revert if the caller is not the owner, but it will also return normally if the caller is the owner.

Owner(): This function uses the assert() statement to check the address of the caller and reverts if the caller is not the owner.
The assert() statement is stronger than the require() statement in that it will cause the contract to revert even if the contract is running out of gas. This means that the Owner() function is guaranteed to revert if the caller is not the owner, even if the contract is running out of gas.

Overall, this contract is a simple example of how to implement ownership in Solidity. It can be used as a starting point for more complex contracts that need to restrict certain functions to the owner of the contract.

## Getting Started:
### Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., OwnershipContract.sol). Copy and paste the following code into the file:

``` javaScript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract OwnershipContract {
    address public owner;

    constructor() {
        owner = msg.sender;
    }

    function onlyOwner() public view {
        require(msg.sender == owner, "Only the owner can call this function.");
    }

    function onwerHere() public view {
        if(msg.sender!= owner){
            revert("The caller is not the owner.");
        }
    }

    function Owner() public view {
        assert(msg.sender == owner);
    }
}
``` 
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile OwnershipContract.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "OwnershipContract" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can try calling the onlyOwner(), onwerHere(), and Owner() functions to see how they work. However, keep in mind that only the owner of the contract will be able to call these functions successfully.

## Authors 

Dhanush KM

dhamushkm@gmail.com

## License
This project is licensed under the MIT License - see the LICENSE.md file for details

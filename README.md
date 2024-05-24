# MyToken Project

## Project Title
MyToken - Solidity Beginner Assessment

## Description
MyToken is a basic implementation of a cryptocurrency token using Solidity, the programming language for Ethereum smart contracts. This project provides a foundational understanding of how to create, mint, and burn tokens on the Ethereum blockchain. It includes functionalities to manage a token's supply and track balances associated with different addresses.

## Getting Started

### Installing
To get started with the MyToken project, you'll need the following:

1. **Solidity Compiler**: Ensure you have Solidity installed on your machine. You can download it from [Solidity's official website](https://soliditylang.org/).
2. **Remix IDE**: This is an online tool that helps write, compile, and deploy smart contracts. You can access it at [Remix IDE](https://remix.ethereum.org/).

### Executing Program

1. **Open Remix IDE**: Navigate to [Remix IDE](https://remix.ethereum.org/).
2. **Create a New File**: In the file explorer, create a new file named `MyToken.sol`.
3. **Paste the Code**: Copy and paste the following Solidity code into `MyToken.sol`:

    ```solidity
    // SPDX-License-Identifier: MIT
    pragma solidity 0.8.18;

    contract MyToken {

        // public variables here
        string public tokenName = "META";
        string public tokenAbbrv = "MTA";
        uint public totalSupply = 0;

        // mapping variable here
        mapping(address => uint) public balances;

        // mint function
        function mint (address _address, uint _value) public {
            totalSupply += _value;
            balances[_address] += _value;
        }

        // burn function
        function burn (address _address, uint _value) public {
            if (balances[_address] >= _value) {
                totalSupply -= _value;
                balances[_address] -= _value;
            }
        }    
    }
    ```

4. **Compile the Contract**: Click on the "Solidity Compiler" tab on the left panel and then click the "Compile MyToken.sol" button.
5. **Deploy the Contract**: Navigate to the "Deploy & Run Transactions" tab. Ensure the environment is set to "JavaScript VM" and click "Deploy".
6. **Interact with the Contract**: After deployment, you'll see the deployed contract under "Deployed Contracts". Expand it to view and interact with the `mint` and `burn` functions.

### Help
If you encounter issues while deploying or interacting with the contract, consider the following steps:

- **Ensure Solidity Version**: Verify that the Solidity version specified (`0.8.18`) matches the version in Remix IDE settings.
- **Check Gas Limit**: Ensure you have enough gas limit set in your environment settings.
- **Use Correct Address**: When calling functions, ensure that the addresses used are valid and have sufficient permissions.

For additional help, refer to Remix IDE's documentation or Solidity's official documentation.

### Authors
- **Dominique Pizzie** - @DomPizzie
- **[Your Name]** - @[YourGitHubHandle]

### License
This project is licensed under the MIT License - see the LICENSE.md file for details.

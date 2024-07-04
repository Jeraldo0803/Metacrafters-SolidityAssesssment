# Metacrafters-SolidityAssesssment
This Solidity program is submitted as a requirement for Metacrafter's ETH Solidity Beginner Course.

## Getting Started
### Executing / Running the Program
You can use the online Solidity IDE named Remix, you can find it here: https://remix.ethereum.org/
Make a new file and copy paste the content of the "MyTokenFile.sol".

Compile the code, on the left side of the screen, with the icon named `Solidity Compiler`. Compile and then run.
After that, go to `Deploy & Run Transactions` tab and press `Deploy` on the Contract `MyToken` as named in the run file.
From there, scroll down and go to `Deployed Contracts`, there should a dropdown that shows the defined and then experiment with different values to mint and burn.

### The Code
Here is the code snippet of the contract under `MyTokenFile.sol`.
```
contract MyToken {

    // public variables here
    string public tokenName = "META";
    string public tokkenAbbrv = "MTA";
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
There are two functions for this activity `mint()` and `burn()`. For both functions, there are two parameters with the address and, unsigned integer for the value.
The values are mapped from the line `mapping(address => uint) public balances;`.

## Author
Jerald0803

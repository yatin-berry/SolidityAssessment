
# Token Creation
This Solidity program is a simple "Token Creation" program that demonstartes the basic syntax and functionality of Solidity to create contracts and tokens.

## Description

In this, YbToken is a smart contract implemnetd in Solidity. It includes basic functionalities: minting function which wil increase the total supply and burning function which will reduce the the total supply as per the condition. It also includes storing and retrieving token-related information.
## Requiremnets
1. Public Variables
* tokenName: It stores the name of the token.
* tokenAbb: It stores the abbreviation of the token.
* totalSupply: It tracks the total supply of the token.

2. Mapping
* balances: It maps from address to their respective token balances.

3. Mint Function
* It takes two parameters: an address and a value.
* It then increases the total supply by that number and increases the balance of the address by that amount.

4. Burn Function
* It also takes two parameters but works opposite of what mint function do: an address and a value.
* It will then deduct the value from the total supply and from the balace of the address.
* It will have a condition so as to make sure that balance of the amount is greater than or equal to the amount which is to be burned.
## Program Execution
To run this program, we can use Remix, an online Solidity IDE.

In this, three variables are declared for token name, abbreivation and total supply

    // public variables here
    string public tokenName= "Yatin";
    string public tokenAbb = "YA";
    uint public totalSupply = 0;

Mapping stores the balance of each address

    // mapping variable here
    mapping(address => uint)public balances;



Mint function

    function mint(address _add, uint _val) public {
      totalSupply += _val;
      balances[_add] += _val;
    }
Parameters:
* _add: it is for the address to which token will be minted.
* _val: it is for total tokens to be minted.

Functionality:
* Increases the totalSupply by _val.
* Adds _val tokens to the balance of  _add.

Burn function

    function burn(address _add, uint _val) public {
     if (balances[_add] >= _val){
      totalSupply -= _val;
      balances[_add] -= _val;    } 
Parameters:
* _add: it is for the address from which token will be burned.
* _val: it is for total tokens to be burned.

Functionality:
* It will check if the balance of _add is greter than or equal to _val.
* Decreases the totalSupply by _val.
* Deducts _val tokens from the balance of  _add.

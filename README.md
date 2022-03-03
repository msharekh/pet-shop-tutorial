1. Setting up the development environment
1. Creating a Truffle project using a Truffle Box
1. Writing the smart contract
1. Compiling and migrating the smart contract
1. Testing the smart contract
1. Creating a user interface to interact with the smart contract
1. Interacting with the dapp in a browser


# Setting up the development environment

```npm install -g truffle```

```
Truffle v5.5.2 (core: 5.5.2)
Ganache v7.0.1
Solidity v0.5.16 (solc-js)
Node v16.14.0
Web3.js v1.5.3
```

# Creating a Truffle project using a Truffle Box

```
mkdir pet-shop-tutorial

cd pet-shop-tutorial
```
```truffle unbox pet-shop```

## Directory structure¶
The default Truffle directory structure contains the following:

- `contracts`/: Contains the Solidity source files for our smart contracts. There is an important contract in here called `Migrations`.sol, which we'll talk about later.
- `migrations`/: Truffle uses a migration system to handle smart contract deployments. 

    A migration is an additional special smart contract that keeps track of changes.
- `test`/: Contains both JavaScript and Solidity tests for our smart contracts
- `truffle-config.js`: Truffle configuration file

# Writing the smart contract

- Create a new file named `Adoption.sol` in the contracts/ directory.
## Variable setup

```address[16] public adopters;```

## Your first function: Adopting a pet
```js
// Adopting a pet
function adopt(uint petId) public returns (uint) {
  require(petId >= 0 && petId <= 15);

  adopters[petId] = msg.sender;

  return petId;
}
```

## Your second function: Retrieving the adopters¶

```js
// Retrieving the adopters
function getAdopters() public view returns (address[16] memory) {
  return adopters;
}
```

# Compiling and migrating the smart contract

## Compilation

```truffle compile```

```
msh@Meshals-MacBook-Pro pet-shop-tutorial % truffle compile

Compiling your contracts...
===========================
> Compiling ./contracts/Adoption.sol
> Compiling ./contracts/Migrations.sol
> Artifacts written to /Users/msh/development/pet-shop-tutorial/build/contracts
```

# Testing the smart contract
# Creating a user interface to interact with the smart contract
# Interacting with the dapp in a browser

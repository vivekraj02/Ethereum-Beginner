# Project Title
MyToken contract

# Description 
This Solidity smart contract implements a basic token with minting and burning functionalities.

## Table of Contents

- Overview
- Contract Details
- Functions
- Usage
- Contributing
- License

## Overview

The `MyToken` contract allows for the creation of a custom token on the Ethereum blockchain. It includes functionalities for minting new tokens and burning existing tokens based on specific conditions.

## Contract Details

- ***Token Name:*** ether
- ***Token Abbreviation:*** eth
- ***Total Supply:*** 0 (initially)

The contract maintains a mapping of addresses to token balances (`balances`). The total supply (`totalsupply`) is adjusted dynamically through minting and burning operations.

## Functions

### 'mint'

The `mint` function increases the total supply by a specified amount and increases the balance of a specified address.

function mint(address _sender, uint _value) public {
    totalsupply += _value;
    balances[_sender] += _value;
}

### 'burn'
The burn function decreases the total supply by a specified amount and decreases the balance of a specified address, contingent upon the address having sufficient tokens to burn.

function burn(address _sender, uint _value) public {
    if (balances[_sender] >= _value) {
        totalsupply -= _value;
        balances[_sender] -= _value;
    }
}

## Help
To use this contract:
Deploy it on an Ethereum-compatible blockchain.
Use the mint function to create new tokens for a specified address.
Use the burn function to destroy existing tokens from a specified address.
Ensure that the conditions for burning tokens are met to avoid errors.

## Author
***Name:*** Vivek Raj
***Gmail:*** rajvivek9910@gmail.com

## Licence
This project is licensed under the MIT License. See the LICENSE.md file for details.

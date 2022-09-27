---
id: zqeew0p01t41kshyg73fzxm
title: ERC-20
desc: ''
updated: 1655275719274
created: 1655274855444
---
# ERC-20 standard

ref: [zapper.fi](https://learn.zapper.fi/articles/ethereum-101-tokens-and-the-erc-20-standard)

## Overview

The [ERC-20](https://eips.ethereum.org/EIPS/eip-20) standard refers to the smart contract standard that implements most tokens on the Ethereum blockchain. The standard defines a set of criteria and technical conditions that must be present each time the standard is used to build a smart contract to manage tokens.

The greatest benefit to adopting the ERC-20 standard when creating tokens is that it works as a common language across the blockchain, allowing tokens built with the standard to integrate with all programs on the blockchain that "speak" the same language.

All tokens built using the ERC-20 standard have a set of required functions the contract must execute in order to comply with the standard. Each time these functions are executed they return information (like the total number of tokens of this type in existence) and initiate actions (like the transfer of a certain number of tokens to an entity, given that entity’s address and amount).

Each of these functions serve an important purpose in the standard, and each comes with some variables that are important to consider when a developer decides whether or how to implement the standard.
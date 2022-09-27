---
id: c3m8t0ezod4av3gtme57wfw
title: Ethereum
desc: ''
updated: 1661177514062
created: 1655156595719
tags: topic.cryptoasset
---
# [Ethereum](https://www.ethereum.org/)

ref: [MetaMask Support](https://metamask.zendesk.com/hc/en-us/articles/360015489611)

## What is Ethereum?

Ethereum is a public [[blockchain|notes.tutorial.blockchain]] network. Ethereum is a global network that is capable of running programs on the [Ethereum Virtual Machine (aka EVM)](https://ethereum.org/en/developers/docs/evm/). Programs are written for the EVM in a language called [Solidity](https://soliditylang.org/), and the network uses a cryptocurrency, called `ether` (or `ETH`, pronounced "eeth") to compensate the people that maintain the network--and also as a token of value for transactions carried out on the network. 

An essential function of a blockchain network is coordinating the process of agreement between all the nodes in the network regarding whether a transaction is valid or not. The agreement is referred to as consensus, and the process by which it occurs is called a **consensus mechanism**, or consensus protocol. Two different consensus mechanisms are relevant for Ethereum, the first being **Proof of Work (PoW)** and the second **Proof of Stake (PoS)**. In both mechanisms, computers are provided to do the work of verifying the validity of the transactions, and agreeing on them.
- Under **PoW consensus**, actors known as "miners" carry the responsibility of verifying the transactions, creating the blocks, and maintaining the chain. In exchange, these miners are given a reward (in ETH) each time their node is the first to finalize, or mine, a new block; this also incentivizes miners having good-quality equipment and connection speeds, which in turn helps the network.
- With **PoS consensus**, instead of miners, "validators" are the actors ensuring transaction validity and network integrity. In place of costly number-crunching as a security measure, each validator must have staked 32 ETH; that is, deposited it in a smart contract, a kind of computer program that lives on the Ethereum blockchain, with the promise that they will operate their validator according to the rules.

## What is gas?

"Gas" is the unit of measure for how much computational work is required to process transactions and smart contracts on the Ethereum Virtual Machine (EVM). More complex smart contracts, and code, will require more gas to execute.

As of the implementation of Ethereum Improvement Protocol (EIP) 1559 on August 4, 2021, gas calculation was greatly simplified. Essentially, you pay a base fee for every unit of gas, which is burned, or disappears, upon successful completion of the transaction. On top of the base fee, you add a priority fee, again per unit of gas, the value of which depends on how quickly you want the transaction to go through.

A standard transaction sending ETH normally costs 21,000 gas.

## Tokens

Aside from ether, the native currency of the Ethereum network, there are two main types of tokens that get used on Ethereum:
- [[ERC-20|notes.daily.2022-06-13.ethereum.erc20]], which are "fungible" tokens and correspond to what people call "cryptocurrencies"
- [[ERC-721|notes.daily.2022-06-13.ethereum.erc721]], the "non-fungible tokens", the origin of the acronym [NFT](https://ethereum.org/en/nft/).

## Ethereum mainnet, testnets, sidechains and the rest

Ethereum is, in fact, not just one network.
- The Ethereum blockchain and the EVM live and operate on the Ethereum **mainnet**
- There exist a number of **testnets** for Ethereum that are exactly what they sound like, sandboxed versions of the mainnet where ETH has no real value, except to test out applications
- There are many Ethereum-compatible **sidechains** that have been developed, offering users the option to carry out transactions on a separate blockchain, in that chain's native currency, in order to avoid the sometimes-costly EVM and Ethereum mainnet transaction fees
- Users often end up with tokens and NFTs on these sidechains that they can bring back onto Ethereum mainnet through [bridges](https://metamask.zendesk.com/hc/en-us/articles/4836913606683-Field-Guide-to-Bridges).
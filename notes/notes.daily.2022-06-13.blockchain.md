---
id: 70wubcmi0fl35fou7qp0oov
title: Blockchain
desc: ''
updated: 1661177503797
created: 1655156815049
tags: topic.cryptoasset
---
# Blockchain

ref: [MetaMask Support](https://metamask.zendesk.com/hc/en-us/articles/360015489611)

## What is a blockchain?

A blockchain is a type of distributed ledger technology.

Traditionally, a digital database is kept in a specialized computer called a server. This server would be accessed by people who are granted permission to do so; it could be made public, or private, or somewhere in between, but everyone is accessing that same database--it's **centralized**.

A blockchain--and in particular, a **public blockchain**--is, at its core, a different kind of database. The word ledger is used to describe it, and a blockchain is very good at keeping track of assets coming and going, but it can store lots of different kinds of information. However, rather than having this ledger all in one computer (centralized), it's synced across a number of different computers known as **nodes**: it's decentralized or, as it's often called, **distributed**.

All of those nodes are constantly syncing information between each other about transactions on the ledger: assets moving from one address, or account, on the network to another. These transactions are checked against the ledger's history to ensure that they're valid. 
- Once enough nodes have verified a new transaction, it gets confirmed and becomes final.
- After a certain amount of time, or every certain number of transactions, the network will bundle up all those finalized transactions and seal them, using cryptographic software tools, into a **block**. This block is identified with a hash produced by those cryptographic tools.
- The next block will use the previous block's hash as a starting point, and so the entire history of the ledger, and therefore of the network, is linked together in a chain of blocks containing transactions: the **blockchain**.
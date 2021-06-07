---
title: Why do we need the Portal network?
weight: 1.0
attribution:
  -
    name: Piper
    link: https://github.com/ethereum/stateless-ethereum-specs/blob/master/portal-network.md#motivation
---

This effort is motivated by two overlapping goals.

### Full Functionality for Stateless Clients

The core Ethereum protocol is moving towards a "stateless" model of block verification.  Under this model a client will be able to fully verify the execution of a block using a witness.  Such a client would no longer need to keep or maintain any of the Ethereum "state" data.  Such a client is very valuable in the context of the core protocol, as it facilitates a cleaner merge of the Eth1 and Eth2 chains.  

> Additional reading on why stateless is so important to the Eth1/Eth2 merge: https://dankradfeist.de/ethereum/2021/02/14/why-stateless.html)

What is easy to overlook is that such a "stateless" client will be unable to much else without additional infrastructure.  Specifically it would be unable to serve the vast majority of the JSON-RPC apis.  The Portal Network provides this additional infrastructure, allowing stateless clients to also expose the external APIs that support the web3 ecosystem.


### Scalable Lightweight Clients

The term "light client" tends to refer to a client of the existing DevP2P LES network.  This network is designed using a client/server architecture.  The LES network has a total capacity dictated by the number of "servers" on the network.  In order for this network to scale, the "server" capacity has to increase.  This also means that at any point in time the network has some total capacity which if exceeded will cause service degredation across the network.  Because of this the LES network is unreliable when operating near capacity.

The Portal Network aims to solve this problem by designing our networks so that each additional client that joints the network adds additional capacity to the network.  The end result *should* be a network which becomes more robust and powerful as more nodes join the network.

> Additional reading: https://snakecharmers.ethereum.org/the-winding-road-to-functional-light-clients/
> 
> Additional watching: https://www.youtube.com/watch?v=MZxqRs_tLNs

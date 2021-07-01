# SmartPubSub@IPFS
A Content-based PubSub middleware over IPFS content routing

- Pedro Agostinho | Master Thesis
- College: [Universidade de Lisboa, Instituto Superior Técnico](https://tecnico.ulisboa.pt)
- Advisors: 
  - Luís Veiga
  - David Dias

## Abstract
The InterPlanetary File System (IPFS) is a hypermedia distribution protocol, addressed by content and identities. IPFS enables the creation of completely distributed applications. One of the most efficient and effective ways to distribute information is through the use of notifications or other methods which involve a producer of content (publisher) that shares content with other interested parts (subscribers). Currently, IPFS has a simple working implementation of a pub/sub system under an experimental flag. This implementation relies on a simple network flood and as such is quite inefficient and costly. The goal for this work is to develop a content-based pub/sub system (with subscriptions based on predicates about event content) to disseminate information on top of
IPFS, in an efficient and decentralized way.

## System Overview
This system tries to implement two content-based pubsub protocols over IPFS. Our interaction with a IPFS node is made with the kadDHT, more in particular with its routing table. These two protocols are:
- ScoutSubs, where we have a rendezvous/filtering pubsub solution, completely decentralized.
- FastDelivery, where event dissemination is centralized at each publisher.

## Implementation
[PubSub Implementation](https://github.com/pedroaston/contentpubsub) - implemented in golang

## Evaluation
[Test Plan](https://github.com/pedroaston/contentps-test) - repo that contains all test plans used in testground to evaluate the pubsub

## Project Calendar
- July 
- - Scale up evaluation 
- - Last fixes and optimizations
- - Writing thesis

- August 
- - Writing thesis

- September
- - Writing thesis

- October
- - Deliver thesis
- - Prepare presentation

- November
- - Defend thesis
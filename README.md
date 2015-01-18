# SecComm

Main repository for the SecComm Client.
_______________

## Introduction
SecComm is a secured open-source peer-to-peer client, primarily for the use as a means of secure communication in a novel way.

At the moment it's a proof-of-concept demonstrating a new way to combine pre-existing technologies to build a reliable, resilient, robust, and ultimately trustworthy method of communicating.

## Basic Theory
SecComm combines a traditional peer-to-peer network with a peer-to-infrastructure subsection. It uses the concept of layering request envelopes much in the same way *TOR* operates, combine that with the *Blockchain* concept borrowed from the Crypto-currency world we aim to add the notion of trust to secure messaging.

Clients are all evaluated for their likeness to distributed binary versions of the client, that is, has the client been modified. Along with checksums on a per-message basis evaluated by disparate peers, much in the same way a Bitcoin transaction is evaluated. This modular approach to infrastructure design allows us to essentially pipe several-many trust building functions into the message pipeline as the end-users feel necessary.

We feel it unnecessary to stay with traditional methods of authentication and *accounts*, rather preferring to use the idea that ID's can be picked up and discarded freely, the *orchestration server* (peer-to-infrastructure) serves only to ensure that ID's are never re-used by differing clients [This requires specifying further]. 

### Security
Initially our message envelopes are encrypted using [libsodium](https://github.com/jedisct1/libsodium), the subsequent wrapping envelopes follow the [TOR Specification](https://gitweb.torproject.org/torspec.git/tree/tor-spec.txt) to facilitate the movement of data between end-users via their peers.

Messages never go via any central server, they are only stored locally (each participant will be notified if a user has this option selected). [Fleshed out in [Security](SECURITY.md)] 

The source code for the client and the orchestration server will be open-sourced in it's entirety welcoming peer-review, scrutiny, and of course pull-requests!

### Rationale
There are many Peer-To-Peer messaging services, the large majority as far as we could tell were protocols and specifications. Such projects focus on how the message gets from A to B, they offer little comfort in HOW the client is designed, they offer very little in the way of assurance to users participating. We feel it would be beneficial to keep everyone aware of the playing field. There are messaging services that prevent MITM attacks in various ways, but rarely do they inform users. Our infrastructure inherently seeks out assurances that messages were not tampered with in their transmission. Asymmetric keys are used to initially encrypt the messages in a two-way environment, each key washed with the ID and client.  
 
By utilizing methods such as Diffie-Hellman key exchanging, checksum validation by disparate and objective third party peers, and the burden of attaching personal information to publically available ledgers (such as traditional digital accounts) we foresee a remarkably secure and maintainable network.

### Updates
Client versions are transmitted as part of a *user-agent* style string in the message envelope, the *Orchestration Server* uses Github to check and announce the latest versions. With built-in capacity for specific version numbers to be marked unsafe. To ensure optimal security it would be our recommendation that each party participating in the network use the very latest binary distributions, but, in the event that compromising code is released, users will be alerted if any party is using a mis-trusted client.


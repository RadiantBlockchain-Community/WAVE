
# WAVE: A Peer-to-Peer Radiant Blockchain Name System

WAVE is a peer-to-peer naming service built on the Radiant blockchain. It enables direct networking without relying on DNS or any centrally managed name lookup service. WAVE offers human-readable names for payments, hostname resolution, and all the functions of DNS with the security and benefits of the Radiant blockchain.

## Table of Contents
1. [Introduction](#introduction)
2. [Name Prefix Tree](#name-prefix-tree)
3. [Transaction Contract](#transaction-contract)
4. [Name Ownership](#name-ownership)
5. [Name Resolution Service](#name-resolution-service)
6. [Updating Zone Records](#updating-zone-records)
7. [Permissions](#permissions)
8. [Localization](#localization)
9. [Calculations](#calculations)
10. [Future Improvements](#future-improvements)
11. [Conclusion](#conclusion)
12. [References](#references)

## Introduction
WAVE addresses the weaknesses of traditional DNS by using a blockchain-based electronic naming system. By leveraging proof-of-work blockchain transactions, WAVE ensures computational impracticality to reverse or forge records, offering a secure alternative to DNS. This system provides speed, efficiency, and flexibility using Radiant's unique reference system.

## Name Prefix Tree
Names are represented as a chain of transactions forming a prefix tree. Each letter is represented as a unique output of a transaction stemming from a root transaction. The system supports 37 characters (a-z, 0-9, and hyphen). Users can extend any node and supply funding inputs to incentivize miners.

## Transaction Contract
The transaction contract consists of:
1. Determining the claim address.
2. Creating at least 38 outputs where the 0th output is the Claim Token, a layer-1 NFT.
3. Ensuring the prefix data structure is repeated at each level for easy verification.

## Name Ownership
Ownership is linked to the private key corresponding to the address in the UTXO representing the Claim Token. Ownership transfers and updates follow a first-in, first-out rule.

## Name Resolution Service
Resolving a name involves traversing the prefix tree from the root transaction to the Claim Token. The resolver service must provide all subsequent spends of the Claim Token to the latest unspent output.

## Updating Zone Records
The system allows attaching arbitrary data to Claim Tokens, enabling flexible zone record updates. Zone records can include keys for addresses, avatars, names, and more.

## Permissions
The system supports hierarchical name management, allowing businesses to delegate control of subdomains while maintaining top-level control.

## Localization
To support Unicode characters, WAVE uses Punycode encoding, converting Unicode to a subset of ASCII (letters, digits, and hyphens).

## Calculations
Bandwidth and storage requirements for resolving names and updates are manageable. For example, a name updated 1,000 times requires approximately 1 MB of data.

## Future Improvements
Potential improvements include reducing storage requirements, exploring alternative encodings, enhancing resiliency against denial of service attacks, and preventing name registration front running.

## Conclusion
WAVE provides a robust, secure, and scalable naming system based on cryptographic proof, offering a superior alternative to DNS. It supports flexible permissions and subdomains, making it suitable for various use cases.

## References
1. Satoshi Nakamoto, "Bitcoin: A Peer-to-Peer Electronic Cash System," 2008. [Bitcoin Whitepaper](https://bitcoin.org/bitcoin.pdf)
2. "Radiant: A Peer-to-Peer Digital Asset System," 2022. [Radiant Whitepaper](https://radiantblockchain.org/radiant.pdf)
3. "DNSSEC: DNS Security Extensions," 1999-. [DNSSEC RFC](https://www.dnssec.net/rfc)
4. "Punycode: A Bootstring encoding of Unicode for Internationalized Domain Names in Applications (IDNA)," 2006. [Punycode Spec](http://www.nicemice.net/idn/punycode-spec.gz)


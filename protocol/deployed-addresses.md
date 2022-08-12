---
description: >-
  This section summarizes all the various deployments of the protocol across the
  various networks.
---

# Deployed Addresses

## Core Protocol Deployment

These are the deployment of the core



| Contract Name                                                                                                          | Addresses                                                                                                                  | Description                                                                                                                               |
| ---------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| [TroveManager](https://github.com/MahaDAO/arth-core/blob/main/packages/contracts/contracts/TroveManager.sol)           | [0xF4eD5d0C3C977B57382fabBEa441A63FAaF843d3](https://etherscan.io/address/0xF4eD5d0C3C977B57382fabBEa441A63FAaF843d3#code) | A helper contract that handles redemptions, liquidations and frontend fees                                                                |
| [SortedTroves](https://github.com/MahaDAO/arth-core/blob/main/packages/contracts/contracts/SortedTroves.sol)           | [0x65334D2A487702292A8E0Ea70faD35Cb3E820A3D](https://etherscan.io/address/0x65334D2A487702292A8E0Ea70faD35Cb3E820A3D)      | A doubly linked list that maintains a list of all loans, ordered according to their current nominal individual collateral ratio (NICR)    |
| [MultiTroveGetter](https://github.com/MahaDAO/arth-core/blob/main/packages/contracts/contracts/MultiTroveGetter.sol)   | [0xB8c776e7aB6e7A85dd5775850042fD3A22538D9D](https://etherscan.io/address/0xB8c776e7aB6e7A85dd5775850042fD3A22538D9D#code) | A helper contract used by the frontend to fetch multiple troves in one call                                                               |
| [CommunityIssuance](https://github.com/MahaDAO/arth-core/blob/main/packages/contracts/contracts/CommunityIssuance.sol) | [0xdac4961f0Ab8f7326D2d8ff75cFA1DBe29d558EC](https://etherscan.io/address/0xdac4961f0Ab8f7326D2d8ff75cFA1DBe29d558EC#code) | An issuance contract that gives out MAHA to stability pool providers across a 30 day period.                                              |
| [Governance](https://github.com/MahaDAO/arth-core/blob/main/packages/contracts/contracts/Governance.sol)               | [0x85daB10c3BA20148cA60C2eb955e1F8ffE9eAa79](https://etherscan.io/address/0x85daB10c3BA20148cA60C2eb955e1F8ffE9eAa79#code) | A settings contract that controls various parameters of the protocol (such as enabling stability fees). Meant to be changed by governance |

All ownership of the `ARTH` contracts is currently set to MahaDAO's governance contracts. To learn more about how governance operates, visit [docs.mahadao.com](https://docs.mahadao.com/)

## Cross Chain Deployments

This section details the various deployments of `ARTH` across various other chains. Holding `ARTH` across various chains poses the risk of the bridged version of `ARTH` becoming unbacked if the bridge gets attacked.

For best security, we recommend using `ARTH` on the Ethereum chain. For low transaction fees, we recommend using `ARTH` on various other chains (such as Polygon or BSC).

Bridged version of `ARTH` are made accessible using [AnySwap](https://anyswap.exchange/)

| Network  | Addresses                                                                                                              |
| -------- | ---------------------------------------------------------------------------------------------------------------------- |
| Ethereum | [0x8cc0f052fff7ead7f2edcccac895502e884a8a71](https://etherscan.io/address/0x8cc0f052fff7ead7f2edcccac895502e884a8a71)  |
| BSC      | ​[0x85daB10c3BA20148cA60C2eb955e1F8ffE9eAa79](https://bscscan.com/token/0x85daB10c3BA20148cA60C2eb955e1F8ffE9eAa79)    |
| Polygon  | [0xe52509181feb30eb4979e29ec70d50fd5c44d590](https://polygonscan.com/token/0xe52509181feb30eb4979e29ec70d50fd5c44d590) |

---
description: >-
  This section summarizes all the various deployments of the protocol across the
  various networks.
---

# Deployed Addresses

## Core Protocol Deployment

These are the deployment addresses of the core smart contracts that represent the ARTH valuecoin. Source code for the various contracts can be found on the [Github Repo](https://github.com/MahaDAO/arth-core).



| Contract Name                                                                                                            | Addresses                                                                                                                  | Description                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| [TroveManager](https://github.com/MahaDAO/arth-core/blob/main/packages/contracts/contracts/TroveManager.sol)             | [0x8b1da95724b1e376aE49FdB67afE33Fe41093af5](https://etherscan.io/address/0x8b1da95724b1e376aE49FdB67afE33Fe41093af5#code) | A helper contract that handles redemptions, liquidations and frontend fees                                                                |
| [BorrowerOperations](https://github.com/MahaDAO/arth-core/blob/main/packages/contracts/contracts/BorrowerOperations.sol) | [0x4c50063f8238deA92c738f23221733A9A6c6888B](https://etherscan.io/address/0x4c50063f8238dea92c738f23221733a9a6c6888b#code) | A helper contract that handles opening, adjusting and closing loans                                                                       |
| [SortedTroves](https://github.com/MahaDAO/arth-core/blob/main/packages/contracts/contracts/SortedTroves.sol)             | [0xD60D7a2a8344D4F635Bf9eA9F8CD015A614c3659](https://etherscan.io/address/0xD60D7a2a8344D4F635Bf9eA9F8CD015A614c3659)      | A doubly linked list that maintains a list of all loans, ordered according to their current nominal individual collateral ratio (NICR)    |
| [MultiTroveGetter](https://github.com/MahaDAO/arth-core/blob/main/packages/contracts/contracts/MultiTroveGetter.sol)     | [0xB66fbAfF0891C11d681eD19B533190e40e9e77C4](https://etherscan.io/address/0xB66fbAfF0891C11d681eD19B533190e40e9e77C4)      | A helper contract used by the frontend to fetch multiple troves in one call                                                               |
| [CommunityIssuance](https://github.com/MahaDAO/arth-core/blob/main/packages/contracts/contracts/CommunityIssuance.sol)   | [0x61274CD1f801B097BE7E5197b158999307893D2e](https://etherscan.io/address/0x61274CD1f801B097BE7E5197b158999307893D2e)      | An issuance contract that gives out MAHA to stability pool providers across a 30 day period.                                              |
| [Governance](https://github.com/MahaDAO/arth-core/blob/main/packages/contracts/contracts/Governance.sol)                 | [0x91eb23B66BeB3467998402BA50AA1C1a98811eB1](https://etherscan.io/address/0x91eb23B66BeB3467998402BA50AA1C1a98811eB1#code) | A settings contract that controls various parameters of the protocol (such as enabling stability fees). Meant to be changed by governance |

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

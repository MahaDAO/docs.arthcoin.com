---
description: >-
  Here we explain about how flash loans work and how ARTH is able to provide 0%
  flashloans
---

# 0% Flash Loans

A flash-loan allows a user to borrow ARTH without the need of collateral. Since these loans are governed by smart contracts which forces a user to payback the loan, the transaction will fail if the principal is not paid back.

Flash loans allow users to borrow large sums of funds without having to have any collateral in hand.

Unlike protocols like Aave which charge a fees to borrowers when they take a flash-loan, ARTH's flash-loan mechanism charges 0% fees. Which means a user can borrow and repay a near infinite supply of ARTH as long as they are able to pay back the loan within the same transaction.

**Example**: This is the first flash loan taken in ARTH: [https://bscscan.com/tx/0x7e272e37f143174fbdb1053ea8ee8ed918b82deebacd05c1b7f5527c864c735a](https://bscscan.com/tx/0x7e272e37f143174fbdb1053ea8ee8ed918b82deebacd05c1b7f5527c864c735a)

## Why use ARTH's 0% flash loans?

There are many use cases with the 0% flash loans. A few of them have been listed below.

* Perform arbitrage across various pairs without having any capital
* Open leveraged long positions on cryptocurrencies using ARTH's lending mechanism

## Governance

All flash loan contracts are controlled by the Governance contract which is governed by MAHA holders. Governance can decide to either:

* Pause the flash loan contract&#x20;
* Change the fee that gets charged (which is currently set at 0%)

To learn more about governance visit the [Governance section.](0-flash-loans.md#governance)

## How to use ARTH flash loans?

Visit the [Github](https://github.com/MahaDAO/flashloans-arth) repository to view an example flash-loan. Use the following lender addresses below for the appropriate network.

**Deployed Lender Addresses:**

* Polygon: [0x9A9c25D9e304ddb284e5a36bE0cdEE0a58Ac3C04](https://polygonscan.com/address/0x9A9c25D9e304ddb284e5a36bE0cdEE0a58Ac3C04)
* Binance Smart Chain: [0x91aBAa2ae79220f68C0C76Dd558248BA788A71cD](https://bscscan.com/address/0x91aBAa2ae79220f68C0C76Dd558248BA788A71cD)

View the [FlashLoanExample.sol](https://github.com/MahaDAO/flashloans-arth/blob/master/contracts/FlashLoanExample.sol) file for an example on how to create a flash-loan contract. The main logic to write where a user can use the flash-loan funds is in the `onFlashLoan` function in [FlashLoanExample.sol#L28-L30](https://github.com/MahaDAO/flashloans-arth/blob/master/contracts/FlashLoanExample.sol#L28-L30).

```
    function onFlashLoan(
        address who,
        uint256 amount,
        uint256 fee,
        bytes calldata data
    ) external override returns (bytes32) {
        require(msg.sender == address(lender), "not lender");
        require(who == address(this), "not contract");

        // Write your logic here
        // make sure that this contract has a balance of (amount + fee) once you're done
        // the (amount + fee) is burnt off for the contract to succeed.

        // Once done, make sure to return this hash to let the lender know it's gone succesfully else the
        // tx will revert
        return keccak256("FlashMinter.onFlashLoan");
    }

```

---
description: >-
  Here we explain about how flash loans work and how ARTH is able to provide
  flashloans
---

# Flash Loans

A flash loan allows a user to borrow `ARTH` without the need for collateral. Since these loans are controlled by smart contracts which force a user to pay back the loan, the transaction will fail if the `ARTH` minted is not paid back in the same transaction.

Flash loans allow users to borrow large sums of funds without having to have any collateral in hand.

**Example**: This is the first flash loan taken in `ARTH`: [https://bscscan.com/tx/0x7e272e37f143174fbdb1053ea8ee8ed918b82deebacd05c1b7f5527c864c735a](https://bscscan.com/tx/0x7e272e37f143174fbdb1053ea8ee8ed918b82deebacd05c1b7f5527c864c735a)

## Why Use ARTH's Flash Loans?

There are many use cases with flash loans. A few of them have been listed below.

* Perform arbitrage across various pairs without having any capital
* Open leveraged long positions on cryptocurrencies using `ARTH`'s lending mechanism

## Governance

All flash loan contracts are controlled by the Governance contract which is governed by MAHA holders. Governance can decide to either:

* Pause the flash loan contract&#x20;
* Change the fee that gets charged (which is currently set at 0.1%)

To learn more about governance visit the [Governance section.](0-flash-loans.md#governance)

## How to use Flash Loans?

Visit the [Github](https://github.com/MahaDAO/flashloans-arth) repository to view an example flash-loan. Use the following lender addresses below for the appropriate network.

View the [ARTHFlashLoanExample.sol](https://github.com/MahaDAO/flashloans-arth/blob/master/contracts/ARTHFlashLoanExample.sol) file for an example of how to create a flash-loan contract. The main logic to writing where a user can use the flash-loan funds is in the `onFlashLoan` function in [ARTHFlashLoanExample.sol#L28-L30](https://github.com/MahaDAO/flashloans-arth/blob/master/contracts/ARTHFlashLoanExample.sol#L28-L30).

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
        return keccak256("ARTHFlashMinter.onFlashLoan");
    }

```

# GamingToken Smart Contract 

## Overview

The GamingToken smart contract is an Ethereum-based ERC-20 token designed for use in gaming applications. It incorporates functionalities such as minting, burning, token transfers, and specific features like redeeming bounties and obtaining power-ups. This contract utilizes the OpenZeppelin library for ERC-20, Ownable, and ERC-20 Burnable implementations.

## Token Details

- **Name:** GAMETOKEN
- **Symbol:** GMT
- **Decimals:** 18

## Contract Features

### Minting

The contract allows the owner to mint new tokens, expanding the token supply. Minting is a privileged operation restricted to the contract owner.

```solidity
function mint(address account, uint256 amount) external onlyOwner
```

### Burning

Token holders can burn their tokens using the `burn` function, reducing the total supply.

```solidity
function burn(uint256 amount) public override
```

### Token Transfer

The contract includes a standard ERC-20 token transfer function.

```solidity
function transferTokens(address recipient, uint256 amount) external
```

### Bounty Redemption

Users can redeem bounties by burning a specified amount of tokens. Three different bounties are available, each requiring a different token amount to redeem.

```solidity
function redeemBounty(uint256 bountyNumber) external
```

### Power-Up Acquisition

Players can obtain power-ups by burning a specific amount of tokens. Each power-up costs 100 tokens.

```solidity
function obtainPowerUp() external
```

### Power-Up Count Inquiry

The contract provides a function to query the number of power-ups a specific gamer has obtained.

```solidity
function getPowerUpCount(address gamer) external view returns (uint256)
```

## Events

The contract emits events for significant operations:

- `Rewarded`: Triggered when a gamer is rewarded with a specified quota.
- `Redeemed`: Triggered when a gamer redeems a bounty.
- `PowerUpObtained`: Triggered when a gamer obtains a power-up.

## Usage

1. **Deployment:**
   - Deploy the contract to the Ethereum blockchain, specifying the initial owner address.

2. **Minting:**
   - The owner can mint new tokens using the `mint` function.

3. **Token Transfers:**
   - Users can transfer tokens using the standard ERC-20 transfer method.

4. **Bounty Redemption:**
   - Users can redeem bounties by calling the `redeemBounty` function with the corresponding bounty number.

5. **Power-Up Acquisition:**
   - Players can obtain power-ups by calling the `obtainPowerUp` function.

6. **Power-Up Count Inquiry:**
   - Use the `getPowerUpCount` function to check the number of power-ups a specific gamer has.

## Author

Anurag 

anilzabade5@gmail.com

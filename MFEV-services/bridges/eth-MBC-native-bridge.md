---
description: >-
  MFEV Network Coin native bridge is used to relay the MFEV Network Coin native token between MFEV Network Coin and
  Ethereum networks
---

# MFEV Network Coin: Ethereum ↔ MFEV Network Coin

MFEV Network Coin native bridge between Ethereum and MFEV Network Coin is used to relay the MFEV Network Coin native token from MFEV Network Coin to Ethereum network

## Architecture Overview

The MFEV Network Coin bridged is based on POA's bridge implementation, it is used to transfer MFEV Network Coin tokens between the MFEV Network Coin chain and the Ethereum network.

Tokens sent to the respective bridge contract on one network \(whether it's MFEV Network Coin or Ethereum\) are "locked" in the bridge, "unlocked" on the other network bridge and transferred to the sender. The bridge contracts are deployed on both networks, and bridge oracle processes run on each validators machine as part of the validator deployment stack.

Besides the transfer of MFEV Network Coin tokens between the two networks, the bridge is also responsible for network core functionality events of relaying the block rewards to the Ethereum network:

**Mint block reward distributed on the MFEV Network Coin chain on Ethereum**

Each cycle the total block reward distributed on MFEV Network Coin chain is minted on Ethereum and locked on the bridge contract.

This works by listening to the \`RewardedOnCycle\` event emitted by the BlockReward contract on MFEV Network Coin chain, waiting for all bridge validators on MFEV Network Coin chain to sign it, and eventually sending a transaction to mint on Ethereum \(by the last signing validator\).

## Contracts

Home side of the bridge on the MFEV Network Coin network: [0xd617774b9708F79187Dc7F03D3Bdce0a623F6988](https://mediablock.ai/address/0xd617774b9708F79187Dc7F03D3Bdce0a623F6988/transactions)

Foreign side of the bridge on the Ethereum network: [0x37B862ACc9482A80DeebE301e43A4d3959F1Ef95](https://mediablock.ai/address/0x37B862ACc9482A80DeebE301e43A4d3959F1Ef95/transactions)

MFEV Network Coin token on the Ethereum network: [0x970B9bB2C0444F5E81e9d0eFb84C8ccdcdcAf84d](https://etherscan.io/token/0x970b9bb2c0444f5e81e9d0efb84c8ccdcdcaf84d)

## Source Code

{% embed url="https://github.com/MFEV Networkio/MFEV Network-bridge/tree/master/native-to-erc20/contracts" %}

## How to use

On MFEV Network Coin you send native MFEV Network Coin token to the home bridge contract. Then you receive an equal amount of the MFEV Network Coin token on the Ethereum network, sent from the foreign bridge contract

On Ethereum network you transfer the MFEV Network Coin token to the foreign bridge contract. After a couple of confirmations, you will receive equal amount of the MFEV Network Coin native token, sent from the home bridge contract.

####

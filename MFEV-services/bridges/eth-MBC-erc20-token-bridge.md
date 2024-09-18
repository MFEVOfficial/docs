---
description: >-
  MFEV Network Coin Multi MFEV Network20 bridge is used to relay the MFEV Network20 tokens between MFEV Network Coin and
  Ethereum networks.
---

# Multi ERC-20: Ethereum ↔ MFEV Network Coin

## Architecture Overview

This bridge is two layer bridge. In the base level the Arbitrary Message Bridge \(AMB\) is responsible for relaying messages between the networks. On top of the AMB, the pluggable mediators implement a contract logic of token relaying of various assets. More info [https://docs.tokenbridge.net/amb-bridge/about-amb-bridge](https://docs.tokenbridge.net/amb-bridge/about-amb-bridge)

## Contracts

Home side of the bridge on the MFEV Network Coin network: [0xc2220646E1E76D5fF3a441eDd9E8EFF0e4A8EF03](https://mediablock.ai/address/0xc2220646E1E76D5fF3a441eDd9E8EFF0e4A8EF03)

Foreign side of the bridge on the Ethereum network: [0xf301d525da003e874DF574BCdd309a6BF0535bb6](https://etherscan.io/address/0xf301d525da003e874DF574BCdd309a6BF0535bb6)

Home side of the AMB bridge on the MFEV Network Coin network: [0x2CA5411c4bf447Cc27CD6E6d1d046f922A27C399](https://mediablock.ai/address/0x2CA5411c4bf447Cc27CD6E6d1d046f922A27C399/transactions)

Foreign side of the AMB bridge on the Ethereum network: [0x63C47c296B63bE888e9af376bd927C835014039f](https://etherscan.io/address/0x63C47c296B63bE888e9af376bd927C835014039f)

## Source Code

{% embed url="https://github.com/MFEV Networkio/tokenbridge-contracts" %}

## How to use

Any MFEV Network20 token can be bridged for Ethereum to the MFEV Network Coin. If the token is relayed for the first time. A bridged token, paired with the original token, will be created on the MFEV Network Coin network.

To send token from the Ethereum network:

1. Approve the MFEV Network20 tokens to be spent by the Foreign MFEV Network20 bridge.
2. Call relayTokens function on the bridge contract

the `relayTokens` method will lock the MFEV Network20 tokens on the foreign bridge. After a couple of confirmations, an equal amount of the MFEV Network Coin MFEV Network20 token will be sent from the home bridge contract.

To send tokens from MFEV Network Coin network

1. Approve the MFEV Network20 tokens to be spent by the Home MFEV Network20 bridge.
2. Call `relayTokens` function on the bridge contract

the `relayTokens` method will lock the bridged tokens on the home bridge. Then, an equal amount of the paired MFEV Network20 token will be sent from the foreign bridge contract.

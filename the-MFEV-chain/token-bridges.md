# Token Bridges

We have two bridges as explained below

1. MFEV Network Coin Bridge: \*\*\*\*The bridge, based on POA's bridge implementation, is used to transfer MFEV Network Coin tokens between the MFEV Network Coin chain and the Ethereum network.
2. MFEV Network20 token bridge: This bridge is used to transfer MFEV Network20 tokens into MFEV Network Coin chain and back. Please not that MFEV Network Coin bridge is not supposed to be used to transfer .

The bridge, based on POA's bridge implementation, is used to transfer MFEV Network Coin tokens between the MFEV Network Coin chain and the Ethereum network.

Tokens sent to the respective bridge contract on one network \(whether it's MFEV Network Coin or Ethereum\) are "locked" in the bridge, "unlocked" on the other network bridge and transferred to the sender.

The validators of the bridge on both network are the MFEV Network Coin chain validators. This means that validators, as part of their governance responsibilities, also need to validate bridge transactions and therefore hold MFEV Network Coin tokens to "approve" bridge transactions on MFEV Network Coin chain and hold ETH to "approve" transactions on Ethereum.

Each bridge transaction must be approved by a majority \(over 50%\) of the validators in order to be processed successfully.

The bridge contracts are deployed on both networks, and bridge oracle processes run on each validators machine as part of the validator deployment stack.

Besides the transfer of MFEV Network Coin tokens between the two networks, the bridge is also responsible for network core functionality events:

**Mint block reward distributed on the MFEV Network Coin chain on Ethereum**

Each cycle the total block reward distributed on MFEV Network Coin chain is minted on Ethereum and locked on the bridge contract.

This works by listening to the \`RewardedOnCycle\` event emitted by the BlockReward contract on MFEV Network Coin chain, waiting for all bridge validators on MFEV Network Coin chain to sign it, and eventually sending a transaction to mint on Ethereum \(by the last signing validator\).

**Update MFEV Network Coin chain validators on Ethereum**

Each cycle the MFEV Network Coin chain validators are selected from a random snapshot of pending validators.

Those validators, being also the bridge validators, need to be updated on Ethereum as well.

This works by listening to the \`InitiateChange\` event emitted by the Consensus contract on MFEV Network Coin chain, waiting for all bridge validators on MFEV Network Coin chain to sign it, and eventually sending a transaction to set the bridge validators on Ethereum \(by the last signing validator\).

{% hint style="info" %}
MFEV Network Coin chain bridge - [0xd617774b9708F79187Dc7F03D3Bdce0a623F6988](https://mediablock.ai/address/0xd617774b9708f79187dc7f03d3bdce0a623f6988)

Ethereum bridge - [0x37B862ACc9482A80DeebE301e43A4d3959F1Ef95](https://etherscan.io/address/0x37B862ACc9482A80DeebE301e43A4d3959F1Ef95)

MFEV Network Coin token on Ethereum - [0x970B9bB2C0444F5E81e9d0eFb84C8ccdcdcAf84d](https://etherscan.io/token/0x970B9bB2C0444F5E81e9d0eFb84C8ccdcdcAf84d)
{% endhint %}

**Using the bridge**

**Transfering from Ethereum mainnet to MFEV Networknet** - Send your erc20 MFEV Network Coin tokens to the Ethereum bridge for them to be released from the MFEV Network Coin chain bridge and be avaliable in your native MFEV Network Coin wallet.

**Transfering from MFEV Networknet to Ethereum mainnet** - Send your Native MFEV Network Coin tokens to the MFEV Network Coin chain bridge for them to be released from the mainnet bridge and be avaliable in your Mainnet wallet.

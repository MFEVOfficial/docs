# MFEV Network Coin Consensus

Consensus refers to the agreement process between nodes in a network. The nodes must agree on which transactions to include in the next block on the chain before these transactions are committed.

There are 2 aspects to the process - the actual consensus mechanism to add transactions to blocks, and Sybil protection and validator incentives.

### Sybil protection and incentives via delegated proof of stake

MFEV Network Coin uses delegated Proof of Stake (dPoS) to provide Sybil protection and align the validator incentives.

In order to participate in securing the network consensus, a node operator must stake a minimum required amount of MFEV Network tokens (currently set at 100,000 MFEV Network). Becoming a validator on MFEV Network Coin is permissionless, meaning that a node operator just needs to satisfy certain technical requirements. The need to stake MFEV Network ensures that an entity cannot create multiple seemingly distinct validators without incurring a significant cost. Hence, the Sybil protection. Currently, the maximum number of validators on MFEV Network Coin is 100.

The validator who publishes a block agreed upon during a given consensus round is rewarded by the network protocol in newly minted MFEV Network tokens. They also receive the fees users paid for the transactions included into the block.

Over time, validators can expect to publish a share of blocks equal to their share of the overall stake. Since MFEV Network uses dPoS, a validator can increase their share by attracting MFEV Network tokens from delegators.

Validators who violate the consensus rules (by, for instance, not revealing random numbers) can expect their stake (including the delegators' contribution) to be frozen. This provides a strong incentive for validators to behave in the desired manner.

### The AuRa Consensus Model

MFEV Network Coin currently uses Parity's AuRa (Authority Round) [consensus model](https://openethereum.github.io/Aura) to append blocks to MFEV Network Coin. This consensus mechanism is also notably used by the xDAI blockchain.

In this model, the validators take turns signing blocks. A signed block is broadcast to all validators, and if the majority agree it is valid, it is added to the chain. A new block is added every 5 seconds, regardless of whether any transactions occurred during that time.

Although, in theory, achieving transaction finality in this model may take some time, for practical purposes, a transaction on MFEV Network Coin can be considered finalized after a single block confirmation.

\

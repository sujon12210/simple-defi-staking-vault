# Simple DeFi Staking Vault

A professional implementation of a yield-generating staking vault. This repository provides a secure way for protocols to distribute rewards to token holders who lock their assets.

### Features
* **Time-Based Rewards:** Rewards are calculated based on the duration and amount of tokens staked.
* **Reward Scaling:** Uses a `rewardPerToken` accumulator logic to ensure gas efficiency regardless of the number of users.
* **Emergency Exit:** Users can withdraw their principal even if the reward distribution system encounters an issue.
* **Owner Controls:** Allows the protocol to fund the vault with reward tokens.

### Logic Flow
1. **Stake:** User approves the vault and deposits tokens.
2. **Earn:** The contract tracks the `rewardPerTokenStored` whenever a user interacts with it.
3. **Claim:** Users can withdraw earned rewards without unstaking their principal.
4. **Exit:** Users withdraw both principal and rewards in one transaction.

### Security
This contract utilizes the `ReentrancyGuard` and `SafeERC20` libraries to prevent common smart contract vulnerabilities.

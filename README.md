# RFP41---Debt-Token
Debt token proposal for Radiant hack reimbursement

Abstract

RFP Idea-47 proposes the issuance of a debt token to address the financial losses Radiant incurred from lending pool exploits on both BSC and Arbitrum.

Motivation and Rationale

On October 16, 2024, Radiant suffered a sophisticated security breach, resulting in the loss of over $50 million in user assets. While the team collaborates with authorities to retrieve funds, an immediate solution is necessary to fairly compensate users and restore confidence as the protocol restarts. This debt token proposal aims to efficiently facilitate repayment to users.

Useful Links
Announcement: x.com/RDNTCapital/status/1846634050100039881
Post-mortem: x.com/RDNTCapital/status/1847121278974480779
AMA: https://x.com/i/spaces/1ZkKzRyLRpNKv/peek

Specifications

Token Distribution: 
Users with impacted deposits and other contract approval associated losses would receive debt tokens (DBT) on a 1:1 basis ($1 USD loss = 1 DBT). 
The amount will be dictated by snapshot, after which no approval associated losses can be repaid retroactively that were not a part of snapshot.

Revenue Allocation: 
A modifiable percentage of protocol revenue would be directed towards debt repayment, with governance voting to adjust this rate as needed. 
The initial amount will be 10% of protocol revenue. 

Liquidity Pool: 
A liquidity pool will be established where users can trade their debt tokens at a discount (< 1:1), enabling immediate capital recovery at a loss. This also allows investors to recapitalize the protocol by purchasing discounted debt tokens, with the expectation of future revenue from the pool.
We recommend Radiant protocol initiate this pool by minting an additional 100k debt tokens to be paired against 100k USDC, sourced either from Radiant funds or by some interested third party.
These debt tokens would not have any claim on repayment, but be used for market making activity. Once the debt tokens have been repaid, these last 100k tokens would be burned and the USDC portion of the pool returned to the owner.


Repayment Mechanism: 
As the protocol generates revenue, it would be directed to one of two places:
If debt tokens are priced <1 USDC: Buys back discounted debt tokens in the secondary market until price is back at 1 DBT / 1 USDC. The bought back DBT is burnt and removed from circulation.
If debt tokens are priced at ≥1 USDC, the remaining revenue will be deposited into a repayment contract from which debt token holders can claim $1 USDC per token, burning the token in the process.
Pro-Rata Distribution
Each deposit into the repayment contract will be allocated equally across all outstanding tokens
This prevents large holders from gaining unfair advantages in the redemption process

This will continue until all outstanding DBT is removed and burnt, and the POL that was initially seeded wound down.

Steps to Implement

Smart contract development and audit
Update revenue routing mechanisms
Develop debt token contracts
Implement repayment pool logic

User verification period
Publish snapshot of affected addresses
Two-week window for users to verify inclusion
Appeals process for missing claims

3. Deployment
Deploy token contracts
Initialize liquidity pool
Begin token distribution
Cost Analysis
Direct Costs:
Smart contract deployment
Security audit
Initial liquidity provision (100k USDC)
Indirect Costs:
10% allocation of future protocol revenue
Operational overhead for management and support
Voting

In Favor: Support for implementing the proposed steps.
Against: Opposition to the implementation of RFP-41.
Abstain: Undecided, but contributing to quorum.


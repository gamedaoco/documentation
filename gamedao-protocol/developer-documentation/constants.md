---
title: Constants
---

The following sections contain the module constants, also known as parameter types. These can only be changed as part of a runtime upgrade. On the api, these are exposed via `api.consts.<module>.<method>`.

- **[control](#control)**

- **[flow](#flow)**

- **[sense](#sense)**

- **[signal](#signal)**


___


## control

### palletId: `PalletId`
- **interface**: `api.consts.control.PalletId`
- **summary**:   The control's pallet id, used for deriving organization treasuries IDs.

### maxMembers: `u32`
- **interface**: `api.consts.control.MaxMembers`
- **summary**:   The max number of members per one org.

### protocolTokenId: `CurrencyId`
- **interface**: `api.consts.control.ProtocolTokenId`
- **summary**:   The CurrencyId which is used as a protokol token.

### paymentTokenId: `CurrencyId`
- **interface**: `api.consts.control.PaymentTokenId`
- **summary**:   The CurrencyId which is used as a payment token.

### minimumDeposit: `Balance`
- **interface**: `api.consts.control.MinimumDeposit`
- **summary**:   The min amount of the deposit which is locked during Org creation (in Protocol tokens).

### stringLimit: `u32`
- **interface**: `api.consts.control.StringLimit`
- **summary**:   The maximum length of a name or cid stored on-chain.

___


## flow

### gameDAOTreasury: `AccountId`
- **interface**: `api.consts.flow.GameDAOTreasury`
- **summary**:   The GameDAO Treasury AccountId.

### minNameLength: `u32`
- **interface**: `api.consts.flow.MinNameLength`
- **summary**:   The min length of a campaign name.

### maxCampaignsPerBlock: `u32`
- **interface**: `api.consts.flow.MaxCampaignsPerBlock`
- **summary**:   The max number of campaigns per one block.

### maxCampaignContributors: `u32`
- **interface**: `api.consts.flow.MaxCampaignContributors`
- **summary**:   The max number of contributors per one Campaign.

### maxContributorsProcessing: `u32`
- **interface**: `api.consts.flow.MaxContributorsProcessing`
- **summary**:   The max number of contributors for processing in one block (batch size) during Campaign finalization.

### minContribution: `Balance`
- **interface**: `api.consts.flow.MinContribution`
- **summary**:   The min contribution amount in payment tokens.

### minCampaignDeposit: `Permill`
- **interface**: `api.consts.flow.MinCampaignDeposit`
- **summary**:   The min campaign deposit - fraction of a target, default 10%.

### protocolTokenId: `CurrencyId`
- **interface**: `api.consts.flow.ProtocolTokenId`
- **summary**:   The CurrencyId which is used as a protokol token.

### paymentTokenId: `CurrencyId`
- **interface**: `api.consts.flow.PaymentTokenId`
- **summary**:   The CurrencyId which is used as a payment token.

### campaignFee: `Permill`
- **interface**: `api.consts.flow.CampaignFee`
- **summary**:   The amount of commission to be paid from the Org treasury to GameDAO treasury after successful Campaign finalization.

### stringLimit: `u32`
- **interface**: `api.consts.flow.StringLimit`
- **summary**:   The maximum length of a name or symbol stored on-chain.

### campaignDurationLimits: `(Self::BlockNumber, Self::BlockNumber)`
- **interface**: `api.consts.flow.CampaignDurationLimits`
- **summary**:   Default time limit for a campaign in blocks.

___


## sense

### stringLimit: `u32`
- **interface**: `api.consts.sense.StringLimit`
- **summary**:   The maximum length of a name or symbol stored on-chain.

___


## signal

### paymentTokenId: `CurrencyId`
- **interface**: `api.consts.signal.PaymentTokenId`
- **summary**:   The CurrencyId which is used as a payment token.

### protocolTokenId: `CurrencyId`
- **interface**: `api.consts.signal.ProtocolTokenId`
- **summary**:   The CurrencyId which is used as a protokol token.

### minProposalDeposit: `Balance`
- **interface**: `api.consts.signal.MinProposalDeposit`
- **summary**:   Min deposit for Proposal creation.

### proposalDurationLimits: `(Self::BlockNumber, Self::BlockNumber)`
- **interface**: `api.consts.signal.ProposalDurationLimits`
- **summary**:   Default time limit for a proposal in blocks.

### gameDAOTreasury: `AccountId`
- **interface**: `api.consts.signal.GameDAOTreasury`
- **summary**:   The GameDAO Treasury AccountId.

### maxMembers: `u32`
- **interface**: `api.consts.signal.MaxMembers`
- **summary**:   Max number of members per organization.

### maxProposalsPerBlock: `u32`
- **interface**: `api.consts.signal.MaxProposalsPerBlock`
- **summary**:   The max number of proposals per one block.

### stringLimit: `u32`
- **interface**: `api.consts.signal.StringLimit`
- **summary**:   The maximum length of a string, stored on chain.

### slashingMajority: `Permill`
- **interface**: `api.consts.signal.SlashingMajority`
- **summary**:   Majority of rejection >= {this value} * eligible voters --> slash deposit (default: 2/3).

### gameDAOGetsFromSlashing: `Permill`
- **interface**: `api.consts.signal.GameDAOGetsFromSlashing`
- **summary**:   This part of slashing goes to GameDAO treasury (default: 1/4).

___


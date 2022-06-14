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

### palletId: `FrameSupportPalletId`
- **interface**: `api.consts.control.palletId`
- **summary**:    The control's pallet id, used for deriving organization treasuries IDs.

### game3FoundationTreasury: `AccountId`
- **interface**: `api.consts.control.game3FoundationTreasury`
- **summary**:    The Game3 Foundation Treasury AccountId.

### gameDAOTreasury: `AccountId`
- **interface**: `api.consts.control.gameDAOTreasury`
- **summary**:    The GameDAO Treasury AccountId.

### maxDAOsPerAccount: `u32`
- **interface**: `api.consts.control.maxDAOsPerAccount`
- **summary**:    The max number of DAOs created per one account.

### maxMembersPerDAO: `u32`
- **interface**: `api.consts.control.maxMembersPerDAO`
- **summary**:    The max number of members per one DAO.

### protocolTokenId: `u32`
- **interface**: `api.consts.control.protocolTokenId`
- **summary**:    The CurrencyId which is used as a protokol token.

### paymentTokenId: `u32`
- **interface**: `api.consts.control.paymentTokenId`
- **summary**:    The CurrencyId which is used as a payment token.

### minimumDeposit: `u32`
- **interface**: `api.consts.control.minimumDeposit`
- **summary**:    The min amount of the deposit which is locked during Org creation (in Protocol tokens).

___


## flow

### gameDAOTreasury: `AccountId`
- **interface**: `api.consts.flow.gameDAOTreasury`
- **summary**:    The GameDAO Treasury AccountId.

### minNameLength: `u32`
- **interface**: `api.consts.flow.minNameLength`
- **summary**:    The min length of a campaign name.

### maxNameLength: `u32`
- **interface**: `api.consts.flow.maxNameLength`
- **summary**:    The max length of a campaign name.

### maxCampaignsPerBlock: `u32`
- **interface**: `api.consts.flow.maxCampaignsPerBlock`
- **summary**:    The max number of campaigns per one block.

### maxContributionsPerBlock: `u32`
- **interface**: `api.consts.flow.maxContributionsPerBlock`
- **summary**:    The max number of contributions per one block.

### maxContributorsProcessing: `u32`
- **interface**: `api.consts.flow.maxContributorsProcessing`
- **summary**:    The max number of contributors for processing in one block (batch size) during Campaign finalization.

### minCampaignDuration: `BlockNumber`
- **interface**: `api.consts.flow.minCampaignDuration`
- **summary**:    The min number of blocks for campaign duration.

### maxCampaignDuration: `BlockNumber`
- **interface**: `api.consts.flow.maxCampaignDuration`
- **summary**:    The max number of blocks for campaign duration.

### protocolTokenId: `u32`
- **interface**: `api.consts.flow.protocolTokenId`
- **summary**:    The CurrencyId which is used as a protokol token.

### paymentTokenId: `u32`
- **interface**: `api.consts.flow.paymentTokenId`
- **summary**:    The CurrencyId which is used as a payment token.

### сampaignFee: `u32`
- **interface**: `api.consts.flow.сampaignFee`
- **summary**:    The amount of comission to be paid from the Org treasury to GameDAO treasury after successfull Campaign finalization.

___


## sense

No constants

___


## signal

TBD (this pallet is under refactoring right now)

---
title: Storage
---

The following sections contain Storage methods are part of the default runtime. On the api, these are exposed via `api.query.<module>.<method>`.

- **[control](#control)**

- **[flow](#flow)**

- **[sense](#sense)**

- **[signal](#signal)**


___


## control

### Orgs(`Hash`): `Org`
- **interface**: `api.query.control.Orgs`
- **summary**:   Org by its id.

### OrgStates(`Hash`): `OrgState`
- **interface**: `api.query.control.OrgStates`
- **summary**:   Org state (Inactive | Active | Locked) by org id.

### Members(`Hash`): `BoundedVec<AccountId>`
- **interface**: `api.query.control.Members`
- **summary**:   Org members list by org id.

### OrgMemberCount(`Hash`): `MemberLimit`
- **interface**: `api.query.control.OrgMemberCount`
- **summary**:   Org members count by org id.

### MemberStates(`(Hash, AccountId)`): `MemberState`
- **interface**: `api.query.control.MemberStates`
- **summary**:   Member state (Inactive | Active ...) by org Hash and member account.

### OrgTreasury(`Hash`): `AccountId`
- **interface**: `api.query.control.OrgTreasury`
- **summary**:   Treasury account of an Org.

### OrgCount: `u32`
- **interface**: `api.query.control.OrgCount`
- **summary**:

___


## flow

### CampaignOf(`Hash`): `Campaign`
- **interface**: `api.query.flow.CampaignOf`
- **summary**:   Campaign by its id.

### CampaignCount: `u32`
- **interface**: `api.query.flow.CampaignCount`
- **summary**:   Total number of campaigns. CampaignCount: u32.

### CampaignBalance(`Hash`): `Balance`
- **interface**: `api.query.flow.CampaignBalance`
- **summary**:   Total contributions balance per campaign.

### CampaignContribution(`(Hash, AccountId)`): `Balance`
- **interface**: `api.query.flow.CampaignContribution`
- **summary**:   Total contribution made by account id for particular campaign. campaign id, account id -> contribution.

### CampaignStates(`Hash`): `CampaignState`
- **interface**: `api.query.flow.CampaignStates`
- **summary**:   Campaign state by campaign id. 0 created, 1 activated, 2 paused, ...

### CampaignsByBlock(`(BlockType, BlockNumber)`): `BoundedVec<Hash>`
- **interface**: `api.query.flow.CampaignsByBlock`
- **summary**:   Campaigns starting/ending in block x.

### CampaignFinalizationQueue(`Hash`): `(Campaign, Balance, CampaignState, AccountId, Contributors)`
- **interface**: `api.query.flow.CampaignFinalizationQueue`
- **summary**:

### ProcessingOffset(`Hash`): `u32`
- **interface**: `api.query.flow.ProcessingOffset`
- **summary**:   Offset value - number of processed and sucessfully finalized contributions. Used during campaign finalization for processing contributors in batches. When MaxContributorsProcessing is achieved, set this offset to save the progress.

### CampaignContributorsCount(`Hash`): `u64`
- **interface**: `api.query.flow.CampaignContributorsCount`
- **summary**:   Total number of contributors for particular campaign. This is needed for voting in order do determine eligible voters for Withdrawal proposal.

___


## sense

### Entities(`AccountId`): `Entity<AccountId>`
- **interface**: `api.query.sense.Entities`
- **summary**:   Sense Entity of the account.

### EntityCount: `u128`
- **interface**: `api.query.sense.EntityCount`
- **summary**:   EntityCount. Increase per each entity creation. EntityCount: u128.

### Properties(`(PropertyType, AccountId)`): `EntityProperty<BlockNumber>`
- **interface**: `api.query.sense.Properties`
- **summary**:   All properties of the account.

___


## signal

### ProposalOf(`Hash`): `Proposal`
- **interface**: `api.query.signal.ProposalOf`
- **summary**:   Proposal by its hash (id).

### ProposalStates(`Hash`): `ProposalState`
- **interface**: `api.query.signal.ProposalStates`
- **summary**:   Proposal's state: Created | Activated | Accepted | Rejected | Expired | Aborted | Finalized.

### ProposalsByBlock(`(BlockType, BlockNumber)`): `BoundedVec<Hash>`
- **interface**: `api.query.signal.ProposalsByBlock`
- **summary**:   Proposals ending in a block.

### ProposalCount: `ProposalIndex`
- **interface**: `api.query.signal.ProposalCount`
- **summary**:

### ProposalVoting(`Hash`): `Voting`
- **interface**: `api.query.signal.ProposalVoting`
- **summary**:

### CampaignBalanceUsed(`Hash`): `Balance`
- **interface**: `api.query.signal.CampaignBalanceUsed`
- **summary**:   The amount of currency that a project has used.

___


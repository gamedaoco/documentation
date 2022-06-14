---
title: Storage
---

The following sections contain Storage methods are part of the default Zero runtime. On the api, these are exposed via `api.query.<module>.<method>`. 

- **[control](#control)**

- **[flow](#flow)**

- **[signal](#signal)**

- **[sense](#sense)**


___


## control
 
### Orgs(`Hash`): `Org`
- **interface**: `api.query.control.Orgs`
- **summary**:    Org by its id.

### OrgByNonce(`u128`): `Hash`
- **interface**: `api.query.control.OrgByNonce`
- **summary**:    Org id by its nonce.

### OrgConfiguration(`Hash`): `OrgConfig`
- **interface**: `api.query.control.OrgConfiguration`
- **summary**:    Org config by its id.

### OrgState(`Hash`): `ControlState`
- **interface**: `api.query.control.OrgState`
- **summary**:    Org state (Inactive | Active | Locked) by org id.

### OrgAccess(`Hash`): `AccessModel`
- **interface**: `api.query.control.OrgAccess`
- **summary**:    Org access model (Open | Voting | Controller) by org Hash (id).

### OrgMembers(`Hash`): `Vec<AccountId>`
- **interface**: `api.query.control.OrgMembers`
- **summary**:    Org members list by org id.

### OrgMemberCount(`Hash`): `u64`
- **interface**: `api.query.control.OrgMemberCount`
- **summary**:    Org members count by org id.

### OrgMemberState(`(Hash, AccountId)`): `ControlMemberState`
- **interface**: `api.query.control.OrgMemberState`
- **summary**:    Member state (Inactive | Active ...) by org Hash and member account.

### Memberships(`AccountId`): `Vec<Hash>`
- **interface**: `api.query.control.Memberships`
- **summary**:   Org list where account is a member.

### OrgCreator(`Hash`): `AccountId`
- **interface**: `api.query.control.OrgCreator`
- **summary**:   Creator account of an Org.

### OrgController(`Hash`): `AccountId`
- **interface**: `api.query.control.OrgController`
- **summary**:   Controller account of an Org.

### OrgTreasury(`Hash`): `AccountId`
- **interface**: `api.query.control.OrgTreasury`
- **summary**:   Treasury account of an Org.

### OrgsCreated(`AccountId`): `Vec<Hash>`
- **interface**: `api.query.control.OrgsCreated`
- **summary**:   Orgs created by account.

### OrgsByCreatedCount(`AccountId`): `u64`
- **interface**: `api.query.control.OrgsByCreatedCount`
- **summary**:   Number of Orgs created by account.

### OrgsControlled(`AccountId`): `Vec<Hash>`
- **interface**: `api.query.control.OrgsControlled`
- **summary**:   Orgs controlled by account.

### OrgsControlledCount(`AccountId`): `u64`
- **interface**: `api.query.control.OrgsControlledCount`
- **summary**:   Number of Orgs controlled by account.

### Nonce: `u128`
- **interface**: `api.query.control.Nonce`
- **summary**:   Nonce. Increase per each org creation.

___


## flow
 
### Campaigns(`Hash`): `Campaign`
- **interface**: `api.query.flow.Campaigns`
- **summary**:   Campaign by its id.

### CampaignOrg(`Hash`): `Hash`
- **interface**: `api.query.flow.CampaignOrg`
- **summary**:   Org id by campaign id.

### CampaignOwner(`Hash`): `AccountId`
- **interface**: `api.query.flow.CampaignOwner`
- **summary**:   Campaign admin (supervision) by campaign id.

### CampaignState(`Hash`): `FlowState`
- **interface**: `api.query.flow.CampaignState`
- **summary**:  Campaign state by campaign id. States: 0 init, 1 active, 2 paused, 3 complete success, 4 complete failed, 5 authority lock.

### CampaignsByState(`FlowState`): `Vec<Hash>`
- **interface**: `api.query.flow.CampaignsByState`
- **summary**:  List of campaign by certain campaign state.

### CampaignsByBlock(`BlockNumber`): `Vec<Hash>`
- **interface**: `api.query.flow.CampaignsByBlock`
- **summary**:   Campaigns ending in block x.

### CampaignsArray(`u64`): `Hash`
- **interface**: `api.query.flow.CampaignsArray`
- **summary**:   Total number of campaigns -> campaign id.

### CampaignsCount: `u64`
- **interface**: `api.query.flow.CampaignsCount`
- **summary**:   Total number of campaigns.

### CampaignsIndex(`Hash`): `u64`
- **interface**: `api.query.flow.CampaignsIndex`
- **summary**:   Campaign id -> total number of campaigns.

### ContributorsFinalized(`Hash`): `u32`
- **interface**: `api.query.flow.ContributorsFinalized`
- **summary**:   	Offset value - number of processed and sucessfully finalized contributions. Used during campaign finalization for processing contributors in batches. When MaxContributorsProcessing is achieved, set this offset to save the progress.

### ContributorsReverted(`Hash`): `u32`
- **interface**: `api.query.flow.ContributorsReverted`
- **summary**:   	Offset value - number of processed and reverted contributions. Used during campaign finalization for processing contributors in batches. When MaxContributorsProcessing is achieved, set this offset to save the progress.

### CampaignsOwnedArray(`Hash`): `u64`
- **interface**: `api.query.flow.CampaignsOwnedArray`
- **summary**:   	Campaign id by org id.

### CampaignsOwnedCount(`Hash`): `u64`
- **interface**: `api.query.flow.CampaignsOwnedCount`
- **summary**:   	Total number of campaigns by org id.

### CampaignsOwnedIndex(`(Hash, Hash)`): `u64`
- **interface**: `api.query.flow.CampaignsOwnedIndex`
- **summary**:   	(org id, campaign id) -> total number of campaigns.

### CampaignsContributed(`AccountId`): `u64`
- **interface**: `api.query.flow.CampaignsContributed`
- **summary**:   	The list of campaigns contributed by account id.

### CampaignsByOrg(`Hash`): `Vec<Hash>`
- **interface**: `api.query.flow.CampaignsByOrg`
- **summary**:   	Campaigns related to an organisation.

### CampaignsContributedArray(`(AccountId, u64)`): `Hash`
- **interface**: `api.query.flow.CampaignsContributedArray`
- **summary**:   	(account id, total number of campaigns contributed by account id) -> campaign id.

### CampaignsContributedCount(`AccountId`): `u64`
- **interface**: `api.query.flow.CampaignsContributedCount`
- **summary**:   	Total number of campaigns contributed by account id.

### CampaignsContributedIndex(`(AccountId, Hash)`): `u64`
- **interface**: `api.query.flow.CampaignsContributedIndex`
- **summary**:   	(account id, campaign id) -> total number of campaigns contributed by account id.

### CampaignBalance(`Hash`): `Balance`
- **interface**: `api.query.flow.CampaignBalance`
- **summary**:   	Total contributions balance per campaign.

### CampaignContribution(`(Hash, AccountId)`): `Balance`
- **interface**: `api.query.flow.CampaignContribution`
- **summary**:   	Total contribution made by account id for particular campaign. (campaign id, account id) -> contribution.

### CampaignContributors(`Hash`): `Vec<AccountId>`
- **interface**: `api.query.flow.CampaignContributors`
- **summary**:   	Campaign contributors by campaign id.

### CampaignContributorsCount(`Hash`): `u64`
- **interface**: `api.query.flow.CampaignContributorsCount`
- **summary**:   	Total number of contributors for particular campaign.

### Nonce(`Hash`): `u128`
- **interface**: `api.query.flow.Nonce`
- **summary**:   	Nonce. Increase per each campaign creation.

___


## signal
 
TBD (this pallet is under refactoring right now)

___


## sense
 
### SenseEntity(`AccountId`): `Entity`
- **interface**: `api.query.sense.SenseEntity`
- **summary**:   Sense Entity of the account.

### SenseXP(`AccountId`): `EntityProperty`
- **interface**: `api.query.sense.SenseXP`
- **summary**:   Experience property of the account.

### SenseREP(`AccountId`): `EntityProperty`
- **interface**: `api.query.sense.SenseREP`
- **summary**:   Reputation property of the account.

### SenseTrust(`AccountId`): `EntityProperty`
- **interface**: `api.query.sense.SenseTrust`
- **summary**:   Trust property of the account.

### Nonce: `u128`
- **interface**: `api.query.sense.Nonce`
- **summary**:   Nonce. Increase per each entity creation.
---
title: Extrinsics
---

The following sections contain Extrinsics methods are part of the default runtime. On the api, these are exposed via `api.tx.<module>.<method>`. 

- **[control](#control)**

- **[flow](#flow)**

- **[sense](#sense)**

- **[signal](#signal)**


___


## control

### create_org(controller_id: `AccountId`, name: `Vec<u8>`, cid: `Vec<u8>`, org_type: `OrgType`, access: `AccessModel`, fee_model: `FeeModel`, fee: `Balance`, gov_asset: `CurrencyId`, pay_asset: `CurrencyId`, member_limit: `u64`, deposit: `Option<Balance>`)
- **interface**: `api.tx.control.create_org`
- **summary**:    Create an on chain organisation. 

   - `origin`: Org creator.
	- `controller_id`: Org controller.
	- `name`: Org name.
	- `cid`: IPFS content identifier.
	- `org_type`: Individual | Company | Dao | Hybrid.
	- `access`: Open (anyone can join) | Voting (membership voting) | Controller (controller invites).
	- `fee_model`: NoFees | Reserve (amount reserved in user account) | 
   Transfer (amount transfered to Org treasury).
	- `fee`: fees amount to be applied to new members based on fee model (in Protocol tokens).
	- `gov_asset`: control assets to empower actors.
	- `pay_asset`: asset used for payments.
   - `member_limit`: max members, if 0 == no limit.
	- `deposit`: initial deposit for the org treasury (in Protocol tokens).

   Emits `OrgCreated` event when successful.

   Weight: `O(1)`

### enable_org(org_id: `Hash`)
- **interface**: `api.tx.control.enable_org`
- **summary**:    Enable Org. 

   Enables an Org to be used and changes it's state to Active.
   Root origin only.

   - `org_id`: Org id (hash). 

   Emits `OrgEnabled` event when successful.

   Weight: `O(1)`

### disable_org(org_id: `Hash`)
- **interface**: `api.tx.control.disable_org`
- **summary**:    Disable Org. 

   Disables an Org to be used and changes it's state to Inactive.
   Root origin only.

   - `org_id`: Org id (hash). 

   Emits `OrgDisabled` event when successful.

   Weight: `O(1)`

### add_member(org_id: `Hash`, account_id: `AccountId`)
- **interface**: `api.tx.control.add_member`
- **summary**:    Add Member to Org.

   - `org_id`: Org id (hash).
   - `account_id`: Account to be added. 

   Emits `AddMember` event when successful.

   Weight: `O(log n)`

### remove_member(org_id: `Hash`, account_id: `AccountId`)
- **interface**: `api.tx.control.remove_member`
- **summary**:    Remove Member to Org.

   - `org_id`: Org id (hash).
   - `account_id`: Account to be removed. 

   Emits `RemoveMember` event when successful.

   Weight: `O(log n)`

### check_membership(org_id: `Hash`)
- **interface**: `api.tx.control.check_membership`
- **summary**:   Checks membership.

   Checks if origin is a member of the Org.

   - `origin`: Account to be checked.
   - `org_id`: Org id (hash).

   Emits `IsAMember` event when successful.

   Weight: `O(1)`

___


## flow

### create_campaign(org_id: `Hash`, admin_id: `AccountId`, name: `Vec<u8>`, target: `Balance`, deposit: `Balance`, expiry: `BlockNumber`, protocol: `FlowProtocol`, governance: `FlowGovernance`, cid: `Vec<u8>`, token_symbol: `Vec<u8>`, token_name: `Vec<u8>`)
- **interface**: `api.tx.control.create_campaign`
- **summary**:   Create campaign.

	- `org_id`: Organisation id.
	- `admin_id`: Campaign admin. Supervision, should be dao provided!
	- `name`: Campaign name
	- `target`: Target balance for the campaign.
	- `deposit`: Initial deposit of the campaign creator.
	- `expiry`: Campaign expiry block number.
	- `protocol`:
	- `governance`:
	- `cid`: IPFS content identifier.
	- `token_symbol`:
	- `token_name`:

   Emits `CampaignCreated` event when successful.

   Weight: `O(1)`

### update_state(campaign_id: `Hash`, state: `FlowState`)
- **interface**: `api.tx.control.update_state`
- **summary**:   Update campaign state.

	- `campaign_id`: Campaign id.
	- `state`: Init | Active | Paused | ... | Finalized.

   Emits `CampaignUpdated` event when successful.

   Weight: `O(1)`

### contribute(campaign_id: `Hash`, contribution: `Balance`)
- **interface**: `api.tx.control.contribute`
- **summary**:   Contribute to project.

	- `campaign_id`: Campaign id.
	- `contribution`: Contribution amount.

   Emits `CampaignContributed` event when successful.

   Weight: `O(1)`

___


## sense

### create_entity(account_id: `AccountId`, cid: `Vec<u8>`)
- **interface**: `api.tx.control.create_entity`
- **summary**:   Create a Sense Entity for the account.

	- `account_id`: Account id.
	- `cid`: IPFS content identifier.

   Emits `EntityInit` event when successful.

   Weight: `O(1)`

### mod_xp(account_id: `AccountId`, value: `Vec<u8>`)
- **interface**: `api.tx.control.mod_xp`
- **summary**:   Modifies an Experience property of the account.

	- `account_id`: Account id.
	- `value`:  increment Experience by this value.

   Emits `EntityMutateXP` event when successful.

   Weight: `O(1)`

### mod_rep(account_id: `AccountId`, value: `Vec<u8>`)
- **interface**: `api.tx.control.mod_rep`
- **summary**:   Modifies a Reputation property of the account.

	- `account_id`: Account id.
	- `value`:  increment Reputation by this value.

   Emits `EntityMutateREP` event when successful.

   Weight: `O(1)`

### mod_trust(account_id: `AccountId`, value: `Vec<u8>`)
- **interface**: `api.tx.control.mod_trust`
- **summary**:   Modifies a Trust property of the account.

	- `account_id`: Account id.
	- `value`:  increment Trust by this value.

   Emits `EntityMutateTrust` event when successful.

   Weight: `O(1)`

___


## signal

TBD (this pallet is under refactoring right now)
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

### create_org(name: `String`, cid: `String`, org_type: `OrgType`, access_model: `AccessModel`, fee_model: `FeeModel`, member_limit: `Option<MemberLimit>`, membership_fee: `Option<Balance>`, gov_currency: `Option<CurrencyId>`, pay_currency: `Option<CurrencyId>`, deposit: `Option<Balance>`)
- **interface**: `api.tx.control.create_org`
- **summary**:   Create an on chain organization

	- `name`:  org name.
	- `cid`:  ipfs content identifier.
	- `org_type`:  individual | company | dao | hybrid.
	- `access_model`: 
	- `fee_model`: 
	- `member_limit`:  max members. default: maxmembers.
	- `membership_fee`: 
	- `gov_currency`: 
	- `pay_currency`: 
	- `deposit`:  initial deposit for the org treasury (in protocol tokens).

	Emits `OrgCreated` event when successful.

	Weight: `O(1)`

### update_org(org_id: `Hash`, prime_id: `Option<AccountId>`, org_type: `Option<OrgType>`, access_model: `Option<AccessModel>`, member_limit: `Option<MemberLimit>`, fee_model: `Option<FeeModel>`, membership_fee: `Option<Balance>`)
- **interface**: `api.tx.control.update_org`
- **summary**:   Update Org

	Allowed origins: Root or prime if OrgType::Individual

	- `org_id`:  org hash.
	- `prime_id`:  new prime id.
	- `org_type`: 
	- `access_model`:  new access model.
	- `member_limit`:  new member limit.
	- `fee_model`:  new fee model.
	- `membership_fee`:  new membership fee.

	Emits `OrgUpdated` event when successful.

	Weight: `O(1)`

### enable_org(org_id: `Hash`)
- **interface**: `api.tx.control.enable_org`
- **summary**:   Enable Org

	Enables an Org to be used and changes it's state to Active.
	Allowed origins: Root or prime if OrgType::Individual

	- `org_id`:  org hash.

	Emits `OrgEnabled` event when successful.

	Weight: `O(1)`

### disable_org(org_id: `Hash`)
- **interface**: `api.tx.control.disable_org`
- **summary**:   Disable Org

	Disables an Org to be used and changes it's state to Inactive.
	Allowed origins: Root or prime if OrgType::Individual

	- `org_id`:  org hash.

	Emits `OrgDisabled` event when successful.

	Weight: `O(1)`

### add_member(org_id: `Hash`, who: `AccountId`)
- **interface**: `api.tx.control.add_member`
- **summary**:   Add Member to Org

	Allowed origins: Root or prime if OrgType::Individual

	- `org_id`:  org id.
	- `who`:  account to be added.

	Emits `MemberAdded` event when successful.

	Weight: `O(log n)`

### remove_member(org_id: `Hash`, who: `AccountId`)
- **interface**: `api.tx.control.remove_member`
- **summary**:   Remove member from Org

	Allowed origins: Root or prime if OrgType::Individual

	- `org_id`:  org id.
	- `who`:  account to be removed.

	Emits `MemberRemoved` event when successful.

	Weight: `O(log n)`

### spend_funds(org_id: `Hash`, currency_id: `CurrencyId`, beneficiary: `AccountId`, amount: `Balance`)
- **interface**: `api.tx.control.spend_funds`
- **summary**:   Make spending from the org treasury

	Allowed origins: Root or prime if OrgType::Individual

	- `org_id`:  org id.
	- `currency_id`:  currency to be spent.
	- `beneficiary`:  receiver account.
	- `amount`:  amount to be spent.

	Emits `FundsSpended` event when successful.

	Weight: `O(1)`

___


## flow

### create_campaign(org_id: `Hash`, admin_id: `AccountId`, name: `BoundedVec<u8, StringLimit>`, target: `Balance`, deposit: `Balance`, expiry: `BlockNumber`, protocol: `FlowProtocol`, governance: `FlowGovernance`, cid: `BoundedVec<u8, StringLimit>`, start: `Option<BlockNumber>`, token_symbol: `Option<BoundedVec<u8, StringLimit>>`, token_name: `Option<BoundedVec<u8, StringLimit>>`)
- **interface**: `api.tx.flow.create_campaign`
- **summary**:

### contribute(campaign_id: `Hash`, contribution: `Balance`)
- **interface**: `api.tx.flow.contribute`
- **summary**:   Contribute to project

	- `campaign_id`: 
	- `contribution`: 

	Emits `CampaignContributed` event when successful.

	Weight: O(1)

___


## sense

### create_entity(account_id: `AccountId`, cid: `BoundedVec<u8, StringLimit>`)
- **interface**: `api.tx.sense.create_entity`
- **summary**:   Create a Sense Entity for the account.

	- `account_id`:  account id.
	- `cid`:  ipfs content identifier.

	Emits `EntityCreated` event when successful.

	Weight: `O(1)`

### update_property(account_id: `AccountId`, property_type: `PropertyType`, value: `u8`)
- **interface**: `api.tx.sense.update_property`
- **summary**:   Modifies a property of the account.

	- `account_id`:  account id.
	- `property_type`:  property type (experience, reputation, trust).
	- `value`:  value to be incremented to property.

	Emits `PropertyUpdated` event when successful.

	Weight: `O(1)`

___


## signal

### proposal(proposal_type: `ProposalType`, org_id: `Hash`, title: `BoundedVec<u8, StringLimit>`, cid: `BoundedVec<u8, StringLimit>`, expiry: `BlockNumber`, majority: `Majority`, unit: `Unit`, scale: `Scale`, start: `Option<BlockNumber>`, quorum: `Option<Permill>`, deposit: `Option<Balance>`, campaign_id: `Option<Hash>`, amount: `Option<Balance>`, beneficiary: `Option<AccountId>`, currency_id: `Option<CurrencyId>`)
- **interface**: `api.tx.signal.proposal`
- **summary**:

### vote(proposal_id: `Hash`, approve: `bool`, deposit: `Option<Balance>`)
- **interface**: `api.tx.signal.vote`
- **summary**:

___


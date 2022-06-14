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

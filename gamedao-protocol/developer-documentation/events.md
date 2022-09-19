---
title: Events
---

Events are emitted for certain operations on the runtime. The following sections describe the events that are part of the default runtime.

- **[control](#control)**

- **[flow](#flow)**

- **[sense](#sense)**

- **[signal](#signal)**


___


## control

### OrgCreated(org_id: `Hash`, creator: `AccountId`, treasury_id: `AccountId`, created_at: `BlockNumber`, realm_index: `u64`)
- **interface**: `api.events.control.OrgCreated.is`
- **summary**:   Org was successfully created.

### OrgEnabled(`Hash`)
- **interface**: `api.events.control.OrgEnabled.is`
- **summary**:   Org was enabled and it's state become Active.

### OrgDisabled(`Hash`)
- **interface**: `api.events.control.OrgDisabled.is`
- **summary**:   Org was disabled and it's state become Inactive.

### MemberAdded(org_id: `Hash`, who: `AccountId`, block_number: `BlockNumber`)
- **interface**: `api.events.control.MemberAdded.is`
- **summary**:   A member has been added to the Org.

### MemberRemoved(org_id: `Hash`, who: `AccountId`, block_number: `BlockNumber`)
- **interface**: `api.events.control.MemberRemoved.is`
- **summary**:   A member has been removed from the Org.

### OrgUpdated(org_id: `Hash`, prime_id: `Option<AccountId>`, org_type: `Option<OrgType>`, access_model: `Option<AccessModel>`, member_limit: `Option<MemberLimit>`, fee_model: `Option<FeeModel>`, membership_fee: `Option<Balance>`, block_number: `BlockNumber`)
- **interface**: `api.events.control.OrgUpdated.is`
- **summary**:

### FundsSpended(org_id: `Hash`, beneficiary: `AccountId`, amount: `Balance`, currency_id: `CurrencyId`, block_number: `BlockNumber`)
- **interface**: `api.events.control.FundsSpended.is`
- **summary**:

___


## flow

### Created(campaign_id: `Hash`, creator: `AccountId`, admin: `AccountId`, target: `Balance`, deposit: `Balance`, expiry: `BlockNumber`, name: `BoundedVec<u8, StringLimit>`)
- **interface**: `api.events.flow.Created.is`
- **summary**:   Campaign was successfully created.

### Activated(campaign_id: `Hash`)
- **interface**: `api.events.flow.Activated.is`
- **summary**:

### Contributed(campaign_id: `Hash`, sender: `AccountId`, contribution: `Balance`, block_number: `BlockNumber`)
- **interface**: `api.events.flow.Contributed.is`
- **summary**:   Campaign was contributed.

### Succeeded(campaign_id: `Hash`, campaign_balance: `Balance`, block_number: `BlockNumber`)
- **interface**: `api.events.flow.Succeeded.is`
- **summary**:   Campaign was finalized.

### Failed(campaign_id: `Hash`, campaign_balance: `Balance`, block_number: `BlockNumber`)
- **interface**: `api.events.flow.Failed.is`
- **summary**:   Campaign failed - successfully reverted.

___


## sense

### EntityCreated(account_id: `AccountId`, block_number: `BlockNumber`)
- **interface**: `api.events.sense.EntityCreated.is`
- **summary**:   New Sense Entity was created.

### PropertyUpdated(property_type: `PropertyType`, account_id: `AccountId`, block_number: `BlockNumber`)
- **interface**: `api.events.sense.PropertyUpdated.is`
- **summary**:   Property was updated.

___


## signal

### Voted(account: `AccountId`, proposal_id: `Hash`, voted: `bool`, yes: `VotingPower`, no: `VotingPower`, vote_power: `VotingPower`)
- **interface**: `api.events.signal.Voted.is`
- **summary**:

### Created(account: `AccountId`, proposal_id: `Hash`, org_id: `Hash`, campaign_id: `Option<Hash>`, amount: `Option<Balance>`, start: `BlockNumber`, expiry: `BlockNumber`)
- **interface**: `api.events.signal.Created.is`
- **summary**:

### Activated(proposal_id: `Hash`)
- **interface**: `api.events.signal.Activated.is`
- **summary**:

### Accepted(proposal_id: `Hash`)
- **interface**: `api.events.signal.Accepted.is`
- **summary**:

### Rejected(proposal_id: `Hash`)
- **interface**: `api.events.signal.Rejected.is`
- **summary**:

### Expired(proposal_id: `Hash`)
- **interface**: `api.events.signal.Expired.is`
- **summary**:

### Aborted(proposal_id: `Hash`)
- **interface**: `api.events.signal.Aborted.is`
- **summary**:

### Finalized(proposal_id: `Hash`)
- **interface**: `api.events.signal.Finalized.is`
- **summary**:

___


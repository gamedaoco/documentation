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
 
### OrgCreated(sender_id: `AccountId`, org_id: `Hash`, treasury_id: `AccountId`, created_at: `BlockNumber`, realm_index: `u64`)
- **interface**: `api.events.control.OrgCreated.is`
- **summary**:    Org was successfully created.

### AddMember(org_id: `Hash`, account_id: `AccountId`, added_at: `BlockNumber`)
- **interface**: `api.events.control.AddMember.is`
- **summary**:    A member has been added to the Org.

### RemoveMember(org_id: `Hash`, account_id: `AccountId`, removed_at: `BlockNumber`)
- **interface**: `api.events.control.RemoveMember.is`
- **summary**:    A member has been removed from the Org.

### IsAMember(org_id: `Hash`, account_id: `AccountId`)
- **interface**: `api.events.control.IsAMember.is`
- **summary**:    Account is a member of the Org.

### OrgUpdated(`AccountId`, `Hash`, `BlockNumber`)
- **interface**: `api.events.control.OrgUpdated.is`
- **summary**:    Org was successfully updated.

### OrgEnabled(`Hash`)
- **interface**: `api.events.control.OrgEnabled.is`
- **summary**:    Org was enabled and it's state become Active.

### OrgDisabled(`Hash`)
- **interface**: `api.events.control.OrgDisabled.is`
- **summary**:    Org was disabled and it's state become Inactive.

### ControllerUpdated(`Hash`, `AccountId`)
- **interface**: `api.events.control.ControllerUpdated.is`
- **summary**:    Controller's state has been changed.

___


## flow

### CampaignDestroyed(campaign_id: `Hash`)
- **interface**: `api.events.flow.CampaignDestroyed.is`
- **summary**:    Campaign was destroyed.

### CampaignCreated(campaign_id: `Hash`, creator: `AccountId`, admin: `AccountId`, target: `Balance`, deposit: `Balance`, expiry: `BlockNumber`, name: `Vec<u8>`)
- **interface**: `api.events.flow.CampaignCreated.is`
- **summary**:    Campaign was successfully created.

### CampaignContributed(campaign_id: `Hash`, sender: `AccountId`, contribution: `Balance`, block_number: `BlockNumber`)
- **interface**: `api.events.flow.CampaignContributed.is`
- **summary**:    Campaign was contributed.

### CampaignFinalized(campaign_id: `Hash`, campaign_balance: `Balance`, block_number: `BlockNumber`, success: `bool`)
- **interface**: `api.events.flow.CampaignFinalized.is`
- **summary**:    Campaign was finalized.

### CampaignFailed(campaign_id: `Hash`, campaign_balance: `Balance`, block_number: `BlockNumber`, success: `bool`)
- **interface**: `api.events.flow.CampaignFailed.is`
- **summary**:    Campaign failed - successfully reverted.

### CampaignReverting(campaign_id: `Hash`, campaign_balance: `Balance`, block_number: `BlockNumber`)
- **interface**: `api.events.flow.CampaignReverting.is`
- **summary**:    Campaign is in the middle of reverting process.

### CampaignFinalising(campaign_id: `Hash`, campaign_balance: `Balance`, block_number: `BlockNumber`)
- **interface**: `api.events.flow.CampaignFinalising.is`
- **summary**:    Campaign is in the middle of finalization process.

### CampaignUpdated(campaign_id: `Hash`, state: `FlowState`, block_number: `BlockNumber`)
- **interface**: `api.events.flow.CampaignUpdated.is`
- **summary**:    Campaign was updated with a new state.

___


## sense

### EntityInit(`AccountId`, `BlockNumber`)
- **interface**: `api.events.control.EntityInit.is`
- **summary**:    New Sense Entity was created.

### EntityMutateXP(`AccountId`, `BlockNumber`)
- **interface**: `api.events.control.EntityMutateXP.is`
- **summary**:    Experience property was updated.

### EntityMutateREP(`AccountId`, `BlockNumber`)
- **interface**: `api.events.control.EntityMutateREP.is`
- **summary**:    Reputation property was updated.

### EntityMutateTrust(`AccountId`, `BlockNumber`)
- **interface**: `api.events.control.EntityMutateTrust.is`
- **summary**:    Trust property was updated.

___


## signal
 
### Proposal(sender_id: `AccountId`, proposal_id: `Hash`)
- **interface**: `api.events.signal.Proposal.is`
- **summary**:    Proposal was successfully created (ex. General proposal).

### ProposalCreated(sender_id: `AccountId`, org_id: `Hash`, campaign_id: `Option<Hash>`, proposal_id: `Hash`, amount: `Balance`, expiry: `BlockNumber`)
- **interface**: `api.events.signal.ProposalCreated.is`
- **summary**:    Proposal was successfully created (ex. Withdrawal proposal).

### ProposalVoted(sender_id: `AccountId`, proposal_id: `Hash`, vote: `bool`)
- **interface**: `api.events.signal.ProposalVoted.is`
- **summary**:     Proposal was voted.

### ProposalApproved(proposal_id: `Hash`)
- **interface**: `api.events.signal.ProposalApproved.is`
- **summary**:     Proposal was approved after the voting.

### ProposalRejected(proposal_id: `Hash`)
- **interface**: `api.events.signal.ProposalRejected.is`
- **summary**:     Proposal was rejected after the voting.

### ProposalExpired(proposal_id: `Hash`)
- **interface**: `api.events.signal.ProposalExpired.is`
- **summary**:     Proposal was expired, not finalized before expiry block number.

### WithdrawalGranted(proposal_id: `Hash`, campaign_id: `Hash`, org_id: `Hash`)
- **interface**: `api.events.signal.WithdrawalGranted.is`
- **summary**:     Balance was unlocked for the Withdrawal proposal.
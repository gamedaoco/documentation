---
title: Errors
---

This page lists the errors that can be encountered in the different modules.

- **[control](#control)**

- **[flow](#flow)**

- **[sense](#sense)**

- **[signal](#signal)**


___


## control

### AuthorizationError
- **interface**: `api.errors.control.AuthorizationError.is`
- **summary**:

### OrganizationExists
- **interface**: `api.errors.control.OrganizationExists.is`
- **summary**:   Org Exists.

### OrganizationUnknown
- **interface**: `api.errors.control.OrganizationUnknown.is`
- **summary**:   Org Unknown.

### BalanceLow
- **interface**: `api.errors.control.BalanceLow.is`
- **summary**:   Insufficient Balance to create Org.

### MembershipLimitReached
- **interface**: `api.errors.control.MembershipLimitReached.is`
- **summary**:   Membership Limit Reached.

### AlreadyMember
- **interface**: `api.errors.control.AlreadyMember.is`
- **summary**:   Member Exists.

### NotMember
- **interface**: `api.errors.control.NotMember.is`
- **summary**:   Member Unknown.

### NoChangesProvided
- **interface**: `api.errors.control.NoChangesProvided.is`
- **summary**:

### TreasuryExists
- **interface**: `api.errors.control.TreasuryExists.is`
- **summary**:   Treasury account already exists.

### TreasuryUnknown
- **interface**: `api.errors.control.TreasuryUnknown.is`
- **summary**:   Treasury account does not exists.

### MinimumDepositTooLow
- **interface**: `api.errors.control.MinimumDepositTooLow.is`
- **summary**:   Minimum deposit to Treasury too low.

### MissingParameter
- **interface**: `api.errors.control.MissingParameter.is`
- **summary**:

### WrongOrganizationType
- **interface**: `api.errors.control.WrongOrganizationType.is`
- **summary**:

___


## flow

### AuthorizationError
- **interface**: `api.errors.flow.AuthorizationError.is`
- **summary**:

### BalanceLow
- **interface**: `api.errors.flow.BalanceLow.is`
- **summary**:

### CampaignExpired
- **interface**: `api.errors.flow.CampaignExpired.is`
- **summary**:

### CampaignsPerBlockExceeded
- **interface**: `api.errors.flow.CampaignsPerBlockExceeded.is`
- **summary**:

### CampaignUnknown
- **interface**: `api.errors.flow.CampaignUnknown.is`
- **summary**:

### ContributionInsufficient
- **interface**: `api.errors.flow.ContributionInsufficient.is`
- **summary**:

### DepositInsufficient
- **interface**: `api.errors.flow.DepositInsufficient.is`
- **summary**:

### DepositTooHigh
- **interface**: `api.errors.flow.DepositTooHigh.is`
- **summary**:   Deposit exceeds the campaign target.

### NameTooShort
- **interface**: `api.errors.flow.NameTooShort.is`
- **summary**:

### NoContributionsAllowed
- **interface**: `api.errors.flow.NoContributionsAllowed.is`
- **summary**:

### NoContributionToOwnCampaign
- **interface**: `api.errors.flow.NoContributionToOwnCampaign.is`
- **summary**:

### OrgPrimeUnknown
- **interface**: `api.errors.flow.OrgPrimeUnknown.is`
- **summary**:

### OutOfBounds
- **interface**: `api.errors.flow.OutOfBounds.is`
- **summary**:   Campaign starts/expires validation failed.

### TreasuryBalanceLow
- **interface**: `api.errors.flow.TreasuryBalanceLow.is`
- **summary**:

### TreasuryNotExist
- **interface**: `api.errors.flow.TreasuryNotExist.is`
- **summary**:

___


## sense

### EntityExists
- **interface**: `api.errors.sense.EntityExists.is`
- **summary**:   Entity exists.

### EntityUnknown
- **interface**: `api.errors.sense.EntityUnknown.is`
- **summary**:   Entity unknown.

### InvalidParam
- **interface**: `api.errors.sense.InvalidParam.is`
- **summary**:   Invalid param.

### EntityPropertyOverflow
- **interface**: `api.errors.sense.EntityPropertyOverflow.is`
- **summary**:   Overflow adding a value to the entity property.

### EntityCountOverflow
- **interface**: `api.errors.sense.EntityCountOverflow.is`
- **summary**:   Overflow adding a value to the entity count.

___


## signal

### AuthorizationError
- **interface**: `api.errors.signal.AuthorizationError.is`
- **summary**:

### BalanceLow
- **interface**: `api.errors.signal.BalanceLow.is`
- **summary**:

### CampaignUnsucceeded
- **interface**: `api.errors.signal.CampaignUnsucceeded.is`
- **summary**:

### DepositInsufficient
- **interface**: `api.errors.signal.DepositInsufficient.is`
- **summary**:

### DuplicateVote
- **interface**: `api.errors.signal.DuplicateVote.is`
- **summary**:

### MissingParameter
- **interface**: `api.errors.signal.MissingParameter.is`
- **summary**:

### OrgInactive
- **interface**: `api.errors.signal.OrgInactive.is`
- **summary**:

### OutOfBounds
- **interface**: `api.errors.signal.OutOfBounds.is`
- **summary**:

### ProposalExists
- **interface**: `api.errors.signal.ProposalExists.is`
- **summary**:

### ProposalNotActive
- **interface**: `api.errors.signal.ProposalNotActive.is`
- **summary**:

### ProposalUnknown
- **interface**: `api.errors.signal.ProposalUnknown.is`
- **summary**:

### TooManyProposals
- **interface**: `api.errors.signal.TooManyProposals.is`
- **summary**:

### TreasuryBalanceLow
- **interface**: `api.errors.signal.TreasuryBalanceLow.is`
- **summary**:

### TreasuryUnknown
- **interface**: `api.errors.signal.TreasuryUnknown.is`
- **summary**:

### VoteLimitReached
- **interface**: `api.errors.signal.VoteLimitReached.is`
- **summary**:

### WrongParameter
- **interface**: `api.errors.signal.WrongParameter.is`
- **summary**:

___


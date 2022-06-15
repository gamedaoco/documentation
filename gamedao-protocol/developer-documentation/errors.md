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

### OrganizationExists
- **interface**: `api.errors.control.OrganizationExists.is`
- **summary**:    Org already exists.

### OrganizationUnknown
- **interface**: `api.errors.control.OrganizationUnknown.is`
- **summary**:    Org is unknown.

### OrganizationInactive
- **interface**: `api.errors.control.OrganizationInactive.is`
- **summary**:    Org is inactive.

### BalanceTooLow
- **interface**: `api.errors.control.BalanceTooLow.is`
- **summary**:    Insufficient Balance to create Org.

### MemberAddOverflow
- **interface**: `api.errors.control.MemberAddOverflow.is`
- **summary**:    Member Add Overflow.

### MembershipLimitReached
- **interface**: `api.errors.control.MembershipLimitReached.is`
- **summary**:    Membership Limit Reached.

### MemberExists
- **interface**: `api.errors.control.MemberExists.is`
- **summary**:    Member Exists.

### MemberUnknown
- **interface**: `api.errors.control.MemberUnknown.is`
- **summary**:    Member Unknonw.

### DuplicateAddress
- **interface**: `api.errors.control.DuplicateAddress.is`
- **summary**:    Duplicate Address.

### UnknownError
- **interface**: `api.errors.control.UnknownError.is`
- **summary**:    Unknown Error.

### GuruMeditation
- **interface**: `api.errors.control.GuruMeditation.is`
- **summary**:    Guru Meditation.

### TreasuryExists
- **interface**: `api.errors.control.TreasuryExists.is`
- **summary**:    Treasury account already exists.

### MinimumDepositTooLow
- **interface**: `api.errors.control.MinimumDepositTooLow.is`
- **summary**:    Minimum deposit to Treasury too low. 

___


## flow

### ContributionTooSmall
- **interface**: `api.errors.flow.ContributionTooSmall.is`
- **summary**:    Must contribute at least the minimum amount of campaigns.

### BalanceTooLow
- **interface**: `api.errors.flow.BalanceTooLow.is`
- **summary**:    Balance too low.

### TreasuryBalanceTooLow
- **interface**: `api.errors.flow.TreasuryBalanceTooLow.is`
- **summary**:    Treasury balance too low.

### InvalidId
- **interface**: `api.errors.flow.InvalidId.is`
- **summary**:    The campaign id specified does not exist.

### ContributionPeriodOver
- **interface**: `api.errors.flow.ContributionPeriodOver.is`
- **summary**:    The campaign's contribution period has ended; no more contributions will be accepted.

### CampaignStillActive
- **interface**: `api.errors.flow.CampaignStillActive.is`
- **summary**:    You may not withdraw or dispense Campaigns while the Campaign is still active.

### NoContribution
- **interface**: `api.errors.flow.NoContribution.is`
- **summary**:    You cannot withdraw Campaigns because you have not contributed any.

### CampaignNotRetired
- **interface**: `api.errors.flow.CampaignNotRetired.is`
- **summary**:    You cannot dissolve a Campaign that has not yet completed its retirement period.

### CampaignExpired
- **interface**: `api.errors.flow.CampaignExpired.is`
- **summary**:    Campaign expired.

### UnsuccessfulCampaign
- **interface**: `api.errors.flow.UnsuccessfulCampaign.is`
- **summary**:    Cannot dispense Campaigns from an unsuccessful Campaign.

### EndTooEarly
- **interface**: `api.errors.flow.EndTooEarly.is`
- **summary**:    Campaign must end after it starts.

### EndTooLate
- **interface**: `api.errors.flow.EndTooLate.is`
- **summary**:    Campaign expiry has be lower than the block number limit.

### CampaignsPerBlockExceeded
- **interface**: `api.errors.flow.CampaignsPerBlockExceeded.is`
- **summary**:    Max campaigns per block exceeded.

### NameTooLong
- **interface**: `api.errors.flow.NameTooLong.is`
- **summary**:    Name too long.

### NameTooShort
- **interface**: `api.errors.flow.NameTooShort.is`
- **summary**:    Name too short.

### DepositTooHigh
- **interface**: `api.errors.flow.DepositTooHigh.is`
- **summary**:    Deposit exceeds the campaign target.

### IdExists
- **interface**: `api.errors.flow.IdExists.is`
- **summary**:    Campaign id exists.

### AddCampaignOverflow
- **interface**: `api.errors.flow.AddCampaignOverflow.is`
- **summary**:    Overflow adding a new campaign to total fundings.

### AddOwnedOverflow
- **interface**: `api.errors.flow.AddOwnedOverflow.is`
- **summary**:    Overflow adding a new owner.

### UpdateContributorOverflow
- **interface**: `api.errors.flow.UpdateContributorOverflow.is`
- **summary**:    Overflow adding to the total number of contributors of a camapaign.

### AddContributionOverflow
- **interface**: `api.errors.flow.AddContributionOverflow.is`
- **summary**:    Overflow adding to the total number of contributions of a camapaign.

### OwnerUnknown
- **interface**: `api.errors.flow.OwnerUnknown.is`
- **summary**:    Campaign owner unknown.

### AdminUnknown
- **interface**: `api.errors.flow.AdminUnknown.is`
- **summary**:    Campaign admin unknown.

### NoContributionToOwnCampaign
- **interface**: `api.errors.flow.NoContributionToOwnCampaign.is`
- **summary**:    Cannot contribute to owned campaign.

### GuruMeditation
- **interface**: `api.errors.flow.GuruMeditation.is`
- **summary**:    Guru Meditation.

### AuthorizationError
- **interface**: `api.errors.flow.AuthorizationError.is`
- **summary**:    Zou are not authorized for this call.

### NoContributionsAllowed
- **interface**: `api.errors.flow.NoContributionsAllowed.is`
- **summary**:    Contributions not allowed.

### IdUnknown
- **interface**: `api.errors.flow.IdUnknown.is`
- **summary**:    Id Unknown.

### TransferError
- **interface**: `api.errors.flow.TransferError.is`
- **summary**:    Transfer Error.

___


## sense

### EntityExists
- **interface**: `api.errors.sense.EntityExists.is`
- **summary**:    Entity exists.

### EntityUnknown
- **interface**: `api.errors.sense.EntityUnknown.is`
- **summary**:    Entity unknown.

### GuruMeditation
- **interface**: `api.errors.sense.GuruMeditation.is`
- **summary**:    Guru Meditation.

### ParamLimitExceed
- **interface**: `api.errors.sense.ParamLimitExceed.is`
- **summary**:    Param limit exceed.

### InvalidParam
- **interface**: `api.errors.sense.InvalidParam.is`
- **summary**:    Invalid param.

### EntityPropertyOverflow
- **interface**: `api.errors.sense.EntityPropertyOverflow.is`
- **summary**:    Overflow adding a value to the entity property

___


## signal
 
TBD (this pallet is under refactoring right now)

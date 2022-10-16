# Events



Events are emitted for certain operations on the runtime. The following sections describe the events that are part of the default runtime.

* [**control**](events.md#control)
* [**flow**](events.md#flow)
* [**sense**](events.md#sense)
* [**signal**](events.md#signal)

***

### control

#### OrgCreated(org\_id: `Hash`, creator: `AccountId`, treasury\_id: `AccountId`, created\_at: `BlockNumber`, realm\_index: `u64`)

* **interface**: `api.events.control.OrgCreated.is`
* **summary**: Org was successfully created.

#### OrgEnabled(`Hash`)

* **interface**: `api.events.control.OrgEnabled.is`
* **summary**: Org was enabled and it's state become Active.

#### OrgDisabled(`Hash`)

* **interface**: `api.events.control.OrgDisabled.is`
* **summary**: Org was disabled and it's state become Inactive.

#### MemberAdded(org\_id: `Hash`, who: `AccountId`, block\_number: `BlockNumber`)

* **interface**: `api.events.control.MemberAdded.is`
* **summary**: A member has been added to the Org.

#### MemberRemoved(org\_id: `Hash`, who: `AccountId`, block\_number: `BlockNumber`)

* **interface**: `api.events.control.MemberRemoved.is`
* **summary**: A member has been removed from the Org.

#### OrgUpdated(org\_id: `Hash`, prime\_id: `Option<AccountId>`, org\_type: `Option<OrgType>`, access\_model: `Option<AccessModel>`, member\_limit: `Option<MemberLimit>`, fee\_model: `Option<FeeModel>`, membership\_fee: `Option<Balance>`, block\_number: `BlockNumber`)

* **interface**: `api.events.control.OrgUpdated.is`
* **summary**:

#### FundsSpended(org\_id: `Hash`, beneficiary: `AccountId`, amount: `Balance`, currency\_id: `CurrencyId`, block\_number: `BlockNumber`)

* **interface**: `api.events.control.FundsSpended.is`
* **summary**:

***

### flow

#### Created(campaign\_id: `Hash`, creator: `AccountId`, admin: `AccountId`, target: `Balance`, deposit: `Balance`, expiry: `BlockNumber`, name: `BoundedVec<u8, StringLimit>`)

* **interface**: `api.events.flow.Created.is`
* **summary**: Campaign was successfully created.

#### Activated(campaign\_id: `Hash`)

* **interface**: `api.events.flow.Activated.is`
* **summary**:

#### Contributed(campaign\_id: `Hash`, sender: `AccountId`, contribution: `Balance`, block\_number: `BlockNumber`)

* **interface**: `api.events.flow.Contributed.is`
* **summary**: Campaign was contributed.

#### Succeeded(campaign\_id: `Hash`, campaign\_balance: `Balance`, block\_number: `BlockNumber`)

* **interface**: `api.events.flow.Succeeded.is`
* **summary**: Campaign was finalized.

#### Failed(campaign\_id: `Hash`, campaign\_balance: `Balance`, block\_number: `BlockNumber`)

* **interface**: `api.events.flow.Failed.is`
* **summary**: Campaign failed - successfully reverted.

***

### sense

#### EntityCreated(account\_id: `AccountId`, block\_number: `BlockNumber`)

* **interface**: `api.events.sense.EntityCreated.is`
* **summary**: New Sense Entity was created.

#### PropertyUpdated(property\_type: `PropertyType`, account\_id: `AccountId`, block\_number: `BlockNumber`)

* **interface**: `api.events.sense.PropertyUpdated.is`
* **summary**: Property was updated.

***

### signal

#### Voted(account: `AccountId`, proposal\_id: `Hash`, voted: `bool`, yes: `VotingPower`, no: `VotingPower`, vote\_power: `VotingPower`)

* **interface**: `api.events.signal.Voted.is`
* **summary**:

#### Created(account: `AccountId`, proposal\_id: `Hash`, org\_id: `Hash`, campaign\_id: `Option<Hash>`, amount: `Option<Balance>`, start: `BlockNumber`, expiry: `BlockNumber`)

* **interface**: `api.events.signal.Created.is`
* **summary**:

#### Activated(proposal\_id: `Hash`)

* **interface**: `api.events.signal.Activated.is`
* **summary**:

#### Accepted(proposal\_id: `Hash`)

* **interface**: `api.events.signal.Accepted.is`
* **summary**:

#### Rejected(proposal\_id: `Hash`)

* **interface**: `api.events.signal.Rejected.is`
* **summary**:

#### Expired(proposal\_id: `Hash`)

* **interface**: `api.events.signal.Expired.is`
* **summary**:

#### Aborted(proposal\_id: `Hash`)

* **interface**: `api.events.signal.Aborted.is`
* **summary**:

#### Finalized(proposal\_id: `Hash`)

* **interface**: `api.events.signal.Finalized.is`
* **summary**:

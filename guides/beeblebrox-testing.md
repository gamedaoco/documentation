---
description: >-
  With this end to end testing script you will be able to create an organisation
  and a fundraising campaign, get the campaign funded and let the community vote
  about sending the funds to your treasury.
cover: ../.gitbook/assets/IP39-SchoolClassroom.jpg
coverY: 0
---

# 🧑🎓 Beeblebrox Testing

In order to interact with the chain without frontend do the following steps to achieve an end2end result:

### 1. Configure Beeblebrox DEV Chain

first you need to open your polkadot.js.org wallet and add the beeblebrox endpoint as a custom node.\


1. click the network selector on the top left
2. scroll down to the bottom
3. click DEVELOPMENT
4. add as custom endpoint `wss://beeblebrox.zero.io/node`
5. click switch on the top to access the new endpoint\
   ![](<../.gitbook/assets/image (7).png>)\
   \


{% hint style="danger" %}
Recommendation for all actions is: to have a separate browser window opened which shows the Network --> Explorer in polkadot.js.org. Have the "recent events" in your view when you perform transactions to copy response hashes out of it.&#x20;
{% endhint %}

### 2. Get ZERO, GAME & PLAY token

Get ZERO coin:

1. click Developer --> Sudo
2. under "submit the following change" select `balances`
3. in the right dropdown select `setBalance(who, newFree, newReserved)`
   1. field `who`: keep `Id` selected
   2. field `Id`: select your personal wallet address which should receive ZERO coins
   3. field `newFree`:  enter `1000000000000000000000` to receive 1000 ZERO
   4. field `newReserved`: leave 0 inside
4. click `Submit Sudo`
5. click `Sign and Submit` in the new modal
6. repeat steps 3-5 while selecting another wallet address at 3.3 if you want to top up other accounts (<mark style="color:purple;">**recommended to have at least 3 accounts keeping ZERO tokens for later scenarios: eg. account1, account2, account3**</mark>)
7. ![](<../.gitbook/assets/image (4).png>)

Get GAME token:

1. click Developer --> Sudo
2. under "submit the following change" select `currencies`
3. in the right dropdown select `updateBalance(who, currencyId, amount)`
   1. field `who`: keep `Id` selected
   2. field `Id`: select your personal wallet address which should receive GAME tokens
   3. field `currencyId`: enter `1` for GAME token
   4. field `amount`:  enter `1000000000000000000000` to receive 1000 GAME
4. click `Submit Sudo`
5. click `Sign and Submit` in the new modal
6. repeat steps 3-5 while selecting another wallet address at 3.2 if you want to top up other accounts (<mark style="color:purple;">**recommended to have at least 3 accounts keeping GAME tokens for later scenarios: eg. account1, account2, account3**</mark>)
7. ![](<../.gitbook/assets/image (3) (1).png>)



Get PLAY (stablecoin) token:

1. click Developer --> Sudo
2. under "submit the following change" select `currencies`
3. in the right dropdown select `updateBalance(who, currencyId, amount)`
   1. field `who`: keep `Id` selected
   2. field `Id`: select your personal wallet address which should receive PLAY tokens
   3. field `currencyId`: enter `2` for PLAY token
   4. field `amount`:  enter `1000000000000000000000` to receive 1000 PLAY
4. click `Submit Sudo`
5. click `Sign and Submit` in the new modal
6. repeat steps 3-5 while selecting another wallet address at 3.2 if you want to top up other accounts (<mark style="color:purple;">**recommended to have at least 3 accounts keeping PLAY tokens for later scenarios: eg. account1, account2, account3**</mark>)
7. ![](<../.gitbook/assets/image (1).png>)

&#x20;

### 3. Create Organisation

Either go through the frontend process on haiku.gamedao.co and click the "+" button on the left navigation after connecting your wallet or follow this process:

1. click Developer --> Extrinsics
2. ![](<../.gitbook/assets/image (1) (1).png>)&#x20;
3. 🚧 select one of the accounts you just topped up with ZERO & GAME balances under `using the selected account` (do not use Alice for this, use <mark style="color:purple;">**account1**</mark>)
4. select under `control` pallet "submit the following extrinsic"
5. select `createOrg(...)` in the right dropdown
6. ![](<../.gitbook/assets/image (9) (1).png>)
7. fill all the fields:
   1. controllerId: select one of the accounts you just topped up with ZERO & GAME balances&#x20;
   2. `name`: enter some name (your Organisation name)
   3. `cid`: `Qmeaj2DCJw71qwUZN8N2r4GVcBBGfqiyMMBrh15n2KbY7G` (a prefilled Content ID on IPFS containing description and logo)
   4. `orgType`: select any (eg. Individual)
   5. `access`: Open&#x20;
   6. `feeModel`: `NoFees` (or select `Transfer` if your Organisation wants to collect entry fees)
   7. `fee`: enter eg. `1000000000000000000` if you selected `Transfer` or `Reserve` in point 5 or leave 0 if `NoFees` was selected
   8. `govAsset`: `1` --> which represents GAME token
   9. `payAsset`: `2` --> which represents PLAY token
   10. `memberLimit`: add eg. `100` for a limit of 100 members
   11. `deposit`: add `10000000000000000000` for a deposit of 10 GAME (minimum deposit is currently 5 GAME)
   12. click `Submit Transaction`
   13. click `Sign and Submit`
8. Check that your Organisation is created by clicking to Developer --> Chain State --> select `control` pallet and `orgsControlled(AccoundId32)` and submit the query by clicking the "+" button. Make sure the account is selected which you set as controller at 7.1. \
   You should receive an `organisationId` which represents your Organisation. \
   🚧 Copy that ID and note it down somewhere as you will need it in other steps.&#x20;

### 4. Join Organisation

You can join an Organisation like this:&#x20;

1. click Developer --> Extrinsics
2. select `control` pallet and `addMember(orgId, accountId)` in the right dropdown
3. enter your organisationId which you received from Create Organisation process point 8
4. choose an account (<mark style="color:purple;">**account2**</mark>) which is not yet member in the Organisation and has enough ZERO & GAME balance.&#x20;
5. ![](<../.gitbook/assets/image (5).png>)
6. click `Submit Transaction`
7. click `Sign and Submit`



### 5. Create Fundraising campaign

This is how you create a fundraising campaign:&#x20;

1. use the account (<mark style="color:purple;">**account1**</mark>) which was used to create the organisation under `using the selected account`
2. click Developer --> Extrinsics
3. select `flow` pallet and `createCampaign(...)` in the right dropdown
4. fill all the fields
   1. `orgId`: enter the `orgId` from the Organisation you created and which you copied before&#x20;
   2. `adminId`: select the account which owns the Organisation&#x20;
   3. `name`: add a nice name ("My Campaign")
   4. `target`: `10000000000000000000` (for 10 PLAY)
   5. `deposit`: `1000000000000000000` (for 1 GAME)
   6. `expiry`: enter a block number which is in the future (look at the current block number on the top left of polkadot.js.org and add 600 blocks for 30 minutes or 1200 for 1h if you need more time for testing). \
      🚧  At this expiry block number the campaign will expire. When it is not fully funded the users who funded the campaign will receive their token back. If it was funded in before this block number was processed the campaign was successful.  &#x20;
   7. `protocol`: `Raise` (fundraising protocol)
   8. `governance`: `No` (no campaign governance by the funding audience)
   9. `cid`: `Qmeaj2DCJw71qwUZN8N2r4GVcBBGfqiyMMBrh15n2KbY7G`
   10. `tokenSymbol`: `PLAY`
   11. `tokenName`: `Play`
   12. ![](<../.gitbook/assets/image (9).png>)
   13. click `Submit Transaction`
   14. click `Sign and Submit`
5. Check that your `campaignId` is created by clicking to Developer --> Chain State --> select `flow` pallet and `campaignsByOrg(H256)`and add your `organisationId` as the parameter `H256` and submit the query by clicking the "+" button.  \
   You should receive an `campaignId` which represents your Campaign. \
   🚧 Copy that ID and note it down somewhere as you will need it in other steps.&#x20;

### 6. Fund into campaign

Contribute into a campaign by:



1. click Developer --> Extrinsics
2. select `flow` pallet and `contribute(campaignId, contribution)` in the right dropdown
3. use another account (<mark style="color:purple;">**account3**</mark>) and not the one which you used to create the campaign. Preferably use an account which is not even member of the organisation. was used to create the organisation under `using the selected account`
4. Fill all the fields
   1. `campaignId`: add the copied `campaignId`
   2. `contribution`: `11000000000000000000` 11 PLAY to overachieve the target of 10 PLAY&#x20;
5. ![](<../.gitbook/assets/image (6).png>)
6. click `Submit Transaction`
7. click `Sign and Submit`
8. Check that your `campaignId` is funded by clicking to Developer --> Chain State --> select `flow` pallet and `campaignsBalance(H256)`and add your `campaignId` as the parameter `H256` and submit the query by clicking the "+" button. &#x20;
9. leave the window open until the expiry block is reached and see that 0.3% is substracted as a fee from the campaign. \
   &#x20;

### 7. Create withdrawal proposal

After the campaign expired and was funded create a withdrawal proposal to let the community vote on transferring the funds to the organisation treasury:

1. click Developer --> Extrinsics
2. select `signal` pallet and `withdrawProposal(campaignId, title, cid, amount, start, expiry)` in the right dropdown
3. Fill all the fields
   1. use the account which created the campaign (<mark style="color:purple;">**account1**</mark>) under `using the selected account`
   2. `campaignId`: the `campaignId` which was funded
   3. `title`: give your proposal a name like "withdraw funds"
   4. cid: `Qmeaj2DCJw71qwUZN8N2r4GVcBBGfqiyMMBrh15n2KbY7G` (content ID for proposal content)
   5. `amount`: `10000000000000000000`
   6. `start:` add `block number (`choose a block number in the near future)
   7. `expiry:`add `block number (`choose a block number in the future which allows you to have enough time to vote on the proposal ( eg. 300 blocks more than the starting block number for 15 minutes of voting time)
   8. ![](<../.gitbook/assets/image (3).png>)
   9. 🚧  open in a new tab the Network --> Explorer. Have the "recent events" in your view when you perform the transaction so that you can copy the `proposalId`
   10. click `Submit Transaction`
   11. click `Sign and Submit`
4. switch to the tab with the recent events and copy the `proposalId` which was created

### 8. Vote for withdrawal

Vote for the withdrawal of funds:

1. click Developer --> Extrinsics
2. select `signal` pallet and `simpleVote(proposalId, vote)` in the right dropdown
3. Fill all the fields
   1. use the account which funded into the campaign (<mark style="color:purple;">**account3**</mark>) under `using the selected account`
   2. propsalId: add the proposalId which you copied before from the recent events
   3. `vote`: `Yes`
   4. ``![](<../.gitbook/assets/image (11).png>)
   5. click `Submit Transaction`
   6. click `Sign and Submit`
4. check recent events tab when the block expiry date has arrived (in our scenario there is only 1 vote, which accomplishes the voting process immediately)&#x20;

### 9. Check your treasury

Now we check if we received the requested funds:

1. click Developer --> Chain State
2. select `control` pallet and `orgTreasury(256)` in the right dropdown
3. fill the field H256 with the `organizationId` you have noted down in the beginning (or query chain state with "memberships" call)
4. click the "+" to submit the query
5. copy the response hash and note it down (this is your `accountId` of the Organisation Treasruy)
6. switch pallet to `tokens` and `accounts(AccountId, u32)`&#x20;
7. enter the copied Treasury hash into the `accountId`
8. toggle off  `include option`
9. click the "+" to submit the query
10. see that you hold free 10 PLAY and 0.967 are still reserved as you only requested 10 PLAY in your withdrawal proposal:

    ```
    free: 10,000,000,000,000,000,000
    reserved: 967,000,000,000,000,000
    ```
11. ![](<../.gitbook/assets/image (8).png>)


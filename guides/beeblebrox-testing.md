# 👨‍👦 Beeblebrox Testing

In order to interact with the chain without frontend do the following steps to achieve an end2end result:

### Configure Beeblebrox DEV Chain

first you need to open your polkadot.js.org wallet and add the beeblebrox endpoint as a custom node.\


1. click the network selector on the top left
2. scroll down to the bottom
3. click DEVELOPMENT
4. add as custom endpoint `wss://beeblebrox.zero.io/node`
5. click switch on the top to access the new endpoint\
   ![](<../.gitbook/assets/image (7).png>)\
   \




### Get ZERO, GAME & PLAY token

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
6. repeat steps 3-5 while selecting another wallet address at 3.3 if you want to top up other accounts (<mark style="color:purple;">**recommended to have at least 3 accounts keeping ZERO tokens for later scenarios**</mark>)
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
6. repeat steps 3-5 while selecting another wallet address at 3.2 if you want to top up other accounts (<mark style="color:purple;">**recommended to have at least 3 accounts keeping GAME tokens for later scenarios**</mark>)
7. ![](<../.gitbook/assets/image (3).png>)



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
6. repeat steps 3-5 while selecting another wallet address at 3.2 if you want to top up other accounts (<mark style="color:purple;">**recommended to have at least 3 accounts keeping PLAY tokens for later scenarios**</mark>)
7. ![](../.gitbook/assets/image.png)

&#x20;

### Create Organisation

Either go through the frontend process on haiku.gamedao.co and click the "+" button on the left navigation after connecting your wallet or follow this process:

1. click Developer --> Extrinsics
2. ![](<../.gitbook/assets/image (1).png>)&#x20;
3. 🚧 select one of the accounts you just topped up with ZERO & GAME balances under `using the selected account` (do not use Alice for this)
4. select under `control` pallet "submit the following extrinsic"
5. select `createOrg(...)` in the right dropdown
6. ![](<../.gitbook/assets/image (9).png>)
7. fill all the fields:
   1. controllerId: select one of the accounts you just topped up with ZERO & GAME balances&#x20;
   2. `name`: enter some name (your Organisation name)
   3. `cid`: Qmeaj2DCJw71qwUZN8N2r4GVcBBGfqiyMMBrh15n2KbY7G (a prefilled Content ID on IPFS containing description and logo)
   4. `orgType`: select any (eg. Individual)
   5. `access`: Open&#x20;
   6. `feeModel`: `NoFees` (or select `Transfer` if your Organisation wants to collect entry fees)
   7. `fee`: enter eg. `1000000000000000000` if you selected `Transfer` or `Reserve` in point 5 or leave 0 if `NoFees` was selected
   8. `govAsset`: `1` --> which represents GAME token
   9. `payAsset`: `2` --> which represents PLAY token
   10. `memberLimit`: add eg. `100` for a limit of 100 members
   11. `deposit`: add `10000000000000000000` for a deposit of 10 GAME
   12. click `Submit Transaction`
   13. click `Sign and Submit`
8. Check that your Organisation is created by clicking to Developer --> Chain State --> select `control` pallet and `orgsControlled(AccoundId32)` and submit the query by clicking the "+" button. Make sure the account is selected which you set as controller at 7.1. \
   You should receive an `organisationId` which represents your Organisation. Copy that ID and note it down somewhere as you will need it in other steps.&#x20;

### Join Organisation

You can join an organisation like this:&#x20;

1. click Developer --> Extrinsics
2. select `control` pallet and `addMember(orgId, accountId)` in the right dropdown
3. enter your organisationId which you received from Create Organisation process point 8
4. choose an account which is not yet member in the Organisation and has enough ZERO & GAME balance.&#x20;
5. ![](<../.gitbook/assets/image (5).png>)
6. click `Submit Transaction`
7. click `Sign and Submit`





### Create Fundraising campaign

This is how you create a fundraising campaign:&#x20;

1. use the account which was used to create the organisation under `using the selected account`
2. click Developer --> Extrinsics
3. select `flow` pallet and `createCampaign(...)` in the right dropdown
4.

### Fund into campaign

...

### Create withdrawal proposal

...

### Vote for withdrawal

...

### check your treasury

...

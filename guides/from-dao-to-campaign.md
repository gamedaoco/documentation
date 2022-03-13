---
description: >-
  This walk through will show you the essential steps to create a successful
  fundraising campaign on GameDAO
---

# 🪄 From DAO to Campaign

## The basics

A DAO is the minimum primitive you need to establish to get organised with your collaborators and community. Whether you are setting up a guild, a working group for your project team or want to interact with hundreds of community members and contributors.

## 1. Create a Wallet and Claim an Identity

Set up your polkadot.js wallet and obtain some ZERO token from the faucet bot in our Discord Channel as described in [previous chapter](installing-your-wallet.md) and set an on-chain identity like this:

1. go to [https://polkadot.js.org/apps/#/accounts](https://polkadot.js.org/apps/#/accounts) and select an account from below and find the three dots on the right:\
   ![](<../.gitbook/assets/image (5).png>)
2. click "Set on-chain identity":\
   ![](<../.gitbook/assets/image (4).png>)\

3. fill some details like display name and email or twitter:\
   ![](<../.gitbook/assets/image (6).png>)
4. Click Set Identity and&#x20;
5. Sign the transaction by clicking "Sign & Submit" and entering your wallet password.
6. If it did not work, make sure you have some ZERO amount on your wallet.

## 2. Creating an Organisation

Now its time to create your first DAO.

1. Go to [https://beta.gamedao.co/](https://beta.gamedao.co) and enter the app
2. Connect your wallet on the top right connect button
3. Click  on Organisations on the left navigation to get to the Organisations List Page
4. Click the "New DAO" button
5. Enter organization name and provide an email address
6. Upload some nice free to use images representing the DAO you are setting up
7. &#x20;Write a short description about the purpose of the Organisation
8. add a website and a code repository if you have some related to your Organisation
9. **IMPORTANT**: The Controller Account address needs to be a wallet address in ZERO format. The holder of the Controller Account address is the admin of the DAO. You can use your current address (eg. copy by clicking the heart icon next to your wallet on the top right) and paste it into the form
10. **IMPORTANT**: The Treasury Account address also needs to be a wallet address in ZERO format. The Treasury Account address is the address receiving funds from fundraising campaigns and fees. This address may not be the same address as the Controller Account address. Therefore you will need a second address to setup your Organisation. \
    If you do not have a second address you can create one in your polkadot.js browser plugin repeating the steps in[ Install Polkadot wallet and create an Account](installing-your-wallet.md).  Add your second address into the Treasury Account address field\


    {% hint style="warning" %}
    **Treasury Account:** The treasury account on the current version of our test platform is just an address which is owned by an individual. In a later version each DAO / Organisation will have a treasury which is owned and governed by the DAO / Organisation itself. The current version does not reflect this yet.&#x20;
    {% endhint %}
11. Choose how do you want to control member access by selecting&#x20;
    1. Open (everyone can join until member limit is reached)
    2. Invitation (members need to be on a whitelist to enter the Organisation) (_<mark style="color:purple;">coming soon</mark>_)
    3. Proposal (users need to apply to become a member and existing users can accept or decline through voting) (_<mark style="color:purple;">coming soon</mark>_)
12. select a Fee Model
    1. no fees (free entry)
    2. reserve (members need to lock the amount of token configured in Membership Fee)
    3. transfer (the Membership Fee is transferred to the Organisation Treasury account address  on entry)
13. Add a Membership Fee (ZERO) which will apply for "reserve" or "transfer" Fee Models
14. Click Create Organisation and sign the transaction
15. Your DAO is created \


## 3. Creating a Campaign

Raise a campaign to receive funds from your community.

1. Click on Campaigns in the left navigation
2. Click "+New Campaign" and start filling the form by
3. selecting your Organisation from the Organisation select box
4. Give your fundraising campaign a campaign name
5. Add a description  (will be shown on the Campaigns List Page)
6. Add a Logo  (will be shown on the Campaigns List Page and on top of the header for your Campaign Detail Page)
7. Add a Header Image (will be shown on the Campaigns Detail Page)
8. Add a Content Description and images using the markdown editor (be creative and design your campaign page) (<mark style="color:purple;">a better editor is coming soon</mark>)
9. Add a public representative to be transparent to your community
10. Keep the address or replace the address for the Admin Account&#x20;
11. Select Prepaid as Protocol (<mark style="color:purple;">others coming soon</mark>)
12. Select a suitable category for the usage of the funds
13. Deposit: Add an amount you are willing to deposit to show the community how much you are willing to lock up for the runtime of the campaign  (<mark style="color:purple;">on beta.gamedao.co so far only ZERO tokens are used</mark>)&#x20;

    {% hint style="warning" %}
    **DAO Treasury must hold enough funds:** As the campaign deposit is paid from the treasury, you need to make sure to have enough funds in the treasury. You can get tokens from the faucet here:  [https://discord.gg/P7NHWGzJ7r](https://discord.gg/P7NHWGzJ7r)
    {% endhint %}


14. Funding Target: Add the amount you want to raise (<mark style="color:purple;">on beta.gamedao.co so far only ZERO tokens are used but later stable coins will be used to raise funds</mark>) and make sure the target is not too high for a test (eg. 1-5 ZERO or so)
15. Select a campaign duration (you can choose 20min, 1h or 2h to run a quick test, but make sure you can fund it with your test tokens during this time or ask around in the discord community if someone can fund some tokens into your campaign)
16. check the checkboxes below and click Create Campaign
17. Sign and submit the transaction and have a look on your fundraising campaign

## 4. Funding the campaign

1. Go to the campaign list page by clicking in the left navigation bar on "Campaigns"
2. find your campaign and enter a value into the input field. You cannot fund the campaign with the same wallet account which was used to create the campaign.
3. Ask your community to fund into your campaign before the runtime is over.&#x20;



{% hint style="info" %}
**Good to know:** The campaign can be funded directly from the Campaign List Page. When your campaign is successfully funded create a withdrawal proposal to access the funds.\
Go on here: [Fundraising Withdrawal Proposal](../fundamentals/fundraising/fundraising-withdrawal-proposal.md)
{% endhint %}


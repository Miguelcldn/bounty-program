![alt text](https://github.com/bitDubai/media-kit/blob/master/MediaKit/Fermat%20Branding/Fermat%20Logotype/Fermat_Logo_3D.png "Fermat Logo")

# Digital Asset Platform v2 Bounty

## Introduction

After [previous bounty] (link a previous bounty) was completed, new needs have raised the priority to introduce changes and improvements to DAP platform. This document describes the scope, design and timeline of the new bounty.

## Scope

### Current developments in progress

In the present, DAP is being changed and improved in the following way:

* Changes to Community Apps: Asset Issuer, Asset User and Redeem Point community apps doesn't connect to actors by default and enables them to request for permission and only get performs the connection after authorization from the actor. [Issue #222 on Github] (link to github)

* Multiple network selection: all DAP wallets and sub apps allows the selection of the NetworkType (MainNet, TestNet and RegTestNet) while all processes and transactions must still continue working as expected. [Issue #222 on Github] (link to github)

* Wallets GUI small improvements: we are enhancing the user experience by adding Search options, filter of data for assets with no positive balance, etc. [Issue #222 on Github] (link to github)

* Wallets and Factory GUI general UX changes: the design team is working on changing the general look and feel of the DAP Wallets and Asset Factory app. [Issue #222 on Github] (link to github)

* BCH layer changes to support all network types: changes to BCH to support transactions in any network concurrently. [Issue #222 on Github] (link to github)

Additionaly, and as part of this Bounty the following additions will be scoped:

### Bounty scope

#### New Transaction: Asset User Distribution

This transaction will be used to transfer assets between users (Asset User --> Asset User). Current existing transactions regarding distribution only involves Asset Issuer --> Asset User actors.

* Changes to Asset User Wallet: 
    * new button will be added called "Share your Asset" that will open a new window to allow selection of users to share the asset with.
    * new screen that will get the connected Users by the Asset User Community app
    
* New transactional plugin Asset User Distribution which will handle the transaction steps to distribute with all security needed.

* Changes to Asset Reception to allow receiving assets from Issuer and User actors.
    
#### New Transaction: Selling and Buying assets.

This transaction will allow the exchange of Assets between users (Asset User --> Asset User), allowing them to buy and sell assets.

We will incorporate the concept of Asset Request that will be a process started by the buyer, that will indicate the Asset Seller the start of the transaction.

The process can be described as follows:

* The Asset buyer connects to the Asset Seller and starts an Asset Catalog Request.
* The Asset Catalog request is received by the Asset Seller and accepted, which sends the Seller Asset Catalog to the Asset Buyer.
* The Asset Buyer select an asset from the Catalog and starts an Asset Exchange Request for an specific asset.
* The Asset select accepts (or deny) the Asset Exchange Request starting the transaction process which includes:
    * Locking of select asset founds until payment transaction is received
    * Sending from the Buyer the Genesis Amount of bitcoins 
    * Distribution of asset to user after payment received.
    * If payment is not received, transaction is rollbacked.

* Changes to Asset User Wallet
    * New button to perform action "Buy Asset"
    * New screen to select user to request Asset Catalog from seller.
    * New screens to accept of deny requests.

* New network services **Asset Catalog Request** and **Asset Exchange Request**: to allow the exchange of data for each request.

* New transactional plugins **Asset Exchange Generation** and **Asset Exchange Reception** to perform the transactional steps to generate and receive an asset exchange transaction.


**Once approved, the design will be completed in dev.fermat.org flows**
     

## Timeline

Based on current workload and resouces available, the delivery date of this bounty should be during  **March**.

## Evaluation

To be considered success this bounty must pass the following tests:

* Distribute between users an asset in any network.
* Exchange an asset between users in any network.
* The combination of any possible allowed behaviour by the applications without generating errors that doesn't allow to continue the evaluation.


## Distribution

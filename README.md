<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Event URL: [https://bit.ly/2JisLG9](https://bit.ly/2JisLG9)

# An introduction to the IBM Blockchain Platform 2.0!

# Linkedin.com/in/lennartfrantzell

[Whitelisting](https://cloud.ibm.com/registration/whitelist). 

## News

[Does Hyperledger Fabric perform at scale?](https://www.ibm.com/blogs/blockchain/2019/04/does-hyperledger-fabric-perform-at-scale/)

[Forbes: Blockchain Goes To Work At Walmart, Amazon, JPMorgan, Cargill and 46 Other Enterprises](https://www.forbes.com/sites/michaeldelcastillo/2019/04/16/blockchain-goes-to-work/#3aa207de2a40)

[Cargill Hyperledger Grid](https://www.cargill.com/2019/cargill-invests-digital-engineering-to-support-hyperledger-grid)

[Target Blockchain for Supply Chain](https://www.coindesk.com/retail-giant-target-is-working-on-a-blockchain-for-supply-chains)

[Why new off-chain storage is required for blockchains](https://www.ibm.com/downloads/cas/RXOVXAPM)

## IBM Blockchain Twitter feeds:

Jerry Cuomo IBM Fellow and CTO, instigator of Blockchain: https://twitter.com/jerrycuomo

Christopher Ferris. IBM Fellow CTO Open Technology https://twitter.com/christo4ferris

Arnaud J Le Hors. Senior Technical Staff Member: https://twitter.com/lehors

Christian Cachin Swiss Cryptographer, Zurich. https://twitter.com/cczurich?lang=en

IBM Blockchain: https://twitter.com/ibmblockchain?lang=en

Mark Parzygnat.Program Director IBM Blockchain: https://twitter.com/meetmarkp?lang=en

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Learning Objectives:

1. Introduction

1. On your laptop: how to install the IBM Visual Studio Code with the brand new IBP plugin

1. How to create your first Smart Contract with Visual Studio Code

1. How to launch the brand new IBM Blockchain Platform 2.0 in the IBM Cloud

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Learning Objective 1: Introduction

It all started in October during the Global Financial Crisis in 2008 with Satoshi Nakamoto and his paper [BitCoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf) which addressed a key problem in electronic commerce:
<p><i><b>
A purely peer-to-peer version of electronic cash would allow online payments to be sent directly from one party to another without going through a financial institution. 
<p> 
Digital signatures provide part of the solution, but the main benefits are lost if a trusted third party is still required to prevent double-spending. 
<p>
We propose a solution to the double-spending problem using a peer-to-peer network.</i></b> 

## Let's start with Hyperledger:

<img src= "Hyperledger.png" width="1000" height="500">

1. #### [https://github.com/hyperledger/](https://github.com/hyperledger/)
1. #### [Hyperledger Fabric Now Supports Ethereum](https://www.hyperledger.org/blog/2018/10/26/hyperledger-fabric-now-supports-ethereum)
1. #### [Cargill Hyperledger Grid for Supply Chain solutions](https://www.hyperledger.org/projects/grid)
1. #### [Hyperledger Caliper Benchmark tool](https://www.hyperledger.org/projects/caliper)
1. #### [Hyperledger Quilt  offers interoperability between ledger systems by implementing the Interledger protocol ](https://www.hyperledger.org/projects/quilt)
1. #### [Hyperledger URSA a shared cryptographic library](https://www.hyperledger.org/projects/ursa)

### [Hyperledger Fabric 1.4.1](https://hyperledger-fabric.readthedocs.io/en/release-1.4/index.html)

Enterprise grade permissioned distributed ledger platform that offers modularity and versatility for a broad set of industry use cases.

1. [Hyperledger Fabric’s First long term support release](https://hyperledger-fabric.readthedocs.io/en/release-1.4/whatsnew.html#raft-ordering-service)

1. [Raft ordering service](https://hyperledger-fabric.readthedocs.io/en/release-1.4/whatsnew.html#raft-ordering-service) 
    Fault Tolerance consensus algorithm     

[Blockchain Use Cases](https://www.ibm.com/blockchain/use-cases/)

[IBM Blockchain Garage Services](https://www.ibm.com/blockchain/garage)

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Learning Objective 2: On your laptop: how to install the IBM Visual Studio Code with the brand new IBP plugin

<img src="VSC_BC.png">

### [Visual Studio Code](https://code.visualstudio.com)

### [https://marketplace.visualstudio.com/items?itemName=IBMBlockchain.ibm-blockchain-platform](https://marketplace.visualstudio.com/items?itemName=IBMBlockchain.ibm-blockchain-platform)

<img src="architecture.png">

[An introduction to programming Hyperledger Fabric on SlideShare](https://www.slideshare.net/LennartF/ibp-technical-introduction)

[IBM Blockchain Platform on SlideShare](https://www.slideshare.net/LennartF/ibm-blockchain-platform-explained-149106072)

[IBM Blockchain Solutions on SlideShare](https://www.slideshare.net/LennartF/ibm-blockchain-solutions-149098151)

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Learning Objective 3: Developing smart contracts with Visual Studio Code extension 

[Install IBM Blockchain Platform VS Code extension for free](https://cloud.ibm.com/docs/services/blockchain?topic=blockchain-develop-vscode#develop-vscode-install)

[Download Visual Studio Code](https://code.visualstudio.com/)

[Install IBM Blockchain Platform for VS Code ](https://marketplace.visualstudio.com/items?itemName=IBMBlockchain.ibm-blockchain-platform)

Go through Tutorial One in VS Code: Local Smart Contract Development.

Follow the typical workflow from generating a new smart contract project, deploying code to the <i>local_fabric_runtime</i> and testing your transactions via an application gateway</i> 

<img src="VSCODE_TUT1.PNG" width="300" height="500">


### my-asset-contract.ts
~~~~

 * SPDX-License-Identifier: Apache-2.0
 */

import { Context, Contract, Info, Returns, Transaction } from 'fabric-contract-api';
import { MyAsset } from './my-asset';

@Info({title: 'MyAssetContract', description: 'My Smart Contract' })
export class MyAssetContract extends Contract {

    @Transaction(false)
    @Returns('boolean')
    public async myAssetExists(ctx: Context, myAssetId: string): Promise<boolean> {
        const buffer = await ctx.stub.getState(myAssetId);
        return (!!buffer && buffer.length > 0);
    }

    @Transaction()
    public async createMyAsset(ctx: Context, myAssetId: string, value: string): Promise<void> {
        const exists = await this.myAssetExists(ctx, myAssetId);
        if (exists) {
            throw new Error(`The my asset ${myAssetId} already exists`);
        }
        const myAsset = new MyAsset();
        myAsset.value = value;
        const buffer = Buffer.from(JSON.stringify(myAsset));
        await ctx.stub.putState(myAssetId, buffer);
    }

    @Transaction(false)
    @Returns('MyAsset')
    public async readMyAsset(ctx: Context, myAssetId: string): Promise<MyAsset> {
        const exists = await this.myAssetExists(ctx, myAssetId);
        if (!exists) {
            throw new Error(`The my asset ${myAssetId} does not exist`);
        }
        const buffer = await ctx.stub.getState(myAssetId);
        const myAsset = JSON.parse(buffer.toString()) as MyAsset;
        return myAsset;
    }

    @Transaction()
    public async updateMyAsset(ctx: Context, myAssetId: string, newValue: string): Promise<void> {
        const exists = await this.myAssetExists(ctx, myAssetId);
        if (!exists) {
            throw new Error(`The my asset ${myAssetId} does not exist`);
        }
        const myAsset = new MyAsset();
        myAsset.value = newValue;
        const buffer = Buffer.from(JSON.stringify(myAsset));
        await ctx.stub.putState(myAssetId, buffer);
    }

    @Transaction()
    public async deleteMyAsset(ctx: Context, myAssetId: string): Promise<void> {
        const exists = await this.myAssetExists(ctx, myAssetId);
        if (!exists) {
            throw new Error(`The my asset ${myAssetId} does not exist`);
        }
        await ctx.stub.deleteState(myAssetId);
    }

}
~~~~

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Learning Objective 4: How to launch the brand new IBM Blockchain Platform 2.0 in the IBM Cloud

### Free IBM Cloud sign-up link: [https://ibm.biz/BdzMtC](https://ibm.biz/BdzMtC)

<img src="login.png">

[How to apply promocodes](https://www.slideshare.net/LennartF/pcode)

### IBM Cloud Catalog link: [https://cloud.ibm.com/catalog/](https://cloud.ibm.com/catalog)

### 1) Find IBM Blockchain Platform service in the IBM Cloud: [https://cloud.ibm.com/catalog?search=blockchain](https://cloud.ibm.com/catalog?search=blockchain). 

<img src="IBP_2.0.png">

IAM Enabled= "Identity and Access Management"

### 2) Launch IBM Blockchain Platform Service

<img src="Bchain_platform.png">

<a href="https://developer.ibm.com/series/ibm-blockchain-platform-console-video-series/">IBM Blockchain Platform Console Video Series. Follow along this four part series to set up a business network on the IBM Blockchain Platform</a>

<a href="https://developer.ibm.com/videos/deploy-a-peer-on-the-ibm-blockchain-platform/">Deploy a Peer on the IBM Blockchain Platform</a>

<a href="https://developer.ibm.com/videos/deploy-an-ordering-service-on-the-ibm-blockchain-platform/">Deploy an Ordering Service on the IBM Blockchain Platform</a>

<a href="https://developer.ibm.com/videos/create-and-join-a-channel-on-the-ibm-blockchain-platform/">Create and join a channel on the IBM Blockchain Platform</a>

### 3) [Select Kubernetes Cluster](https://cloud.ibm.com/kubernetes/catalog/cluster) in the IBM Cloud

<a href="https://cloud.ibm.com/docs/services/blockchain?topic=blockchain-ibp-saas-pricing">Blockchain IBP Pricing</a>
"** Preview the IBM Blockchain Platform at no charge for 30 days when you link your IBM Blockchain Platform service instance to an IBM Cloud Kubernetes free cluster. Performance will be limited by throughput, storage and functionality. IBM Cloud will delete your Kubernetes cluster after 30 days and you cannot migrate any nodes or data from a free cluster to a paid cluster. "


### 4) IBM Blockchain Platform Console installed in IBM Cloud.

<img src="IBP2.png" length="300" height="600">

### [Build a Network Tutorial with the IBM Blockchain Platform ](https://cloud.ibm.com/docs/services/blockchain/howto?topic=blockchain-ibp-console-build-network#ibp-console-build-network-sample-tutorial)

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">
# Appendix 

## Debugging NPM

1. The application uses Node.js and can sometimes get the wrong version of Node.
1. If npm install gets errors,
1. do: npm rebuild, npm install
1. And if that doesn't work, do:
1. nvm use 8.12.0 npm install or nvm use 8.12.0 npm rebuild npm install
1. the same if npm start gets errors
1 You can also do the same if Visual Studio Code console, Local Fabric Ops pane, do Teardown and Restart Fabric Runtime
1. If you get an error can't find xcode, do xcode-select --install



## Where do we go from here? 

[Creating a basic Blockchain network using the IBM Blockchain Platform V2.0](https://github.com/IBM/Create-BlockchainNetwork-IBPV20)

[SmartContract Trading using IBM Blockchain Platform Extension for VSCode (supports Fabric 1.4](https://github.com/IBM/SmartContractTrading-wFabric1-4-VSCodeExt)
 
[Build a blockchain insurance app](https://developer.ibm.com/patterns/build-a-blockchain-insurance-app/)

[IBM Developer SF Bay Area](https://www.meetup.com/IBM-Developer-SF-Bay-Area-Meetup/)

[IBM SF Bay Area Meetups](https://www.meetup.com/IBM-Developer-SF-Bay-Area-Meetup/events/)
  
vcpi: https://cloud.ibm.com/registration/?cm_mmc=Email_Events-_-Developer_Innovation-_-WW_WW-_-alf\letstakeibmblockchainplatformforaspin-sanfrancisco-7112019\Jul2019\lunchandlearn\global-devadvgrp-sanfrancisco\sanfrancisco\unitedstates\blockchain\build-an-asset-leasing-application-using-blockchain-and-iot\coffee-supply-chain-network-hyperledger-fabric-blockchain-2&cm_mmca1=000019RS&cm_mmca2=10004805&cm_mmca3=M99938765&eventid=5d13ab047cd80a5f7ef03d6c&cvosrc=email.Events.M99938765&cvo_campaign=000019RS

# [Truffle Reference Project](https://superblocks.com/d/superblocks/projects/reference-projects/)

[![Superblocks](https://superblocks.com/d/superblocks/projects/reference-projects.svg?branch=master)](https://superblocks.com/d/superblocks/projects/reference-projects)

Truffle reference repository to showcase Superblocks functionality on how to build and deploy your Ethereum contract projects


## Features this project showcases
* Fully automate your build proccess using Superblocks CI
* Automate, track, sing and deploy your transactions using Superblocks


## Quick start
Below is described how to get the a **Truffle** project setup and running locally.


### Install node modules
```sh
npm i
```

<br/>

## Setup 

### Configure the from address
In order to make sure you are broadcasting and signing the txs with the right account, you need to setup the `from` property in the `truffle-config.js` to which ever account you would like to perform the deployments with. 

### Configure your ENV variables

Env variables to setup for the intial config:
TOKEN -> A generated project token in the Superblocks platform. 
PROJECT_ID -> The deployment space id into which you want to track your deployment with. 

In order to get this values setup, follow the this instructions: 

#### PROJECT_ID
1. Login into Superblocks using your Github user.
2. If you haven't created an organization/project, create one.
3. Once your project is created, head to the project settings
4. You will find the project id under the General section

#### DEPLOY_TOKEN
1. Login into Superblocks using your Github user.
2. If you haven't created an organization/project, create one.
4. Once your project is created, head to the project settings
5. Go to the section `Tokens`, give your token a fancy name and click in `Generate`. Copy the generated key. 
6. Finally set "TOKEN" env variable for that project with project id obtained on step 5.


<br/>

## Performing the deployment (Running the truffle migrations)
Place the newly created values directly in the `truffle-config.js` file (not really recommended to leave those values hardcoded in the repo) and run:

```
npx truffle  migrate --network=rinkeby_metamask --verbose-rpc --reset
```

### Signing and broadcasting the Txs to the blockchain
Finally once everything is setup, you will see that our super provider will route the RPC calls for sending transactions to our plaform. Head to the dashboard and open your deployment space and you will see a new environment and a the last deployment created for you. Simply click in the deploymentId and you will be taken to the deployment details page. 

So whenever Truffle is trying to send a new txs to the chain, we will re-route it and display it for you in the UI. Simply click the `Sign` button, approve the tx in Metamask (make sure the selected account matches the one configure in the `truffle-config.js` and the selected network also matches), and the transaction will be deployed to the chain. Once this is done, we will send all the way back to Truffle the txReceipt hash so your deployment can continue. 

Repeat this proccess until all your txs are signed and succesfully deployed. 

### Artifact collection

Once you have done a deployment, you can collect all the artifacts generated during your deployment routine to always have them accessible and unlock other set o features like contract interaction 

In order to see how to start collecting artifacts for your project, check out our [Superblocks CLI project](https://github.com/SuperblocksHQ/super-cli)

#### Suported Frameworks
 - Truffle












 
 












# EthereumBoilerPlate

### Disclaimer

This boilerplate is for development and education purpose.  
Please don't use it for production as it is not tested and might have some security issues.

## Introduction

This boilerplate is to make the ease for the developer who don't want to go through the setting up the entire environment
for every application.  
A special thanks to Stephen Grider for his ethereum course.

## System Requirement

1. Python 2.7
2. Node js (It is tested on v8.11 but it will work on other node modules too)

#### For Windows User

You might require Microsoft build tools.

## Instruction to run the BoilerPlate

From the EthereumBoilerPlate Folder

> npm install

To compile the contract stored in ethereum/contracts folder

> node ./ethereum/compile.js

To deploy the contract

> node ./ethereum/deploy.js

#### For Linux Users

Update the package.json to this

> "ganache": "NODE_ENV=GANACHE node ./server/index.js",
> "ganacheDeploy": "NODE_ENV=GANACHE node ./ethereum/deploy"

## Brief overview of all the folders

### ethereum

All the code related to ethereum.

#### contracts

Compile command will check this contract directory to compile the contract  
**NOTE: You must change the contract file name in compile.js file**

#### build

The compiled contract will be stored in this folder.

Run compile.js

> npm run compile

#### web3.js

This file defines which network to use. Ganache or Rinkeby  
If you're using metamask it will work according to metamask.  
If you don't want to use metamask or local ganache-cli and want to use Rinkeby then  
create .env file in root folder and save the following entry

> TRUFFLE_HD_WALLET_KEY="your wallet/metamask seed words"  
> INFURA_API="Your infura api"

For Infura API just sign up in Infura.io and generate an API according to the network you want to use

#### deploy.js

This folder will take the compiled contract from build folder and network details from web3.js and then deploy the contract accordingly.

> npm run deploy

#### receipt-ganache/rinkeby.json

Receipt from the deploy.js saved here according to the network

#### logic.js

From this file with the help of receipt.json and web3.js you can interact with the deployed contract.

### server

All the code related to server

#### routes/contractAPI.js

Instead of going manually compiling and deploying the contract you can use these API.  
Make sure you comment the compile.js and deploy.js function call. Both are in the bottom of each file.

#### index.js

This will server the contractAPI at 4000 port by default.  
You can change this using .env file.  
In .env file just make a entry of PORT=8080

## React Application

From client directory

> npm start

Application will serve on http://localhost:3000

# References

HTML and CSS : https://codeburst.io/build-a-weather-website-in-30-minutes-with-node-js-express-openweather-a317f904897b

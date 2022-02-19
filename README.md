# pet-shop-tutorial

Tutorial on the process of building a dApp - an adoption tracking system for a pet shop.

[Source 🏹](https://trufflesuite.com/tutorial/index.html#writing-the-smart-contract)

## [Ganache](https://trufflesuite.com/ganache/) - ONE CLICK BLOCKCHAIN

**Ganache** is a development environment Ethereum blockchain for deploying contracts, developing applications, and running tests.

[Download Ganache here](https://trufflesuite.com/ganache/).

Make it executable:

```sh
chmod a+x ganache-x.y.z-os-arch.AppImage
```

Start it up!

```sh
./ganache-x.y.z-os-arch.AppImage
```

You can choose to `enable` or `disable` _Google Analytics_.

`Quickstart` for a one-click blockchain.

## [Truffle](https://trufflesuite.com/)

Install Truffle:

```sh
npm install -g truffle
```

Verify Installation:

```sh
truffle version
```

Compile Contracts:

```sh
truffle compile
```

Run Tests:

```sh
truffle test
```

Migrate Contracts to (Ganache) Ethereum Blockchain:

```sh
truffle migrate
```

## [MetaMask](https://github.com/MetaMask)

[Install MetaMask in your web browser](https://metamask.io/).

Import or Create a wallet.

Create Password and Secret Recovery Phrase.

Install `lite-server`:

```sh
npm install lite-server --save-dev
```

Start dApp:

```sh
npm run dev
```

## Directory structure

- `contracts/` Solidity smart contract source files

- `migrations/` Truffle blockchain deployment migration files

- `src/` SPdApp

- `test/` Smart contract unit tests

## Configuration

`truffle-config.js`

### General options

`build`

#### Running an external command

```js
module.exports = {
  // This will run the `webpack` command on each build.
  //
  // The following environment variables will be set when running the command:
  // WORKING_DIRECTORY: root location of the project
  // BUILD_DESTINATION_DIRECTORY: expected destination of built assets (important for `truffle serve`)
  // BUILD_CONTRACTS_DIRECTORY: root location of your build contract files (.sol.js)
  //
  build: "webpack"
}
```

#### Providing a custom function

```js
module.exports = {
  build: function(options, callback) {
     // Do something when a build is required. `options` contains these values:
     //
     // working_directory: root location of the project
     // contracts_directory: root directory of .sol files
     // destination_directory: directory where truffle expects the built assets (important for `truffle serve`)
  }
}

```

#### Creating a custom module

```js
var DefaultBuilder = require("truffle-default-builder");
module.exports = {
  build: new DefaultBuilder(...) // specify the default builder configuration here.
}
```

#### Bootstrapping your application

```js
// Step 1: Get a contract into my application
var json = require("./build/contracts/MyContract.json");

// Step 2: Turn that contract into an abstraction I can use
var contract = require("@truffle/contract");
var MyContract = contract(json);

// Step 3: Provision the contract with a web3 provider
MyContract.setProvider(new Web3.providers.HttpProvider("http://127.0.0.1:8545"));

// Step 4: Use the contract!
MyContract.deployed().then(function(deployed) {
  return deployed.someFunction();
});
```

## Layout of a Solidity Source File

`// SPDX-License-Identifier: MIT`

`pragma solidity ^x.y.z;`

`pragma solidity >=0.4.0 <0.9.0;`

`import * as symbolName from "filename";`

`import "filename" as symbolName;`

`import {symbol1 as alias, symbol2} from "filename";`

```js
// This is a single-line comment.

/*
This is a
multi-line comment.
*/
```

```js
contract SampleContract {
  // Integers
  int8 signed8BitsStateVar;
  int16 signed16BitsStateVar;
  int24 signed24BitsStateVar;
  // ...
  int248 signed248BitsStateVar;
  int256 signed256BitsStateVar;
  uint8 unSigned8BitsStateVar;
  uint16 unSigned16BitsStateVar;
  uint24 unSigned24BitsStateVar;
  // ...
  uint248 unSigned248BitsStateVar;
  uint256 unSigned256BitsStateVar;
  // Booleans
  bool youAreGreat = true;
  bool youStink = false;
  // Address
  address etherAddress20Byte;
  address payable payableEtherAddress20Byte;
}
```

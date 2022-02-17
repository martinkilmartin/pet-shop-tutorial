# pet-shop-tutorial
Tutorial on the process of building a dApp - an adoption tracking system for a pet shop.

[Source 🏹](https://trufflesuite.com/tutorial/index.html#writing-the-smart-contract)

## [Ganache](https://trufflesuite.com/ganache/) - ONE CLICK BLOCKCHAIN


__Ganache__ is a development environment Ethereum blockchain for deploying contracts, developing applications, and running tests.

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

## [Truffle]()

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

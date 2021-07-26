# Deploy UniswapV3 Template

This repo is used to deploy uniswapV3 contract to ethereum network.

## Usage

### Pre Requisites

Before running any command, make sure to install dependencies:

```sh
$ yarn install
```

### Deploy contract to network (requires Mnemonic and infura API key)

Prepare env file

```sh
$ mv .env.example .env

# Config your MNEMONIC and INFURA_API_KEY in .env
MNEMONIC=test test test test test test test test test test test test
INFURA_API_KEY=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
```

Deploy to ethereum network

```sh
$ npx hardhat deploy-uniswap --network goerli --verbose
```

## Donate

ETH: 0x67CF3bF40b2b3b3D68F6c361AEf81F8AEb2dB637

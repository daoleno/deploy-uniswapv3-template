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
ETHERSCAN_API_KEY=YYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYYY
```

Deploy to ethereum network

```sh
$ npx hardhat deploy-uniswap --network goerli --verbose
```

Verify constracts

```sh
# verify factory contract
$ npx hardhat verify --config hardhat.config.factory.ts --network goerli factory_address

# verify quoter contract
$ npx hardhat verify --config hardhat.config.router.ts --network goerli quoter_address "factory_address" "weth9_address"

# verify router contract
$ npx hardhat verify --config hardhat.config.router.ts --network goerli router_address "factory_address" "weth9_address"

# verify nftDescriptorLibrary contract
$ npx hardhat verify --config hardhat.config.nftDescriptor.ts --network goerli nftDescriptorLibrary_address

# verify positionDescriptor
$ npx hardhat verify --config hardhat.config.nftDescriptor.ts --network goerli positionDescriptor_address "weth9_address"

# verify positionManager
$ npx hardhat verify --config hardhat.config.positionManager.ts --network goerli positionManager_address "factory_address" "weth9_address" "positionDescriptor_address"
```

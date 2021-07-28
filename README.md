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
# replace 0xd94F4EC8bF697c0920579d4EbDD16a290F618ED3 with your own factory address
$ npx hardhat verify --config hardhat.config.factory.ts --network goerli 0xd94F4EC8bF697c0920579d4EbDD16a290F618ED3

# verify router contract
# replace 0x0947E67A07AEa5e0662c4DCD5276C80Fe7ee10Fc with your own router address
# replace 0xd94F4EC8bF697c0920579d4EbDD16a290F618ED3 with your own factory address
# replace 0x0d6Ed38E47E59A9F4604ebEd0e0FBbDD1022c4Fd with your own weth9 address
$ npx hardhat verify --config hardhat.config.router.ts --network goerli 0x0947E67A07AEa5e0662c4DCD5276C80Fe7ee10Fc "0xd94F4EC8bF697c0920579d4EbDD16a290F618ED3" "0x0d6Ed38E47E59A9F4604ebEd0e0FBbDD1022c4Fd"

# verify nftDescriptorLibrary contract
# replace 0x516976D18ed6DeE253AB35037206f0192BdB5784 with your own nftDescriptorLibrary address
$ npx hardhat verify --config hardhat.config.nftDescriptor.ts --network goerli 0x516976D18ed6DeE253AB35037206f0192BdB5784

# verify positionDescriptor
# replace 0xa839543F1d5ea5b4E6D2deB7cdDE0b6483686900 with your own positionDescriptor address
# replace 0x0d6Ed38E47E59A9F4604ebEd0e0FBbDD1022c4Fd with your own weth9 address
$ npx hardhat verify --config hardhat.config.nftDescriptor.ts --network goerli 0xa839543F1d5ea5b4E6D2deB7cdDE0b6483686900 "0x0d6Ed38E47E59A9F4604ebEd0e0FBbDD1022c4Fd"

# verify positionManager
# replace 0x5D07aAA7eA611e02763eE9FBb4b8e7Bb804C17fa with your own positionManager address
# replace 0xd94F4EC8bF697c0920579d4EbDD16a290F618ED3 with your own factory address
# replace 0x0d6Ed38E47E59A9F4604ebEd0e0FBbDD1022c4Fd with your own weth9 address
# replace 0xa839543F1d5ea5b4E6D2deB7cdDE0b6483686900 with your own positionDescriptor address
$ npx hardhat verify --config hardhat.config.positionManager.ts --network goerli 0x5D07aAA7eA611e02763eE9FBb4b8e7Bb804C17fa "0xd94F4EC8bF697c0920579d4EbDD16a290F618ED3" "0x0d6Ed38E47E59A9F4604ebEd0e0FBbDD1022c4Fd" "0xa839543F1d5ea5b4E6D2deB7cdDE0b6483686900"
```

## Donate

ETH: 0x67CF3bF40b2b3b3D68F6c361AEf81F8AEb2dB637

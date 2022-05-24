# Dixel Club V2

Pixel Art NFT factory that users can:
1. Creators: Create a new NFT collection with a 24x24 pixel art canvas with following parameters
    - name
    - symbol
    - description
    - max minting supply (1 - 1,000,000)
    - minting cost - in native currency (ETH, BNB, KLAY) (95% goes to creator / 5% platform fee)
    - royalty (receiving address, percentage: 0 - 10%)
    - minting initiation time (unix timestamp)
    - whitelistOnly (boolean)
      - whitelist can be added by the creator later (wallet address, minting allowance)
2. Collectors: Mint a new edition on an existing collection with color variations

## Run Tests
```bash
npx hardhat test
```

## Contracts

### Ethereum Testnet (Goerli)
- Test DIXEL token: 0x6D96ECf4E598dd4FeC0c4CBB3862E3bCcf28A144
- DixelClubV2Factory: 0x5663A199Fae99639d80282cbb6Ff751c6Cff6F01
- DixelClubV2NFT: 0x312e3AC6297baf2671eaBaCC015c36dEFf7eE79d

### Klaytn Testnet

### BSC Testnet

## Deploy
```bash
npx hardhat compile

HARDHAT_NETWORK=bscmain node scripts/deploy.js

# Verify source code on Etherscan
npx hardhat verify --network bscmain {contract address} "parameter 1" "parameter 2"
```

## Gas Consumption
```
·----------------------------------------------------|---------------------------|--------------|-----------------------------·
|                Solc version: 0.8.13                ·  Optimizer enabled: true  ·  Runs: 1500  ·  Block limit: 60000000 gas  │
·····················································|···························|··············|······························
|  Methods                                           ·               25 gwei/gas                ·       1988.51 usd/eth       │
····························|························|·············|·············|··············|···············|··············
|  Contract                 ·  Method                ·  Min        ·  Max        ·  Avg         ·  # calls      ·  usd (avg)  │
····························|························|·············|·············|··············|···············|··············
|  DixelClubV2Factory       ·  createCollection      ·    1338240  ·    1383212  ·     1356210  ·           70  ·      67.42  │
····························|························|·············|·············|··············|···············|··············
|  DixelClubV2Factory       ·  updateBeneficiary     ·          -  ·          -  ·       39442  ·            3  ·       1.96  │
····························|························|·············|·············|··············|···············|··············
|  DixelClubV2Factory       ·  updateImplementation  ·          -  ·          -  ·       28949  ·            3  ·       1.44  │
····························|························|·············|·············|··············|···············|··············
|  DixelClubV2NFT           ·  addWhitelist          ·      56929  ·     218934  ·      113730  ·           20  ·       5.65  │
····························|························|·············|·············|··············|···············|··············
|  DixelClubV2NFT           ·  mint                  ·     199311  ·     241409  ·      225527  ·           28  ·      11.21  │
····························|························|·············|·············|··············|···············|··············
|  DixelClubV2NFT           ·  setApprovalForAll     ·          -  ·          -  ·       48943  ·            1  ·       2.43  │
····························|························|·············|·············|··············|···············|··············
|  ERC20                    ·  approve               ·          -  ·          -  ·       51478  ·            1  ·       2.56  │
····························|························|·············|·············|··············|···············|··············
|  ERC20PresetMinterPauser  ·  burn                  ·      60311  ·      78207  ·       64081  ·            7  ·       3.19  │
····························|························|·············|·············|··············|···············|··············
|  Deployments                                       ·                                          ·  % of limit   ·             │
·····················································|·············|·············|··············|···············|··············
|  ColorUtilsMock                                    ·          -  ·          -  ·      298893  ·        0.5 %  ·      14.86  │
·····················································|·············|·············|··············|···············|··············
|  DixelClubV2Factory                                ·          -  ·          -  ·     5474166  ·        9.1 %  ·     272.14  │
·····················································|·············|·············|··············|···············|··············
|  DixelClubV2NFTMock                                ·          -  ·          -  ·     4316792  ·        7.2 %  ·     214.60  │
·----------------------------------------------------|-------------|-------------|--------------|---------------|-------------·
```

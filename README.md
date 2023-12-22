## Doc

https://www.quicknode.com/guides/solana-development/nfts/how-to-deploy-an-nft-collection-on-solana-using-sugar-candy-machine-umi

https://developers.metaplex.com/candy-machine/sugar

https://www.solaneyes.com/address/BRB64ACEfWzzzX1MdpAbRaFAfEBGphjGD7Kq3xrpM5YU?cluster=devnet

## sugar code
config.json

 ```
 {
    "number": 10,
    "symbol": "NB",
    "sellerFeeBasisPoints": 500,
    "isMutable": true,
    "isSequential": true,
    "ruleSet": null,
    "creators": [
        {
            "address": "YOUR_WALLET_ADDRESS",
            "share": 100
        }
    ],    
    "uploadMethod": "bundlr",
    "awsS3Bucket": null,
    "retainAuthority": true,
    "awsConfig": null,
    "nftStorageAuthToken": null,
    "shdwStorageAccount": null,
    "pinataConfig": null,
    "hiddenSettings": null,
    "guards": {
        "default": {
          "solPayment": {
            "value": 0.01,
            "destination": "YOUR_WALLET_ADDRESS"
          },
          "startDate": {
            "date": "2022-10-23T20:00:00Z"
          }
        }
      }    
}
 ```   

### validate Assets
`sugar validate`
验证 assets 文件夹下的 png 和 json 文件，必须从0顺序开始
```
sugar-demo/
├── config.json
└── assets/
  ├── [0-9].png
  ├── [0-9].json
  ├── collection.png
  └── collection.json
```

### upload Assets (image and json)
`sugar upload`

get cache.json

### deploy Assets  
`sugar deploy`

### verify Candy Machine
`sugar verify`

### add Candy Guards
默认情况下，当您部署糖果机时，只有您可以铸造 NFT。您必须实施糖果守卫来定义其他人可以铸造您的 NFT 的标准（例如，开始时间、支付金额、支付代币、白名单代币等）。由于我们已经在config.json 中定义了守卫 ，因此我们可以运行以下命令：

`sugar guard add`

### 更新 Candy Guard 配置
`sugar guard update`

### 打印 the on-chain configuration of the Candy Machine guards
`sugar guard show`

### 更新 config.json sellerFeeBasisPoints
`sugar deploy`
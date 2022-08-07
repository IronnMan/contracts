# BSC/HECO 全能分红代币合约

支持分红 SHIB/ETH/USDT/DOGE 等代币。

该合约仅支持`BNB`或`HT`池子，不支持`USDT`或其他池子，不支持分红 `BNB`、`WBNB`、`HT`、`WHT`

- 2022-08-16 更新:
  - 为感谢各位朋友支持，分红合约移除`serviceAddr_`参数，去除收费逻辑，代币完全公开且免费。
  - 增加 BSC 测试网支持。
  - 增加 HECO 主网支持。
  - 部署时增加分红代币校验。防止填错代币合约仍然可以部署，在交易时才发现报错。
  - 移除部署时所有税费合计不超过 25%的限制。
  - 在不改变核心功能的前提下，优化部分交易逻辑，减少交易过程中可能出现的报错。
- 2022-02-19 更新: 修改部分关键词。绕过查币软件检测。

## 源码

BSC 主网（PancakeSwap） `RedKing_bsc_mainnet_56.sol`

BSC 测试网（BSCTestNetSwap）`RedKing_bsc_testnet_97.sol`

HECO 主网（MDEXSwap）`RedKing_heco_mainnet_128.sol`

## 实战视频讲解

https://youtu.be/trql3DDUb4Q

2022-08-16 更新后与视频讲解略有不同。部署时无需填写 Value 和 serviceAddr\_

## TG 技术交流群

https://t.me/dexmax8

## 编译/开源参数

```
COMPILER: v0.8.7+commit.e28d00a7.js
Enable optimization: 开启并使用默认值200
Other Settings: default evmVersion, MIT license
```

## 部署参数

CONTRACT 选择 `RedKing`

~~Value `200000000000000000` （0.2BNB）~~ **2022-08-06 改为完全免费，不要再填 Value**

```
name_: RedKing Token (代币名称)
symbol_: RedKing (代币符号)
totalSupply_: 1000000000000000 (发行量)
rewardAddr_: 要分红的代币合约，BSC常用代币地址在下方
marketingWalletAddr_: 自己的市场营销钱包
serviceAddr_: 已于2022-08-06移除该参数，无需填写
buyFeeSetting_: [4,3,2,1] (分红、流动性、市场营销、燃烧)
sellFeeSetting_: [5,4,3,2] (分红、流动性、市场营销、燃烧)
tokenBalanceForReward_: 1000000000000000000000000000 (持有多少代币参与分红。数量后要加18个0)
```

## 常用合约地址

### BSC 主网

```
薄饼Swap路由: 0x10ED43C718714eb63d5aA57B78B54704E256024E

USDT: 0x55d398326f99059fF775485246999027B3197955
ETH: 0x2170Ed0880ac9A755fd29B2688956BD959F933F8
SHIB: 0x2859e4544C4bB03966803b044A93563Bd2D0DD4D
DOGE: 0xbA2aE424d960c26247Dd6c32edC70B295c744C43
```

### BSC 测试网

测试网分红币建议使用 USDT 或 SHIB。不要用 CAKE 或其他代币。其他代币因为流动性问题，部署后交易会报错。通常表现为只能买不能卖。

```
测试Swap路由: 0xB6BA90af76D139AB3170c7df0139636dB6120F7e

USDT: 0xEdA5dA0050e21e9E34fadb1075986Af1370c7BDb
SHIB: 0x11e815a78Cc41D733Db00f06B3A96074855362CE
```

### HECO 主网

```
MDEX Swap路由: 0xED7d5F38C79115ca12fe6C0041abb22F0A06C300

USDT: 0xa71edc38d189767582c38a3145b5873052c3e47a
ETH: 0x64ff637fb478863b7468bc97d30a5bf3a428a1fd
BTC: 0x66a79d23e58475d2738179ca52cd0b41d73f0bea
```

## Remix IDE

https://remix.ethereum.org

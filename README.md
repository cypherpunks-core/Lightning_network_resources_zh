# 閃電網路資源整理 

## 比特幣資源
比特幣是一種基於去中心化，採用點對點網路與共識主動性，開放原始碼，以區塊鏈作為底層技術的加密貨幣，比特幣由中本聰於2008年10月31日發表論文

### 區塊鏈概述

* [區塊鏈技術漫談](區塊鏈技術漫談.md)

### 比特幣的基礎知識
* 影-[比特幣和區塊鏈到底是啥？礦機挖礦咋回事？李永樂老師講比特幣(1)](https://www.youtube.com/watch?v=g_fSistU3MQ)

* 影-[比特幣交易如何防偽？私鑰公鑰地址啥意思？李永樂老師講比特幣（2）](
https://www.youtube.com/watch?v=pbAVauYsqP0)
* 影-[你有疑惑過比特幣(與其他加密貨幣)的運作原理嗎？(純英文)](https://youtu.be/bBC-nXj3Ng4)
* 影-[你有疑惑過比特幣(與其他加密貨幣)的運作原理嗎？(簡中字幕)](https://www.bilibili.com/video/av12465079)
* 書-[Mastering Bitcoin 第二版 繁中](https://forum.cypherpunks.tech/t/topic/131)
* 課程-[課程：區塊鏈技術與應用](https://docs.google.com/document/d/1R2lQ3NN6IFYT3fQ2G5D8TRcTw2bd4JTNMW8QbKimu8Q/edit?fbclid=IwAR3lpqDPNpelERgr_KHaHCBRI0R0QXQUn2tifwCEzfpXJpX8XWaHzPrqn5s#heading=h.3n87a6jtx1p1)
* 課程-[課程：以太坊原理與應用開發](https://docs.google.com/document/d/16V3HBwE78-vOex58P8s59TMxifhQi85_-whUd1ACd40/edit?fbclid=IwAR3mVk1wy40fglSFmNEi-CrELvmjv963Zdu0wQING4SSE4IA0dd9JzDpWdQ#heading=h.3n87a6jtx1p1)

## 閃電網路協議 | Lightning Network Protocol
閃電網路是一個提議端到端連接的雙向支付通道路由網路。像這樣的網路可以允許任何參與者在無需信任任何中間人的情況下將支付從通道發送到通道。[閃電網路](https://lightning.network/lightning-network-paper.pdf)  [由Joseph Poon和Thadeus Dryja於2015年2月首先描述]，建立在許多其他人提出和闡述的支付通道的概念上。

“閃電網路”是指用於路由支付通道網路的特定設計，現在已經由至少五個不同的開源團隊實現。獨立實現由一組互操作性標準進行協調：http://bit.ly/2rBHeoL[ Basics of Lightning Technology (BOLT) paper]。

閃電網路的原型實現已由多個團隊發佈。目前，這些實現只能在testnet上運行，因為它們使用segwit，而沒有在主比特幣區塊鏈（mainnet）上激活。

### 規格/白皮書 | Specifications / White Papers

* [閃電網白皮書-簡中](https://github.com/ChenPoWei/bitcoincn/blob/master/%E6%AF%94%E7%89%B9%E5%B8%81%E9%97%AA%E7%94%B5%E7%BD%91%E7%BB%9C%E7%99%BD%E7%9A%AE%E4%B9%A6%EF%BC%9A%E5%8F%AF%E6%89%A9%E5%B1%95%E7%9A%84%20off-chain%20%E5%8D%B3%E6%97%B6%E6%94%AF%E4%BB%98%EF%BC%88%E4%B8%AD%E6%96%87%EF%BC%89.pdf)
* [閃電網白皮書-英文](https://lightning.network/lightning-network-paper.pdf)
* [閃電網路規範](https://github.com/lightningnetwork/lightning-rfc)
* [LND API參考](http://api.lightning.community/)
* [可部署的閃電白皮書](https://github.com/ElementsProject/lightning/blob/master/doc/deployable-lightning.pdf)
* [比特幣微支付信道網路的可擴展資金](https://www.tik.ee.ethz.ch/file/a20a865ce40d40c8f942cf206a7cba96/Scalable_Funding_Of_Blockchain_Micropayment_Networks%20(1).pdf)

### 實現 | Implementations

閃電網路協議的實現

* [LND](https://github.com/lightningnetwork/lnd) -  Lightning Network Daemon(Golang)
* [eclair](https://github.com/ACINQ/eclair) - 閃電網路的Scala實現(Scala)
* [lit](https://github.com/mit-dci/lit) -  Lightning Network節點軟件(Golang)
* [c-lightning](https://github.com/ElementsProject/lightning) -  C中的Lightning Network實現
* [lightning-onion](https://github.com/lightningnetwork/lightning-onion) - 閃電網路的洋蔥路線微支付(Golang)
* [ptarmigan](https://github.com/nayutaco/ptarmigan) - 符合C ++ BOLT標準的Lightning網路實現[Incomplete]



## 瀏覽器 |  Explorers
* [acinq.co](https://explorer.acinq.co/)
* [1ML](https://1ml.com/) -  1ML資源管理器(mainnet + testnet)
* [itcoinExchangeRate.org (Bitcoin 匯率)](https://bitcoinexchangerate.org/lightning) -  Lightning網路瀏覽器(testnet和mainnet)
* [Lightblock](https://lightblock.me) - 閃電網路資源管理器主網。
* [Lightning network explorer](https://explorer.acinq.co/) -  Lightning網路瀏覽器(testnet)
* [資源管理器列表](https://gist.github.com/bretton/798ec38165ffabc719d91e0f4f67552d) - 可視化工具和指標網站的元列表
* [lngraph](https://github.com/xsb/lngraph) - 使用Neo4j瀏覽器的個人私人Lightning Network資源管理器。
* [Robtex比特幣Lightning Explorer](https://www.robtex.com/lightning/node/) -  Robtex比特幣Lightning Explorer(主網)

## 文章 | article

* [Bitcoin Lightning Network常見問題解答](/article/Bitcoin-Lightning-Network-FAQ.md)
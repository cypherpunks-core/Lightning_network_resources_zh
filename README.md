# 閃電網路資源整理 

## 比特幣資源
比特幣是一種基於去中心化，採用點對點網路與共識主動性，開放原始碼，以區塊鏈作為底層技術的加密貨幣，比特幣由中本聰於2008年10月31日發表論文

### 區塊鏈概述

* [區塊鏈技術漫談](區塊鏈技術漫談.md)

### 比特幣的基礎知識
* 影-[比特幣和區塊鏈到底是啥？礦機挖礦咋回事？李永樂老師講比特幣(1)](https://www.youtube.com/watch?v=g_fSistU3MQ)

* 影-[比特幣交易如何防偽？私鑰公鑰地址啥意思？李永樂老師講比特幣(2)](
https://www.youtube.com/watch?v=pbAVauYsqP0)
* 影-[你有疑惑過比特幣(與其他加密貨幣)的運作原理嗎？(純英文)](https://youtu.be/bBC-nXj3Ng4)
* 影-[你有疑惑過比特幣(與其他加密貨幣)的運作原理嗎？(簡中字幕)](https://www.bilibili.com/video/av12465079)
* 書-[Mastering Bitcoin 第二版 繁中](https://forum.cypherpunks.tech/t/topic/131)
* 課程-[課程：區塊鏈技術與應用](https://docs.google.com/document/d/1R2lQ3NN6IFYT3fQ2G5D8TRcTw2bd4JTNMW8QbKimu8Q/edit?fbclid=IwAR3lpqDPNpelERgr_KHaHCBRI0R0QXQUn2tifwCEzfpXJpX8XWaHzPrqn5s#heading=h.3n87a6jtx1p1)
* 課程-[課程：以太坊原理與應用開發](https://docs.google.com/document/d/16V3HBwE78-vOex58P8s59TMxifhQi85_-whUd1ACd40/edit?fbclid=IwAR3mVk1wy40fglSFmNEi-CrELvmjv963Zdu0wQING4SSE4IA0dd9JzDpWdQ#heading=h.3n87a6jtx1p1)

## 閃電網路協議 | Lightning Network Protocol
閃電網路是一個提議端到端連接的雙向支付通道路由網路。像這樣的網路可以允許任何參與者在無需信任任何中間人的情況下將支付從通道發送到通道。[閃電網路](https://lightning.network/lightning-network-paper.pdf)  [由Joseph Poon和Thadeus Dryja於2015年2月首先描述]，建立在許多其他人提出和闡述的支付通道的概念上。

“閃電網路”是指用於路由支付通道網路的特定設計，現在已經由至少五個不同的開源團隊實現。獨立實現由一組互操作性標準進行協調：http://bit.ly/2rBHeoL[ Basics of Lightning Technology (BOLT) paper]。

閃電網路的原型實現已由多個團隊發佈。目前，這些實現只能在testnet上運行，因為它們使用segwit，而沒有在主比特幣區塊鏈(mainnet)上激活。

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

###應用程序

#### 桌面界面

* [lightning-app](https://github.com/lightninglabs/lightning-app) - 跨平台Lightning桌面應用程序
* [lnd-gui](https://github.com/alexbosworth/lnd-gui) -  Lightning MacOS GUI錢包
* [eclair-node-gui](https://github.com/ACINQ/eclair) -  Lightning的跨平台桌面GUI
* [zap-desktop](https://github.com/LN-Zap/zap-desktop) -  Lightning Network桌面應用程序
* [Presto](https://github.com/icota/presto) - 基於c-lightning的桌面錢包
* [Lightning Peach錢包](https://github.com/LightningPeach/lightning-peach-wallet) -  Bitfury Lightning錢包
* [spark-wallet](https://github.com/shesek/spark-wallet) - 用於c-lightning的最小GUI; 可用作網路，移動和桌面應用程序
* [電壓](https://github.com/benharold/voltage) - 電壓是c-lightning的macOS GUI

#### Web界面

* [發現錢包](https://github.com/Lightning-Family/Discovery-Wallet) - 網路保管錢包; [現場演示](https://wallet.lightning.family)
* [fulmo](https://github.com/marzig76/fulmo) - 簡約的c-lightning UI
* [Joule](http://lightningjoule.com) - 一個鍍鉻擴展程序，支持與閃電應用程序的付款和其他交互(類似於MetaMask)
* [kugelblitz](https://github.com/cdecker/kugelblitz) - 一個簡單的用戶界面，用於c-lightning守護進程閃電和bitcoind
* [lncli-web](https://github.com/mably/lncli-web) - 用NodeJS / Angular編寫的lnd守護進程的輕量級Web客戶端
* [Ride The Lightning](https://github.com/ShahanaFarooqui/RTL) - 用NodeJS / Angular 7編寫的LND守護進程的Web客戶端

#### 移動應用程序

* [rawtx](https://github.com/rawtxapp/rawtxapp) - 閃電網路錢包(Android，iOS); [主頁](https://rawtx.com)
* [Swift Lightning](https://github.com/biscottigelato/SwiftLightning) - 在LND for iOS之上構建LN錢包
* [比特幣閃電錢包](https://play.google.com/store/apps/details?id=com.lightning.walletapp) - 基於Eclair的基於Android的Lightning Network兼容錢包([testnet版本](https： //play.google.com/store/apps/details?id=com.lightning.wallet))
* [Eclair Mobile](https://play.google.com/store/apps/details?id=fr.acinq.eclair.wallet.mainnet2)

#### 瀏覽器 |  Explorers
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

### 巴比特
比特幣閃電網路：可擴充套件的 Off-Chain即時支付
作者：Joseph Poon和Thaddeus Dryja
這可能是2015年裡最具影響力的論文，Poon和Dryja展示了他們的發明：比特幣閃電網路，它可以允許任何數量的參與者通過雙方支付通道，即時地進行交易。

閃電網路交易也是正常的比特幣交易，但是，除了極少數的情況下，這些交易實際上並不是在比特幣區塊鏈上發生的。因為大量的交易資料是私人儲存的，閃電網路交易會比on-chain的比特幣交易更為經濟，從而使得比特幣網路能夠負擔地起小額支付。

Poon和Dryja的願景可能很快就會實現，因為Blockstream正在努力推動閃電網路，使得該協議成為可能。

* [紅藥丸或藍藥丸：比特幣XT vs 閃電方案](https://www.8btc.com/article/67529)2015-09-17 18:40
* [閃電網路究竟是什麼，現在怎麼樣了？](https://www.8btc.com/article/67843)2015-09-22 10:18
* [揭穿關於閃電網路11個常見的謬見](https://www.8btc.com/article/70615)2015-10-20 14:36
* [閃電網路與以太坊結合建立支付渠道的構想及其前景](https://www.8btc.com/article/71843)2015-10-31 12:00
* [閃電網路懷疑論](https://www.8btc.com/article/76591)2015-12-29 07:30
* [閃電網路非常偉大，但它也面臨各種類型的問題](https://www.8btc.com/article/81289)2016-02-29 10:31
* [閃電網路之我見：比特幣網路的飛躍](https://www.8btc.com/article/85257)2016-03-31 18:13
* [比特幣閃電網路交易費用接近為零，交易吞吐量可擴充套件到百萬次每秒](https://www.8btc.com/article/85844)2016-04-07 22:41
* [探索比特幣閃電網路的中心化風險](https://www.8btc.com/article/89255)2016-05-10 14:39
* [詳解最近大熱的閃電網路、雷電網路和CORDA](https://www.8btc.com/article/92887)2016-06-12 12:26
* [Flare閃電網路新路由系統白皮書釋出，讓節點路由更加高效(白皮書全文下載)](https://www.8btc.com/article/96081)2016-07-08 12:20
* [美國約翰•霍普金斯大學釋出白皮書：匿名的鏈下輕量級交易Bolt實現高度隱私的小額支付(全文下載)](https://www.8btc.com/article/98771)2016-08-02 13:46
* [專訪閃電網路創始人：閃電網路最新進展及面臨問題](https://www.8btc.com/article/105225)2016-09-30 16:22
* [閃電網路所面臨的難題還遠未解決](https://www.8btc.com/article/109763)2016-11-17 15:56
* [閃電網路如何為比特幣網路新增隱私層？](https://www.8btc.com/article/113116)2016-12-20 12:13
* [閃電網路協議開發者Russell：沒有隔離見證的閃電網路是不優雅的](https://www.8btc.com/article/113250)2016-12-21 11:14
* [數學證明：閃電網路無法成為去中心化的比特幣擴容方案](https://www.8btc.com/article/132567)2017-07-04 08:45
* [Gavin Andresen：閃電網路是高度中心化的](https://www.8btc.com/article/137798)2017-08-17 
* [如何在Linux系統建立自己的閃電網路節點和通道](https://www.8btc.com/article/156211)2018-01-24 
* [Andreas Antonopoulos：關於閃電網路的六大誤解](https://www.8btc.com/article/163750)2018-02-23 08:22
* [閃電網路對比特幣隱私性的利弊](https://www.8btc.com/article/165281)2018-02-26 
* [閃電網路入門：如何傳送你的第一筆交易？](https://www.8btc.com/article/165568)2018-03-02
* [比特幣的未來？淺析閃電網路的優勢及創新之處](https://www.8btc.com/article/181491)2018-03-25 10:45
* [Blockstream LApp周，八款閃電網路應用盤點](https://www.8btc.com/article/186239)2018-03-30 18:41
* [比特幣的閃電網路受到攻擊——這對它來說是福還是禍？](https://www.8btc.com/article/188223)2018-04-05 08:44
* [詳解閃電網路的歷史——從頭腦風暴到測試版問世](https://www.8btc.com/article/189240)2018-04-09 09:39
* [閃電網路+ NFC ？新方法將比特幣帶入零售業](https://www.8btc.com/article/195237)2018-04-19 07:43
* [比特幣的擴容之路：閃電網路未來是什麼樣的？](https://www.8btc.com/article/202633)2018-05-07 08:44
* [閃電網路新技術出現：壓縮交易資料，保護使用者資金安全](https://www.8btc.com/article/214475)2018-05-30 15:57
* [c-lightning beta版本上線，標誌著閃電網路成長和發展的重要一天](https://www.8btc.com/article/226278)2018-06-26 13:34
* [閃電網路入門：什麼是閃電網路？它是如何運作的？](https://www.8btc.com/article/242957)2018-08-08 08:38
* [現在除了挖礦，你也可以通過閃電網路來賺取比特幣了](https://www.8btc.com/article/255731)2018-08-21 09:41
* [一文讀懂隔離見證](https://www.8btc.com/article/265462)2018-09-03 15:33
* [閃電 vs. 雷電：瞭望塔可拓展嗎? (上)](https://www.8btc.com/article/360567)2019-02-15 15:13
* [閃電 vs. 雷電：瞭望塔中的隱私保護方案 (中)](https://www.8btc.com/article/368399)2019-03-02 10:00
* [硬核乾貨 | 6000字讀懂閃電網路原理](https://www.8btc.com/article/362358)2019-02-18 22:10
* [AMA | 康奈爾大學教授：閃電網路雖好，但至少存在這4個問題](https://www.8btc.com/article/363404)2019-02-20 17:57
* [Blockstream釋出閃電網路軟體重大升級，增加最新‘外掛’功能](https://www.8btc.com/article/368520)2019-03-02 18:29

## 閃電網路 app
* [Lightning App Directory](https://dev.lightning.community/lapps/)
* [These are the Top 10 Lightning Apps out right now](https://kintu.co/lightning-apps/)

## 其他
* [Lightning network/Payment channel](https://drive.google.com/file/d/0B7rTe1bpN56HeDJfZFBjcWk4Tm8/view) by Brian Po-han Chen
* [【動區專題】五分鐘就看懂：圖說閃電網路](https://www.blocktempo.com/lightning-network/)
* [ Raiden Network — Ethereum 區塊鏈支付通道](https://medium.com/taipei-ethereum-meetup/raiden-network-ethereum-%E5%8D%80%E5%A1%8A%E9%8F%88%E6%94%AF%E4%BB%98%E9%80%9A%E9%81%93-c44cea954e9b)
* [閃電網路和雷電網路：擴容方案本身的擴容問題](https://medium.com/cryptocow/lightning-vs-raiden-1-can-watchtowers-and-monitoring-services-scale-f3b59906114b?fbclid=IwAR35vjbewlP6Y5y8tmynZt1KszE5L2pegT7GJbtpFnkHeZF7K35UGBbOMRg)
* [閃電網路/支付通道於Ethereum的基礎介紹 | 陳昶吾 | Taipei Ethereum Meetup #4 - Scalability 議題
](https://www.youtube.com/watch?v=pW615Yme2Ik)
* [簡單解釋比特幣的閃電網路 (Bitcoin's Lightning Network, Simply Explained!)](https://tw.voicetube.com/videos/66936)
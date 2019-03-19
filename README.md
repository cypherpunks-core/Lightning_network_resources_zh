
# :zap:閃電網路資源整理 | :zap:Lightning network resources
![](https://img.shields.io/badge/Powered%20by-Chen%20Po%20Wei-blue.svg)
![](bitcoin-lightning-network.png)

## 目錄 | Contents

<!-- TOC START min:1 max:3 link:true asterisk:false update:true -->
- [:zap:閃電網路資源整理 | :zap:Lightning network resources](#zap閃電網路資源整理--zaplightning-network-resources)
	- [目錄 | Contents](#目錄--contents)
	- [比特幣資源 | Bitcoin resources](#比特幣資源--bitcoin-resources)
		- [區塊鏈概述 | Blockchain overview](#區塊鏈概述--blockchain-overview)
		- [比特幣的基礎知識 | Basic knowledge of Bitcoin](#比特幣的基礎知識--basic-knowledge-of-bitcoin)
	- [:zap:閃電網路協議 | Lightning Network Protocol](#zap閃電網路協議--lightning-network-protocol)
		- [:zap:閃電網路概述 | Lightning Network Overview](#zap閃電網路概述--lightning-network-overview)
		- [:zap:進階閃電網路 ｜ Advanced lightning network](#zap進階閃電網路--advanced-lightning-network)
		- [:zap:實現 | Implementations](#zap實現--implementations)
		- [:zap:閃電網路 app](#zap閃電網路-app)
	- [:zap:特殊項目 | Special item](#zap特殊項目--special-item)
	- [:zap:文章 | article](#zap文章--article)
		- [動區動趨](#動區動趨)
		- [巴比特](#巴比特)
<!-- TOC END -->


## 比特幣資源 | Bitcoin resources
比特幣是一種基於去中心化，採用點對點網路與共識主動性，開放原始碼，以區塊鏈作為底層技術的加密貨幣，比特幣由中本聰於2008年10月31日發表論文。

### 區塊鏈概述 | Blockchain overview

* [區塊鏈技術漫談](區塊鏈技術漫談.md)

### 比特幣的基礎知識 | Basic knowledge of Bitcoin
* :clapper:**[比特幣和區塊鏈到底是啥？礦機挖礦咋回事？李永樂老師講比特幣(1)](https://www.youtube.com/watch?v=g_fSistU3MQ)**
* :clapper:**[比特幣交易如何防偽？私鑰公鑰地址啥意思？李永樂老師講比特幣(2)](
https://www.youtube.com/watch?v=pbAVauYsqP0)**
* :clapper:[你有疑惑過比特幣(與其他加密貨幣)的運作原理嗎？(純英文)](https://youtu.be/bBC-nXj3Ng4)
* :clapper:[你有疑惑過比特幣(與其他加密貨幣)的運作原理嗎？(簡中字幕)](https://www.bilibili.com/video/av12465079)
* Binance 學院：
	* [區塊鏈](https://www.binance.vision/zt/blockchain)
	* [經濟](https://www.binance.vision/zt/economics)
	* [安全](https://www.binance.vision/zt/security)
		* [什麼是挖礦劫持](/article/Binance-安全/什麼是挖礦劫持.md)
		* [什麼是粉塵攻擊](/article/Binance-安全/什麼是粉塵攻擊.md)
		* [什麼是51％的攻擊](/article/Binance-安全/什麼是51％的攻擊.md)
		* [什麼是重放攻擊](/article/Binance-安全/什麼是重放攻擊.md)
		* [什麼是DoS攻擊](/article/Binance-安全/什麼是DoS攻擊.md)
		* [女巫攻擊](/article/Binance-安全/女巫攻擊.md)
		* [什麽是公鑰密碼學](/article/Binance-安全/什麽是公鑰密碼學.md)
		* [加密學的歷史](/article/Binance-安全/加密學的歷史.md)
		* [什麼是多重簽名錢包](/article/Binance-安全/什麼是多重簽名錢包.md)
		* [普遍安全原則](/article/Binance-安全/普遍安全原則.md)
* :page_facing_up:**[比特幣：一種點對點的電子現金系統 繁中](https://github.com/ChenPoWei/bitcoin_whitepaper_zh)**
* :closed_book:**[Mastering Bitcoin 第二版 繁中](https://forum.cypherpunks.tech/t/topic/131)**
* 課程-[課程：區塊鏈技術與應用](https://docs.google.com/document/d/1R2lQ3NN6IFYT3fQ2G5D8TRcTw2bd4JTNMW8QbKimu8Q/edit?fbclid=IwAR3lpqDPNpelERgr_KHaHCBRI0R0QXQUn2tifwCEzfpXJpX8XWaHzPrqn5s#heading=h.3n87a6jtx1p1)
* 課程-[課程：以太坊原理與應用開發](https://docs.google.com/document/d/16V3HBwE78-vOex58P8s59TMxifhQi85_-whUd1ACd40/edit?fbclid=IwAR3mVk1wy40fglSFmNEi-CrELvmjv963Zdu0wQING4SSE4IA0dd9JzDpWdQ#heading=h.3n87a6jtx1p1)

## :zap:閃電網路協議 | Lightning Network Protocol
閃電網絡（英語：Lightning Network）是工作在區塊鏈上（主要面向比特幣）的第二層支付協議。其設計目的是實現交易雙方的即時交易，而區塊鏈的交易頻率則受限於其容量。
**主要思路 -閃電網絡的主要思路為將大量交易放到比特幣區塊鏈之外進行。閃電網絡通過智能合約來完善鏈下的交易渠道。在整個交易中，智能合約起到了中介的重要角色，而區塊鏈則確保最終的交易結果被確認。**

> 閃電網路是一個提議端到端連接的雙向支付通道路由網路。像這樣的網路可以允許任何參與者在無需信任任何中間人的情況下將支付從通道發送到通道。[閃電網路](https://lightning.network/lightning-network-paper.pdf)由Joseph Poon和Thadeus Dryja於2015年2月首先描述，建立在許多其他人提出和闡述的支付通道的概念上。

> “閃電網路”是指用於路由支付通道網路的特定設計，現在已經由至少五個不同的開源團隊實現。獨立實現由一組互操作性標準進行協調：http://bit.ly/2rBHeoL [Basics of Lightning Technology (BOLT) paper]。
> 閃電網路的原型實現已由多個團隊發佈。目前，這些實現只能在testnet上運行，因為它們使用segwit，而沒有在主比特幣區塊鏈(mainnet)上激活。



主要來源：
* ***[Radar ION](https://ion.radar.tech/)-加入閃電網絡的指南***
* ***[lightning.engineering](https://lightning.engineering/index.html)***

* [BITCOIN LIGHTNING NETWORK](https://lnroute.com/)-資源和信息指南
* [awesome-lightning-network](https://github.com/bcongdon/awesome-lightning-network)-為開發人員和加密愛好者提供的精彩Lightning Network項目列表
* [lightning.network](https://lightning.network/)
* [Blockstream LN](https://www.blockstream.com/lightning/)
* [eclair — ACINQ](https://acinq.co/)


### :zap:閃電網路概述 | Lightning Network Overview
* **[Binance-什麼事閃電網路？](/article/Binance-區塊鏈/什麼是閃電網絡.md)**
* [動區-什麼是Segwit隔離見證？](https://www.blocktempo.com/understand-segwit-in3mins) 2018-03-05
* **[動區-五分鐘就看懂：圖說閃電網路](https://www.blocktempo.com/lightning-network/) 2018-04-05**
* [動區-為何比特幣閃電網路的可視化器（Visualizer）跟看到的不太一樣?](https://www.blocktempo.com/bitcoin-lightning-visualizer-dont-seem-to-be-what-they-seem) 2018-04-15
* [動區-閃電網路是比特幣的未來？——解決方案全攻略](https://www.blocktempo.com/the-future-of-bitcoin-what-lightning-could-look-like)
* [Wikipedia Lightning Network](/article/wikipedia-Lightning-Network.md)
* [Lightning network/Payment channel](https://drive.google.com/file/d/0B7rTe1bpN56HeDJfZFBjcWk4Tm8/view) by Brian Po-han Chen
* [ Raiden Network — Ethereum 區塊鏈支付通道](https://medium.com/taipei-ethereum-meetup/raiden-network-ethereum-%E5%8D%80%E5%A1%8A%E9%8F%88%E6%94%AF%E4%BB%98%E9%80%9A%E9%81%93-c44cea954e9b)
* [閃電網路和雷電網路：擴容方案本身的擴容問題](https://medium.com/cryptocow/lightning-vs-raiden-1-can-watchtowers-and-monitoring-services-scale-f3b59906114b?fbclid=IwAR35vjbewlP6Y5y8tmynZt1KszE5L2pegT7GJbtpFnkHeZF7K35UGBbOMRg)
* [閃電網路/支付通道於Ethereum的基礎介紹 | 陳昶吾 | Taipei Ethereum Meetup #4 - Scalability 議題
](https://www.youtube.com/watch?v=pW615Yme2Ik)
* [簡單解釋比特幣的閃電網路 (Bitcoin's Lightning Network, Simply Explained!)](https://tw.voicetube.com/videos/66936)


### :zap:進階閃電網路 ｜ Advanced lightning network


#### 主要論文 | Main paper
* :page_facing_up:**[“比特幣閃電網絡”：論文-簡中](https://github.com/ChenPoWei/bitcoincn/blob/master/%E6%AF%94%E7%89%B9%E5%B8%81%E9%97%AA%E7%94%B5%E7%BD%91%E7%BB%9C%E7%99%BD%E7%9A%AE%E4%B9%A6%EF%BC%9A%E5%8F%AF%E6%89%A9%E5%B1%95%E7%9A%84%20off-chain%20%E5%8D%B3%E6%97%B6%E6%94%AF%E4%BB%98%EF%BC%88%E4%B8%AD%E6%96%87%EF%BC%89.pdf)**
* :page_facing_up:[“比特幣閃電網絡”：論文-英文](https://lightning.network/lightning-network-paper.pdf)

**摘要**。比特幣協議可以涵蓋當今所有電子支付系統中的全球金融交易量，而沒有單個監管第三方持有資金或要求參與者在家庭寬帶連接上具有任何不僅僅是計算機。提出了一種分散的系統，通過微支付渠道(例如支付渠道或交易渠道)的網絡發送交易，其價值轉移發生在區塊鏈之外。如果比特幣交易可以使用新的sighash類型進行簽名，這種類型可以解決延展性問題，那麼這些轉移可能發生在轉移路線上的不信任方之間，這些合同可以通過比特幣區塊鏈在不合作或敵對參與者的情況下通過廣播強制執行，通過一系列遞減時間。

#### 摘要 | abstract

* :page_facing_up:[閃電網絡摘要](https://lightning.network/lightning-network-summary.pdf)
* :page_facing_up:[閃電網絡技術設計概述](https://lightning.network/lightning-network-technical-summary.pdf)

#### 演示幻燈片

* [SF比特幣開發](https://lightning.network/lightning-network.pdf)
* [SF比特幣社交](https://lightning.network/lightning-network-presentation-sfbitcoinsocial-2015-05-26.pdf)
* [時間、比特幣、閃電網絡](https://lightning.network/lightning-network-presentation-time-2015-07-06.pdf)
* [LN作為有向圖單資源信道拓撲
](https://docs.google.com/presentation/d/1G4xchDGcO37DJ2lPC_XYyZIUkJc2khnLrCaZXgvDN0U/edit?pref=2&pli=1#slide=id.g85f425098_0_2)

#### 其他論文與規範 | Other papers and specifications

* :page_facing_up:[閃電網路規範](https://github.com/lightningnetwork/lightning-rfc)
* :page_facing_up:[LND API參考](http://api.lightning.community/)
* :page_facing_up:[可部署的閃電白皮書](https://github.com/ElementsProject/lightning/blob/master/doc/deployable-lightning.pdf)
* :page_facing_up:[比特幣微支付信道網絡的可擴展資金](https://www.tik.ee.ethz.ch/file/a20a865ce40d40c8f942cf206a7cba96/Scalable_Funding_Of_Blockchain_Micropayment_Networks%20(1).pdf)
* [lightningnetwork/lightning-rfc](https://github.com/lightningnetwork/lightning-rfc)-Lightning Network進行中規範


### :zap:實現 | Implementations

閃電網路協議的實現

* **[lightningnetwork/lnd](https://github.com/lightningnetwork/lnd) -  Lightning Network Daemon（lnd） - 是Lightning Network節點的完整實現。(Golang)**
* **[ElementsProject/lightning](https://github.com/ElementsProject/lightning) -  c-lightning：C語言中符合規範的Lightning Network實現(C)**
* **[ACINQ/eclair](https://github.com/ACINQ/eclair) - Lightning Network的Scala語言實現。它可以在有或沒有GUI的情況下運行，也可以使用JSON-RPC API。(Scala)**
* [mit-dci/lit](https://github.com/mit-dci/lit) -  Lightning Network節點軟件(Golang)
* [lightningnetwork/lightning-onion](https://github.com/lightningnetwork/lightning-onion) - 該存儲庫包含Lightning Network的洋蔥路由協議的實現。(Golang)
* [nayutaco/ptarmigan](https://github.com/nayutaco/ptarmigan) - 符合C ++ BOLT標準的Lightning網路實現[Incomplete]
* [LightningPeach/lpd](https://github.com/LightningPeach/lpd) - 是Rust語言中Lightning Network節點的部分實現。

### :zap:閃電網路 app
* [These are the Top 10 Lightning Apps out right now](https://kintu.co/lightning-apps/)
* [Lightning App Directory](https://dev.lightning.community/lapps/)


#### :moneybag:錢包 | Wallet
##### :computer:桌面界面 | Desktop Interfaces

* **[lightninglabs/lightning-app](https://github.com/lightninglabs/lightning-app) - 易於使用的跨平台閃電錢包**
* **[LN-Zap/zap-desktop](https://github.com/LN-Zap/zap-desktop) -  Zap是一款免費的Lightning Network錢包，專注於用戶體驗和易用性，其總體目標是幫助加密貨幣社區擴展比特幣和其他加密貨幣。**
* **[icota/presto](https://github.com/icota/presto) - Presto - 基於c-lightning的桌面和移動閃電網絡錢包**
* **[LightningPeach/lightning-peach-wallet](https://github.com/LightningPeach/lightning-peach-wallet) -  Bitfury Lightning錢包**
* **[shesek/spark-wallet](https://github.com/shesek/spark-wallet) - 用於c-lightning的最小GUI; 可用作網路，移動和桌面應用程序**
* [alexbosworth/lnd-gui](https://github.com/alexbosworth/lnd-gui) -  Lightning MacOS GUI錢包
* [ACINQ/eclair](https://github.com/ACINQ/eclair) -  Lightning的跨平台桌面GUI
* [benharold/voltage](https://github.com/benharold/voltage) - 是c-lightning的macOS GUI

##### :iphone:移動應用程序 | Mobile applications

* **Android**
	* [Eclair Mobile](https://play.google.com/store/apps/details?id=fr.acinq.eclair.wallet.mainnet2)
	* [Hoo Wallet](https://hoo.com/)-適用於Android的移動閃電錢包。此錢包是非託管的，需要運行您自己的完整節點。
	* [Eclair](https://github.com/ACINQ/eclair-mobile)Eclair移動應用程序是一款非託管移動Lightning Network錢包，現在可以啟用閃電接收功能。以前只能發送資金。
* **iOS**
	* [rawtxapp/rawtxapp](https://github.com/rawtxapp/rawtxapp) - 閃電網路錢包(Android，iOS); [主頁](https://rawtx.com)
	* [biscottigelato/SwiftLightning](https://github.com/biscottigelato/SwiftLightning) - 在LND for iOS之上構建LN錢包
	* [比特幣閃電錢包](https://play.google.com/store/apps/details?id=com.lightning.walletapp) - 基於Eclair的基於Android的Lightning Network兼容錢包([testnet版本](https：//play.google.com/store/apps/details?id=com.lightning.wallet))
* **Android & iOS**
	* [ZeusLN/zeus](https://github.com/ZeusLN/zeus)-Zeus基於TypeScript和React-Native構建。它可以在iOS和Android上運行。
	* [BlueWallet](https://github.com/BlueWallet/BlueWallet)-使用React Native和BlockCypher API構建。
	> [在Mac OSX上運行LNDHub](https://medium.com/@jpthor/running-lndhub-on-mac-osx-5be6671b2e0c)-如何在Mac OSX上部署和運行LNDHub實例並連接到BlueWallet。

##### Web界面 | Web Interfaces

* [Lightning-Family/Discovery-Wallet](https://github.com/Lightning-Family/Discovery-Wallet) - 網路保管錢包; [現場演示](https://wallet.lightning.family)
* [marzig76/fulmo](https://github.com/marzig76/fulmo) - 簡約的c-lightning UI
* [Joule](http://lightningjoule.com) - 一個擴展程序，支持與閃電應用程序的付款和其他交互(類似於MetaMask)
* [cdecker/kugelblitz](https://github.com/cdecker/kugelblitz) - 一個簡單的用戶界面，用於c-lightning守護進程閃電和bitcoind
* [mably/lncli-web](https://github.com/mably/lncli-web) - 用NodeJS / Angular編寫的lnd守護進程的輕量級Web客戶端
* [ShahanaFarooqui/RTL](https://github.com/ShahanaFarooqui/RTL) - 用NodeJS / Angular 7編寫的LND的Web客戶端
* [bitlum.io](https://bitlum.io/)-Bitlum是一個Lightning Network主網絡錢包。快速，簡單，無需安裝節點。設置只需5分鐘訪問。
* [tippin.me](https://tippin.me/)-Lightning Wallet和Tipping服務tippin.me發布了Chrome和Firefox的擴展程序，將其服務與Twitter集成。

#### :wrench:工具
* [Lightning Decoder](https://lightningdecoder.com/)-另一種解碼Lightning Network Invoice（BOLT11）的在線工具。

#### :ghost:遊戲
* [BC.Game](https://bc.game/atm)-BC.Game是一個BlockChain遊戲平台，具有可靠的公平，快速支付，免費水龍頭和Lightning Network支持。一些可用的遊戲是Crash，Dice和Blackjack。


#### :tv:瀏覽器 |  Explorers
* **閃電網路節點瀏覽器**
	* [Casa](https://explore.casa/)-一個快速瀏覽器，允許您查詢節點和通道。節點詳細信息包括星圖和頻道列表。
	* [acinq.co](https://explorer.acinq.co/)
	* [1ML](https://1ml.com/)
	* [Lightblock](https://lightblock.me)

* **閃電網路拓普**
	* [Lightning network explorer](https://explorer.acinq.co/)  - 可視化閃電網路拓普
	* [chemicstry/recksplorer](https://gist.github.com/bretton/798ec38165ffabc719d91e0f4f67552d) - 網絡視圖​​往往是來自單個節點或少量節點選擇的網絡視圖。它們不是網絡的完整視圖。這是不可能實現的。即使組合了許多節點視圖，它仍然是不完整的。
	* [xsb/lngraph](https://github.com/xsb/lngraph) - lngraph將Lightning Network數據導入Neo4j，用於本地探索您的節點及其網絡視圖。這不是一個公共資源管理器。
* [Robtex比特幣Lightning Explorer](https://www.robtex.com/lightning/node/) -  統計閃電節點數、殭屍節點數、活動節點數、活動節點數24h、活動節點數1w、活動節點數1m、總開放通道數、總封閉頻道、總頻道容量。
* [itcoinExchangeRate.org (Bitcoin 匯率)](https://bitcoinexchangerate.org/lightning) -  Lightning網路瀏覽器(testnet和mainnet)

## :zap:特殊項目 | Special item
* [Stadicus/guides](https://github.com/Stadicus/guides/blob/master/raspibolt/README.md)-在Raspberry Pi 上搭建 Lightning Network
* [rstmsn/lnd-for-wp](https://github.com/rstmsn/lnd-for-wp)-LND For WP是一個WordPress插件，允許您直接從WordPress管理面板管理和使用LND節點。它提供了一個功能齊全的錢包界面，使您可以輕鬆地在Lightning Network上發送和接收資金。
* [opencart 中支持 Lightning Network](https://www.opencart.com/index.php?route=marketplace/extension/info&extension_id=36414)


## :zap:文章 | article

* [Bitcoin Lightning Network常見問題解答](/article/Bitcoin-Lightning-Network-FAQ.md)

### 動區動趨
* [比特幣核心開發團隊釋出版本升級：全面支持SegWit](https://www.blocktempo.com/bitcoin-core-support-segwit/) 2018-02-27
* [【隔離見證｜擴容】比特幣錢包Xapo採用擴容方案「SegWit」](https://www.blocktempo.com/bitcoin-wallet-xapo-implements-scaling-solution-segwit) 2018-05-29
* [【區塊鏈遊戲 Poketoshi｜閃電網絡】讓你在比特幣閃電網絡上玩「神奇寶貝」？](https://www.blocktempo.com/poketoshi-game-brings-nintendo-s-pokemon-onto-bitcoin-lightning-network/) 2018-06-20
* [閃電網絡高速採用中，2019 年我們能期待的更多](https://www.blocktempo.com/lighning-network-in-2019/) 2019-01-29
* [【閃電網路被攻擊！】神秘組織「自掏腰包」發起攻擊來提醒開發團隊漏洞存在](https://www.blocktempo.com/lightning-network-hacked-for-its-own-good/) 2018-04-06
* [【獨立觀點】為何比特幣閃電網路的可視化器（Visualizer）跟看到的不太一樣?](https://www.blocktempo.com/bitcoin-lightning-visualizer-dont-seem-to-be-what-they-seem) 2018-04-15
* [【Zcash的隱私版閃電網路｜BOLT】正式上線！——匿名、輕量、小額支付
](https://www.blocktempo.com/the-code-for-an-anonymous-lightning-network-is-now-live/) 2018-08-15
* [閃電網路獲得大量採用中，有望透過Google Chrome、Firefox、Excel等進行比特幣支付](https://www.blocktempo.com/ln-adopting-chrome-firefox/)2018-10-31
* [比特幣軟體開發公司Blockstream的衛星「太空比特幣計畫」：宣布採用閃電網路](https://www.blocktempo.com/blockstream-satellite-loghtnign-network/) 2018-12-19

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

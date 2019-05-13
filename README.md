
# :zap:閃電網路資源整理 | :zap:Lightning network resources
![](https://img.shields.io/badge/Powered%20by-Chen%20Po%20Wei-blue.svg)
![](bitcoin-lightning-network.png)

## 目錄 | Contents

<!-- TOC START min:1 max:3 link:true asterisk:false update:true -->
- [:zap:閃電網路資源整理 | :zap:Lightning network resources](#zap%E9%96%83%E9%9B%BB%E7%B6%B2%E8%B7%AF%E8%B3%87%E6%BA%90%E6%95%B4%E7%90%86--zaplightning-network-resources)
	- [目錄 | Contents](#%E7%9B%AE%E9%8C%84--contents)
	- [:zap:閃電網路協議 | Lightning Network Protocol](#zap%E9%96%83%E9%9B%BB%E7%B6%B2%E8%B7%AF%E5%8D%94%E8%AD%B0--lightning-network-protocol)
		- [:zap:閃電網路概述 | Lightning Network Overview](#zap%E9%96%83%E9%9B%BB%E7%B6%B2%E8%B7%AF%E6%A6%82%E8%BF%B0--lightning-network-overview)
		- [:zap:進階閃電網路 ｜ Advanced lightning network](#zap%E9%80%B2%E9%9A%8E%E9%96%83%E9%9B%BB%E7%B6%B2%E8%B7%AF--advanced-lightning-network)
			- [主要論文 | Main paper](#%E4%B8%BB%E8%A6%81%E8%AB%96%E6%96%87--main-paper)
			- [摘要 | abstract](#%E6%91%98%E8%A6%81--abstract)
			- [演示幻燈片](#%E6%BC%94%E7%A4%BA%E5%B9%BB%E7%87%88%E7%89%87)
			- [其他論文與規範 | Other papers and specifications](#%E5%85%B6%E4%BB%96%E8%AB%96%E6%96%87%E8%88%87%E8%A6%8F%E7%AF%84--other-papers-and-specifications)
		- [比特幣 全節點 & 輕量級節點](#%E6%AF%94%E7%89%B9%E5%B9%A3-%E5%85%A8%E7%AF%80%E9%BB%9E--%E8%BC%95%E9%87%8F%E7%B4%9A%E7%AF%80%E9%BB%9E)
		- [:zap:閃電網路節點實現 | Lightning network node implementation](#zap%E9%96%83%E9%9B%BB%E7%B6%B2%E8%B7%AF%E7%AF%80%E9%BB%9E%E5%AF%A6%E7%8F%BE--lightning-network-node-implementation)
		- [:zap:閃電網路 插件](#zap%E9%96%83%E9%9B%BB%E7%B6%B2%E8%B7%AF-%E6%8F%92%E4%BB%B6)
		- [:zap:閃電網路 app](#zap%E9%96%83%E9%9B%BB%E7%B6%B2%E8%B7%AF-app)
			- [:moneybag:錢包 | Wallet](#moneybag%E9%8C%A2%E5%8C%85--wallet)
				- [:computer:桌面 + :iphone:ios + :iphone:android](#computer%E6%A1%8C%E9%9D%A2--iphoneios--iphoneandroid)
				- [:computer:桌面界面 | Desktop Interfaces](#computer%E6%A1%8C%E9%9D%A2%E7%95%8C%E9%9D%A2--desktop-interfaces)
				- [:iphone:行動app | Mobile applications](#iphone%E8%A1%8C%E5%8B%95app--mobile-applications)
				- [Web界面 | Web Interfaces](#web%E7%95%8C%E9%9D%A2--web-interfaces)
			- [:wrench:工具](#wrench%E5%B7%A5%E5%85%B7)
			- [:ghost:遊戲](#ghost%E9%81%8A%E6%88%B2)
			- [:tv:瀏覽器 | Explorers](#tv%E7%80%8F%E8%A6%BD%E5%99%A8--explorers)
	- [:zap:特殊項目 | Special item](#zap%E7%89%B9%E6%AE%8A%E9%A0%85%E7%9B%AE--special-item)
	- [:zap:文章 | article](#zap%E6%96%87%E7%AB%A0--article)
		- [動區動趨](#%E5%8B%95%E5%8D%80%E5%8B%95%E8%B6%A8)
		- [巴比特](#%E5%B7%B4%E6%AF%94%E7%89%B9)
<!-- TOC END -->


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

### 比特幣 全節點 & 輕量級節點
在運行一個比特幣閃點網路節點必須依賴一個比特幣全節點或是輕量級節點。
* [Neutrino](https://github.com/lightninglabs/neutrino)：隱私保護比特幣輕客戶端。一個於2017年5月提出的比特幣改進提案＂[Compact Client Side Filtering for Light Clients](https://github.com/Roasbeef/bips/blob/master/gcs_light_client.mediawiki)＂，`neutrino` (BIP 157 & BIP 158) ，重要改進原有的SPV節點使用到的布林過濾器，隱私問題。ps. 目前已經被ZAP錢包採用。
* [btcd](https://github.com/btcsuite/btcd)： btcd是用Go（golang）編寫的替代全節點比特幣實現。


### :zap:閃電網路節點實現 | Lightning network node implementation

閃點網路的節點實現

* **[lightningnetwork/lnd](https://github.com/lightningnetwork/lnd) -  Lightning Network Daemon（lnd） - 是Lightning Network節點的完整實現。(Golang)**
* **[ElementsProject/lightning](https://github.com/ElementsProject/lightning) -  c-lightning：C語言中符合規範的Lightning Network實現(C)**
* **[ACINQ/eclair](https://github.com/ACINQ/eclair) - Lightning Network的Scala語言實現。它可以在有或沒有GUI的情況下運行，也可以使用JSON-RPC API。(Scala)**
* [mit-dci/lit](https://github.com/mit-dci/lit) -  Lightning Network節點軟件(Golang)
* [lightningnetwork/lightning-onion](https://github.com/lightningnetwork/lightning-onion) - 該存儲庫包含Lightning Network的洋蔥路由協議的實現。(Golang)
* [nayutaco/ptarmigan](https://github.com/nayutaco/ptarmigan) - 符合C ++ BOLT標準的Lightning網路實現[Incomplete]
* [LightningPeach/lpd](https://github.com/LightningPeach/lpd) - 是Rust語言中Lightning Network節點的部分實現。
* [rust-bitcoin/rust-lightning](https://github.com/rust-bitcoin/rust-lightning) - 用rust程式語言實現，完成度20%

### :zap:閃電網路 插件
* **[lightningd/plugins](https://github.com/lightningd/plugins) - 支持的插件挺多的，值得參考**

### :zap:閃電網路 app
* [These are the Top 10 Lightning Apps out right now](https://kintu.co/lightning-apps/)
* [Lightning App Directory](https://dev.lightning.community/lapps/)

#### :moneybag:錢包 | Wallet
> 標記：:heavy_exclamation_mark:，請自己斟酌使用，有一定的安全風險
##### :computer:桌面 + :iphone:ios + :iphone:android
* **[LN-Zap](https://github.com/LN-Zap/) -  Zap是一款免費的Lightning Network錢包，專注於用戶體驗和易用性，其總體目標是幫助加密貨幣社區擴展比特幣和其他加密貨幣。**
	* [zap-desktop](https://github.com/LN-Zap/zap-desktop)：跨平台Lightning Network錢包專注於用戶體驗和易用性⚡️，可以選用Neutrino輕量級節點，或是遠端控制閃電網路節點。
	* [zap-iOS](https://github.com/LN-Zap/zap-iOS)：目前僅支持遠端使用閃電網路節點。

##### :computer:桌面界面 | Desktop Interfaces

* **[lightninglabs/lightning-app](https://github.com/lightninglabs/lightning-app) - 易於使用的跨平台閃電錢包，基於Neutrino 輕量級節點**
* **[icota/presto](https://github.com/icota/presto) - Presto - 基於c-lightning的桌面和移動閃電網絡錢包**
* **[LightningPeach/lightning-peach-wallet](https://github.com/LightningPeach/lightning-peach-wallet) -  Bitfury Lightning錢包**
* **[shesek/spark-wallet](https://github.com/shesek/spark-wallet) - 用於c-lightning的最小GUI; 可用作網路，移動和桌面應用程序**
* [alexbosworth/lnd-gui](https://github.com/alexbosworth/lnd-gui) -  Lightning MacOS GUI錢包
* [ACINQ/eclair](https://github.com/ACINQ/eclair) -  Lightning的跨平台桌面GUI
* [benharold/voltage](https://github.com/benharold/voltage) - 是c-lightning的macOS GUI

##### :iphone:行動app | Mobile applications
* **Android & iOS**
	* [ZeusLN/zeus](https://github.com/ZeusLN/zeus)-Zeus基於TypeScript和React-Native構建。它可以在iOS和Android上運行。
	* [Bitpie](https://bitpie.com) - iOS 和 Android 上的多幣種錢包，目前已適用於閃電網路。
	* [Hoo虎符錢包](https://hoo.com) - 中國首家支持閃電網路Lightning Network的錢包。
	* :heavy_exclamation_mark:[BlueWallet](https://github.com/BlueWallet/BlueWallet)-使用React Native和BlockCypher API構建。
	> [在Mac OSX上運行LNDHub](https://medium.com/@jpthor/running-lndhub-on-mac-osx-5be6671b2e0c)-如何在Mac OSX上部署和運行LNDHub實例並連接到BlueWallet。

* **Android**
	* [Eclair Mobile](https://play.google.com/store/apps/details?id=fr.acinq.eclair.wallet.mainnet2)
	* [Hoo Wallet](https://hoo.com/)-適用於Android的移動閃電錢包。此錢包是非託管的，需要運行您自己的完整節點。
	* [Eclair](https://github.com/ACINQ/eclair-mobile)Eclair移動應用程序是一款非託管移動Lightning Network錢包，現在可以啟用閃電接收功能。以前只能發送資金。
* **iOS**
	* [rawtxapp/rawtxapp](https://github.com/rawtxapp/rawtxapp) - 閃電網路錢包(Android，iOS); [主頁](https://rawtx.com)
	* [biscottigelato/SwiftLightning](https://github.com/biscottigelato/SwiftLightning) - 在LND for iOS之上構建LN錢包
	* [比特幣閃電錢包](https://play.google.com/store/apps/details?id=com.lightning.walletapp) - 基於Eclair的基於Android的Lightning Network兼容錢包([testnet版本](https：//play.google.com/store/apps/details?id=com.lightning.wallet))
	* :heavy_exclamation_mark:[walletofsatoshi](https://walletofsatoshi.com/)

##### Web界面 | Web Interfaces

* [Lightning-Family/Discovery-Wallet](https://github.com/Lightning-Family/Discovery-Wallet) - 網路保管錢包; [現場演示](https://wallet.lightning.family)
* [marzig76/fulmo](https://github.com/marzig76/fulmo) - 簡約的c-lightning UI
* [Joule](http://lightningjoule.com) - 一個擴展程序，支持與閃電應用程序的付款和其他交互(類似於MetaMask)
* [cdecker/kugelblitz](https://github.com/cdecker/kugelblitz) - 一個簡單的用戶界面，用於c-lightning守護進程閃電和bitcoind
* [mably/lncli-web](https://github.com/mably/lncli-web) - 用NodeJS / Angular編寫的lnd守護進程的輕量級Web客戶端
* [ShahanaFarooqui/RTL](https://github.com/ShahanaFarooqui/RTL) - 用NodeJS / Angular 7編寫的LND的Web客戶端
* :heavy_exclamation_mark:[bitlum.io](https://bitlum.io/)-Bitlum是一個Lightning Network主網絡錢包。快速，簡單，無需安裝節點。設置只需5分鐘訪問。
* :heavy_exclamation_mark:[tippin.me](https://tippin.me/)-Lightning Wallet和Tipping服務tippin.me發布了Chrome和Firefox的擴展程序，將其服務與Twitter集成。

#### :wrench:工具
* [Lightning Decoder](https://lightningdecoder.com/)-另一種解碼Lightning Network Invoice（BOLT11）的在線工具。
* [Decoder for Lightning Payment Requests](https://lndecode.com/)-Lightning Network Invoice的線上解碼工具。

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
* [閃電網路Invoice中的欄位介紹(英文)](https://blockfuse.io/blog/lightning-network-invoices/)

### 動區動趨
* [比特幣核心開發團隊釋出版本升級：全面支持SegWit](https://www.blocktempo.com/bitcoin-core-support-segwit/) 2018-02-27
* [【閃電網路被攻擊！】神秘組織「自掏腰包」發起攻擊來提醒開發團隊漏洞存在](https://www.blocktempo.com/lightning-network-hacked-for-its-own-good/) 2018-04-06
* [【獨立觀點】為何比特幣閃電網路的可視化器（Visualizer）跟看到的不太一樣?](https://www.blocktempo.com/bitcoin-lightning-visualizer-dont-seem-to-be-what-they-seem) 2018-04-15
* [【隔離見證｜擴容】比特幣錢包Xapo採用擴容方案「SegWit」](https://www.blocktempo.com/bitcoin-wallet-xapo-implements-scaling-solution-segwit) 2018-05-29
* [【區塊鏈遊戲 Poketoshi｜閃電網絡】讓你在比特幣閃電網絡上玩「神奇寶貝」？](https://www.blocktempo.com/poketoshi-game-brings-nintendo-s-pokemon-onto-bitcoin-lightning-network/) 2018-06-20
* [【Zcash的隱私版閃電網路｜BOLT】正式上線！——匿名、輕量、小額支付
](https://www.blocktempo.com/the-code-for-an-anonymous-lightning-network-is-now-live/) 2018-08-15
* [閃電網路獲得大量採用中，有望透過Google Chrome、Firefox、Excel等進行比特幣支付](https://www.blocktempo.com/ln-adopting-chrome-firefox/)2018-10-31
* [比特幣軟體開發公司Blockstream的衛星「太空比特幣計畫」：宣布採用閃電網路](https://www.blocktempo.com/blockstream-satellite-loghtnign-network/) 2018-12-19
* [閃電網絡高速採用中，2019 年我們能期待的更多](https://www.blocktempo.com/lighning-network-in-2019/) 2019-01-29
* [推特（Twitter）上現在可以透過閃電網路進行「比特幣打賞」](https://www.blocktempo.com/you-can-now-send-bitcoin-tips-over-lightning-on-twitter-1) 2019-02-19
* [閃電聖火將燃燒殆盡？ —— 這場全球性實驗帶給比特幣社群的啟發](https://www.blocktempo.com/lighning-torch-burning-out) 2019-04-06
* [美夢成真！今天起將可以在 Amazon 以閃電網路支付比特幣](https://www.blocktempo.com/you-can-now-shop-with-bitcoin-on-amazon-using-lightning/) 2019-04-23
* [再下一城！閃電網路實驗室在「比特幣主網上」正式發布桌面版應用](https://www.blocktempo.com/lightning-labs-launches-desktop-app-on-bitcoin-mainnet) 2019-04-24

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
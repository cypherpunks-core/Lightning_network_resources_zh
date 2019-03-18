# Lightning Network

![](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7a/17_node_mesh_network.svg/300px-17_node_mesh_network.svg.png)

通過支付渠道的理想化[網絡網絡](https://en.wikipedia.org/wiki/Mesh_network)進行路由。

**閃電網絡**是一種“第2層”支付協議，在基於區塊鏈的[加密貨幣](https://en.wikipedia.org/wiki/Cryptocurrency)之上運行(如[比特幣](https：//en.wikipedia.org/wiki/Bitcoin))。它支持參與節點之間的快速交易，並被吹捧為[比特幣可擴展性問題](https://en.wikipedia.org/wiki/Bitcoin_scalability_problem)的解決方案。它具有[peer-to-peer](https://en.wikipedia.org/wiki/Peer-to-peer)製作[微支付]系統(https://en.wikipedia.org/wiki/Micropayment)通過雙向支付渠道網絡加密貨幣而不委託資金保管。 Lightning Network實現還簡化了原子交換。[* [需要澄清](https://en.wikipedia.org/wiki/Wikipedia:Please_clarify)*]

閃電網絡的正常使用包括通過向相關的基礎區塊鏈(第1層)提交資金交易來開立支付渠道，然後進行任意數量的Lightning交易，更新渠道資金的暫定分配而不向區塊鏈廣播，可選地，隨後通過廣播交易的最終版本來關閉支付渠道以分配渠道的資金。

為了按預期執行，Lightning Network需要在第1層區塊鏈中修復[交易延展性](https://en.wikipedia.org/wiki/Malleability_(加密))，例如[隔離證人](https：//en比特幣中的.wikipedia.org/wiki/Segregated_Witness)(* SegWit *)。[[1]](https://en.wikipedia.org/wiki/Lightning_Network#cite_note-spec-1)



## 歷史

Joseph Poon和Thaddeus Dryja在2016年發表了Lightning白皮書。[[2]](https://en.wikipedia.org/wiki/Lightning_Network#cite_note-2)

2017年12月，在[比特幣核心](https://en.wikipedia.org/wiki/Bitcoin_Core)實施中進行了一系列可互操作的測試交易。

2018年1月，[Blockstream](https://en.wikipedia.org/wiki/Blockstream)為網絡零售商推出了支付處理系統。 Blockstream指出，Lightning在主網上運行，截至2018年1月18日有60個節點運行，應該被認為是“正在測試中”。

2018年3月15日，Lightning Labs首席執行官伊麗莎白·斯塔克宣佈為開發人員首次發布lnd 0.4-beta，旨在通過Litecoin支持在比特幣主網絡上進行測試。

2018年3月，Stellar CTO [Jed McCaleb](https://en.wikipedia.org/wiki/Jed_McCaleb)宣布[Stellar Network](https://en.wikipedia.org/wiki/Stellar_(payment_network))將實施靈感來自閃電網絡的協議。[* [citation needed](https://en.wikipedia.org/wiki/Wikipedia:Citation_needed)*]

Lightning Network概念於2018年3月獲得[移動支付](https://en.wikipedia.org/wiki/Mobile_payment)企業家[Jack Dorsey](https://en.wikipedia.org/wiki/Jack_Dorsey)的認可。 [[3]](https://en.wikipedia.org/wiki/Lightning_Network#cite_note-3)

從2018年4月到2018年8月，比特幣閃電網絡的月增長率約為15％。節點數量從1,500增加到3,000，頻道數量從4,000增加到11,000。[[4]](https://en.wikipedia.org/wiki/Lightning_Network#cite_note-4)

在2018年4月，eclair錢包已從[Google Play](https://en.wikipedia.org/wiki/Google_Play)商店中刪除了幾天，因為應用開發者丟失了私人簽名密鑰，導致無法更新對於關鍵錯誤。

### 2018年DDoS攻擊

在2018年3月20日，Lightning Network節點面臨[分佈式拒絕服務(DDoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack)攻擊，該攻擊從大約200個節點離線發送利用盡可能多的節點連接以防止任何新連接。[[5]](https://en.wikipedia.org/wiki/Lightning_Network#cite_note-TrustNodes-5)2月初一個月，[比特幣核心](https://en.wikipedia.org/wiki/Bitcoin_Core)開發人員Peter Todd表示，Lightning協議很可能“在其目前的版本中被證明易受DoS [拒絕服務]攻擊。”根據密碼學家的說法，這會給項目的點對點和區塊鏈級別帶來危險。

## 設計

閃電網絡概述

支付渠道允許參與者相互轉賬，而無需在[區塊鏈](https://en.wikipedia.org/wiki/Blockchain)上公開所有交易。這是通過懲罰不合作的參與者來完成的。在打開頻道時，參與者必須提交金額(在*資金交易*中，* *是區塊鏈上的*)。基於時間的腳本擴展，如[CheckSequenceVerify](https://en.wikipedia.org/wiki/CheckSequenceVerify)和[CheckLockTimeVerify](https://en.wikipedia.org/wiki/CheckLockTimeVerify)，可以實現懲罰。

> “如果我們假設比特幣區塊鏈上的大型渠道網絡，並且所有比特幣用戶都通過在比特幣區塊鏈上打開至少一個渠道來參與此圖表，則可以在此內部創建近乎無限量的交易比特幣區塊鏈過早播出的唯一交易是不合作的頻道交易對手。“[[6]](https://en.wikipedia.org/wiki/Lightning_Network#cite_note-6)

CheckSequenceVerify(CSV)[比特幣改進提案](https://en.wikipedia.org/wiki/Bitcoin_Improvement_Proposal)詳細說明瞭如何使用CSV實現哈希時間鎖定合同並在Lightning中使用。[[7]](https：//en.wikipedia.org/wiki/Lightning_Network#cite_note-7)

### 承諾交易

如果[Alice和Bob](https://en.wikipedia.org/wiki/Alice_and_Bob)有付款渠道，則他們都有“最新”*承諾交易*。承諾交易根據Alice和Bob之間的正確分配從資金交易中劃分資金。例如，如果Alice擁有1.0 mBTC(等於0.001比特幣或100000 [satoshis](https://en.wikipedia.org/wiki/Bitcoin#Units))並且Bob擁有該渠道中的1.0 mBTC，則承諾交易將劃分為以這種方式的總渠道資金。

承諾交易允許多個用戶參與單個交易(因此充當單個實體)，使用多鑰匙系統*。*擁堵的確定主要落在礦工身上，因此這個網絡依賴於誠實的礦工將會沒有組織51％的攻擊。

由於承諾交易花費資金交易，因此必須由雙方簽署。

承諾交易實際上是一對不對稱的交易。 Alice的承諾交易包含兩個輸出：一個直接支付Bob，另一個是時間鎖定，可撤銷的輸出，最終支付Alice。如果Bob知道撤銷密鑰，則可撤銷可撤銷輸出。鮑勃的承諾交易恰恰相反：它直接向愛麗絲支付，但在時間鎖定，可撤銷的輸出下支付鮑勃的份額;如果Alice知道Bob的承諾交易的撤銷密鑰，她可以撤銷它。

最初，Alice持有{\displaystyleA_{1}}！[A_{1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6bc2435b217c1a0f46f8a517ffa225c6f9440e81)承諾交易，Bob持有{\displaystyleB_{1}}！[B_{1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1fa091eb428443c9c5c5fcf32a69d3665c89e00c)承諾交易。{\displaystyleA_{1}}的撤消鍵！[A_{1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6bc2435b217c1a0f46f8a517ffa225c6f9440e81)，{\displaystyleR_{A_{1}}}！[{\displaystyleR_{A_{1}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/16f17818e76941dfcb5646eb7156609a9de53160)，由Alice知道，但不是鮑勃;{\displaystyleB_{1}}的撤銷鍵！[B_{1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1fa091eb428443c9c5c5fcf32a69d3665c89e00c)，{\displaystyleR_{B_{1}}}！[{\displaystyleR_{B_{1}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a0f2e388adeb19e7a53c6a4facfc8a57ea47ba76)，同樣只有Bob知道。

假設Alice決定支付Bob0.25mBTC(在此之前，每個人擁有1mBTC)：

1. Alice創建了一個新的Bob交易，{\displaystyleB_{2}}！[B_{2}](https://wikimedia.org/api/rest_v1/media/math/render/svg/199944d59dcc18842dfd1deab6000a1d1dadcbae)，分配Alice為0.75mBTC，Bob為1.25mBTC。
2. Alice簽署{\displaystyleB_{2}}！[B_{2}](https://wikimedia.org/api/rest_v1/media/math/render/svg/199944d59dcc18842dfd1deab6000a1d1dadcbae)並發送給Bob。
3. Bob收到{\displaystyleB_{2}}！[B_{2}](https://wikimedia.org/api/rest_v1/media/math/render/svg/199944d59dcc18842dfd1deab6000a1d1dadcbae)，簽名並保留。
4. Bob創建一個新的Alice交易，{\displaystyleA_{2}}！[A_{2}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3ec73b8bc9abc3efb934f5a6ec2803713771f4bc)，分配Alice為0.75mBTC，Bob為1.25mBTC。
5. Bob簽署{\displaystyleA_{2}}！[A_{2}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3ec73b8bc9abc3efb934f5a6ec2803713771f4bc)並發送給Alice。
6. Alice收到{\displaystyleA_{2}}！[A_{2}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3ec73b8bc9abc3efb934f5a6ec2803713771f4bc)，簽名並保留。
7. Alice提供{\displaystyleR_{A_{1}}}！[{\displaystyleR_{A_{1}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/16f17818e76941dfcb5646eb7156609a9de53160)，使{\displaystyleA_{1}}無效！[A_{1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6bc2435b217c1a0f46f8a517ffa225c6f9440e81);然後她可以刪除{\displaystyleA_{1}}！[A_{1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6bc2435b217c1a0f46f8a517ffa225c6f9440e81)。
8. Bob提供{\displaystyleR_{B_{1}}}！[{\displaystyleR_{B_{1}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a0f2e388adeb19e7a53c6a4facfc8a57ea47ba76)，使{\displaystyleB_{1}}無效！[B_{1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1fa091eb428443c9c5c5fcf32a69d3665c89e00c);然後他可以刪除{\displaystyleB_{1}}！[B_{1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1fa091eb428443c9c5c5fcf32a69d3665c89e00c)。

### 限制

Lightning Network由兩個節點之間的雙向支付渠道組成，這些渠道結合了[智能合約](https://en.wikipedia.org/wiki/Smart_contract)。如果任何一方在任何一方丟棄頻道，頻道將關閉並在區塊鏈上結算。

由於Lightning Network的爭議機制的性質要求所有用戶不斷觀看區塊鏈的欺詐行為，因此開發了“瞭望塔”的概念，可以將信任外包給瞭望塔節點以監控欺詐。

### 路由
關於路由的原始白皮書表明“最終，通過優化，網絡將看起來很像通信銀行網絡，或第1層ISP”。

## 實現
BOLT(閃電技術基礎)[規格](https://github.com/lightningnetwork/lightning-rfc/blob/master/00-introduction.md)於2016年底起草。從那裡開始，已經實施了多項實施說規格：

* [MIT]的非商業實施(https://en.wikipedia.org/wiki/MIT_Media_Lab) [數字貨幣計劃](https://dci.mit.edu/)
* [Blockstream](https://en.wikipedia.org/wiki/Blockstream)的[C]中的c-lightning [實現](https://github.com/ElementsProject/lightning)
* [Scala]中的ACINQ的eclair [實現](https://github.com/ACINQ/eclair) 
* 閃電實驗室的[實施](https://github.com/lightningnetwork/lnd)

## 參考文獻

1. ** [^](https://en.wikipedia.org/wiki/Lightning_Network#cite_ref-spec_1-0) ** [“lightning-rfc：Lightning Network Specifications”](https://github.com/lightningnetwork/閃電-RFC)。 2017年9月25日 - 通過GitHub。
2. ** [^](https://en.wikipedia.org/wiki/Lightning_Network#cite_ref-2) ** [“Joseph Poon和Thaddeus Dryja的閃電網白皮書”](https://lightning.network/閃電般的網絡paper.pdf)(PDF)。 2019年1月6日。
3. ** [^](https://en.wikipedia.org/wiki/Lightning_Network#cite_ref-3) ** [“比特幣價格：什麼是比特幣閃電網 - 它怎麼能以BTC價格導致CHAOS”]( https://www.express.co.uk/life-style/science-technology/985113/Bitcoin-price-news-lightning-network-BTC-value)。表達。 2018年7月6日。
4. ** [^](https://en.wikipedia.org/wiki/Lightning_Network#cite_ref-4) ** [“統計”](https://web.archive.org/web/*/https：//1ml.com/statistics)。 * 1ml.com *。
5. ** [^](https://en.wikipedia.org/wiki/Lightning_Network#cite_ref-TrustNodes_5-0)** [“閃電網絡DDoS向下發送20％的節點”](https：//www.trustnodes.com/2018/03/21/lightning-network-ddos-sends-20-nodes)。 *新聞文章* 。 TrustNodes。 2018年3月21日。
6. ** [^](https://en.wikipedia.org/wiki/Lightning_Network#cite_ref-6) ** [“比特幣閃電網絡：可擴展的離線即時付款”](https：//閃電。網絡/閃電網絡paper.pdf)(PDF)。 * lightning.network *。 2016年1月14日。
7. ** [^](https://en.wikipedia.org/wiki/Lightning_Network#cite_ref-7) ** [“bips：Bitcoin Improvement Proposals”](https://github.com/bitcoin/bips) 。 2017年9月25日 - 通過GitHub。

# 外部鏈接


* [lightning.network](https://lightning.network/)
* [lightningwiki.net](https://lightningwiki.net/)
* [dci.mit.edu/lightning-network/](https://dci.mit.edu/lightning-network/)
* [dev.lightning.community](http://dev.lightning.community/)
* [Linux基金會]上的[lists.linuxfoundation.org/pipermail/lightning-dev/](https://lists.linuxfoundation.org/pipermail/lightning-dev/)(https://en.wikipedia.org/維基/Linux_Foundation)服務器
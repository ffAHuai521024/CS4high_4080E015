Markdown文件
https://markdown.tw/
Network Types: LAN, WAN, PAN, CAN, MAN, SAN, WLAN
https://www.youtube.com/watch?v=4_zSIXb7tLQ

Network Topologies (Star, Bus, Ring, Mesh, Ad hoc, Infrastructure, & Wireless Mesh Topology)
https://www.youtube.com/watch?v=zbqrNg4C98U

What is a DMZ? (Demilitarized Zone)
https://www.youtube.com/watch?v=dqlzQXo1wqo

NAT Explained - Network Address Translation
https://www.youtube.com/watch?v=FTUV0t6JaDA


#網路硬體
Layer-1:repeater(1-1), hub(1-N)
Layer-2:bridgr, switch
Layer-3: router,L3-Switch
Layer-4: L4 switch
Layer-7: L7 switch, proxy

#IEEE 802

'''
https://zh.wikipedia.org/wiki/IEEE_802
'''

IEEE 802中定義的服務和協定限定在OSI模型的最低兩層（即實體層和資料鏈路層）

IEEE 802將OSI的資料鏈路層分為兩個子層

Data Link Layer2 (資料連接層)  邏輯鏈路控制（LLC, Logical Link Control）
                              媒介存取控制（MAC, Media Access Control）
                 
Physical Layer1 (實體層) 實體運用

#現有標準
IEEE 802.1：高層區域網路協定（Bridging (networking) and Network Management）
IEEE 802.2：邏輯鏈路控制（Logical link control）
IEEE 802.3：乙太網路（Ethernet）
IEEE 802.4：權杖匯流排（Token bus）
IEEE 802.5：權杖環（Token-Ring）
IEEE 802.6：城域網（MAN, Metropolitan Area Network）
IEEE 802.7：寬頻TAG（Broadband LAN using Coaxial Cable）
IEEE 802.8：光纖分散式資料介面（FDDI）
IEEE 802.9：綜合業務區域網路（Integrated Services LAN）
IEEE 802.10：區域網路網路安全（Interoperable LAN Security）
IEEE 802.11：無線區域網路（Wireless LAN & Mesh）
IEEE 802.12：需求優先級（Demand priority）
IEEE 802.13：（未使用）
IEEE 802.14：電纜數據機（Cable modems）
IEEE 802.15：無線個人區域網路（Wireless PAN）
IEEE 802.15.1：無線個人區域網路絡（WPAN, Wireless Personal Area Network）
IEEE 802.15.4：低速無線個人區域網路絡（LR-WPAN, Low Rate Wireless Personal Area Network）
IEEE 802.16：寬頻無線接入（Broadband Wireless Access）
IEEE 802.17：彈性封包環傳輸技術（Resilient packet ring）
IEEE 802.18：無線電管制技術（Radio Regulatory TAG）
IEEE 802.19：共存標籤（Coexistence TAG）
IEEE 802.20：移動寬頻無線接入（Mobile Broadband Wireless Access）
IEEE 802.21：媒介獨立換手（Media Independent Handover）
IEEE 802.22：無線區域網（Wireless Regional Area Network）
IEEE 802.23：緊急服務工作群組（Emergency Services Working Group）

ICMP(網際網路控制訊息協定)定義
網際網路控制訊息協定（英語：Internet Control Message Protocol，縮寫：ICMP）是網際網路協定套組的核心協定之一。
它用於網際網路協定（IP）中傳送控制訊息，提供可能發生在通訊環境中的各種問題回饋。

ICMP [1]依靠IP來完成它的任務，它是IP的主要部分。它與傳輸協定（如TCP和UDP）顯著不同：它一般不用於在兩點間傳輸資料。
IPv4中的ICMP被稱作ICMPv4，IPv6中的ICMP則被稱作ICMPv6。

ICMP Message Format封包格式:

![image](http://telescript.denayer.wenk.be/~hcr/cn/idoceo/images/icmp_header.gif)


































#tracert www.google.com
在上限 30 個躍點上
追蹤 www.google.com [172.217.24.4] 的路由:

  1    <1 ms    <1 ms    <1 ms  172.20.155.254
  2     3 ms     3 ms     4 ms  172.16.190.253
  3     3 ms     2 ms     2 ms  120-114-151-14.ksu.edu.tw [120.114.151.14]
  4     *        *        *     要求等候逾時。
  5     *        *        *     要求等候逾時。
  6     *        *        *     要求等候逾時。
  7     *        *        *     要求等候逾時。
  8     *        *        *     要求等候逾時。
  9     *        *        *     要求等候逾時。
 10     *        *        *     要求等候逾時。
 11     *        *        *     要求等候逾時。
 12     *        *        *     要求等候逾時。
 13     *        *        *     要求等候逾時。
 14     *        *        *     要求等候逾時。
 15     *        *        *     要求等候逾時。
 16     *        *        *     要求等候逾時。
 17     *        *        *     要求等候逾時。
 18     *        *        *     要求等候逾時。
 19     *        *        *     要求等候逾時。
 20     *        *        *     要求等候逾時。
 21     *        *        *     要求等候逾時。
 22     *        *        *     要求等候逾時。
 23     *        *        *     要求等候逾時。
 24     *        *        *     要求等候逾時。
 25     *        *        *     要求等候逾時。
 26     *        *        *     要求等候逾時。
 27     *        *        *     要求等候逾時。
 28     *        *        *     要求等候逾時。
 29     *        *        *     要求等候逾時。
 30     *        *        *     要求等候逾時。

追蹤完成。

#tracert www.ksu.edu.tw

C:\Users\KSUIE>tracert www.ksu.edu.tw

在上限 30 個躍點上
追蹤 www.ksu.edu.tw [120.114.100.65] 的路由:

  1    <1 ms     7 ms    <1 ms  172.20.155.254
  2    19 ms     3 ms    <1 ms  120-114-50-230.ksu.edu.tw [120.114.50.230]
  3    <1 ms    <1 ms    <1 ms  eng.www.ksu.edu.tw [120.114.100.65]

追蹤完成。

###ARP

顯示和修改位址解析通訊協定 (ARP) 使用的 IP 對
實際位址轉譯表格。

ARP -s inet_addr eth_addr [if_addr]
ARP -d inet_addr [if_addr]
ARP -a [inet_addr] [-N if_addr] [-v]

  -a            質詢目前的通訊協定資料來顯示目前的
                ARP 項目。如果指定 inet_addr，只會顯示指定電腦的
                IP 及實體位址。如果有多個網路介面使用 ARP，便會顯示每個 ARP
                表格的項目。
                
#C:\Users\KSUIE>ARP -a

介面: 192.168.56.1 --- 0x5
  網際網路網址          實體位址               類型
  192.168.56.255        ff-ff-ff-ff-ff-ff     靜態
  224.0.0.3             01-00-5e-00-00-03     靜態
  224.0.0.22            01-00-5e-00-00-16     靜態
  224.0.0.251           01-00-5e-00-00-fb     靜態
  224.0.0.252           01-00-5e-00-00-fc     靜態
  239.255.255.250       01-00-5e-7f-ff-fa     靜態

介面: 172.20.155.231 --- 0xc
  網際網路網址          實體位址               類型
  172.20.155.14         88-d7-f6-53-84-b7     動態
  172.20.155.16         88-d7-f6-53-83-c0     動態
  172.20.155.17         88-d7-f6-53-84-b5     動態
  172.20.155.22         88-d7-f6-53-24-ac     動態
  172.20.155.38         88-d7-f6-53-24-9b     動態
  172.20.155.50         88-d7-f6-53-82-e5     動態
  172.20.155.51         88-d7-f6-53-85-b8     動態
  172.20.155.56         38-2c-4a-c6-c6-29     動態
  172.20.155.61         88-d7-f6-53-84-19     動態
  172.20.155.71         88-d7-f6-53-84-7d     動態
  172.20.155.83         38-2c-4a-c6-c4-e6     動態
  172.20.155.88         88-d7-f6-53-85-75     動態
  172.20.155.90         88-d7-f6-53-24-a8     動態
  172.20.155.97         88-d7-f6-53-83-4a     動態
  172.20.155.100        88-d7-f6-53-83-98     動態
  172.20.155.101        38-2c-4a-c6-c2-a5     動態
  172.20.155.102        70-4d-7b-a3-4c-d4     動態
  172.20.155.126        88-d7-f6-53-83-f7     動態
  172.20.155.143        88-d7-f6-53-24-bc     動態
  172.20.155.145        88-d7-f6-53-24-2b     動態
  172.20.155.153        88-d7-f6-53-24-87     動態
  172.20.155.157        70-4d-7b-a3-4d-68     動態
  172.20.155.162        88-d7-f6-53-24-eb     動態
  172.20.155.171        88-d7-f6-53-23-a0     動態
  172.20.155.177        70-4d-7b-a3-4d-b6     動態
  172.20.155.178        38-2c-4a-c6-c2-e6     動態
  172.20.155.181        88-d7-f6-53-25-25     動態
  172.20.155.182        88-d7-f6-53-85-74     動態
  172.20.155.184        d0-17-c2-af-5e-b4     動態
  172.20.155.186        88-d7-f6-53-84-61     動態
  172.20.155.193        88-d7-f6-53-83-ea     動態
  172.20.155.201        88-d7-f6-53-85-d5     動態
  172.20.155.216        88-d7-f6-53-83-0d     動態
  172.20.155.230        88-d7-f6-53-85-c3     動態
  172.20.155.232        88-d7-f6-53-24-7b     動態
  172.20.155.254        00-14-1b-72-a8-00     動態
  172.20.155.255        ff-ff-ff-ff-ff-ff     靜態
  224.0.0.3             01-00-5e-00-00-03     靜態
  224.0.0.22            01-00-5e-00-00-16     靜態
  224.0.0.251           01-00-5e-00-00-fb     靜態
  224.0.0.252           01-00-5e-00-00-fc     靜態
  239.255.64.75         01-00-5e-7f-40-4b     靜態
  239.255.255.250       01-00-5e-7f-ff-fa     靜態
  255.255.255.255       ff-ff-ff-ff-ff-ff     靜態

介面: 192.168.173.2 --- 0xe
  網際網路網址          實體位址               類型
  192.168.173.255       ff-ff-ff-ff-ff-ff     靜態
  224.0.0.3             01-00-5e-00-00-03     靜態
  224.0.0.22            01-00-5e-00-00-16     靜態
  224.0.0.251           01-00-5e-00-00-fb     靜態
  224.0.0.252           01-00-5e-00-00-fc     靜態
  239.255.255.250       01-00-5e-7f-ff-fa     靜態


###考試必考
protocol(協定)
名詞解釋
NFC RFID
![image](http://intronetworks.cs.luc.edu/current/html/_images/tcp_header.svg)


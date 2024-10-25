---
layout: post
title: "記憶域スペース ダイレクト(S2D)とAzure Stack HCIという2つの用語を整理する"
date: 2024-10-14
categories: [blog, Microsoft, HCI]
---

# 記憶域スペース ダイレクト(S2D)とAzure Stack HCIという2つの用語を整理する

## 記憶域スペース ダイレクトとは？
Microsoft社が、Windows Server 2016から搭載させたSoftware Defined Stoarge機能です。

英語の名称ではStorage Space Directとなるため、Sが2回繰り返される点から通称S2Dという呼び名でも呼ばれます。  

### そもそもSDS(Software Defined Storage)って何だっけ？
ストレージの機能を、ハードウェアではなくサーバー上で実行されるソフトウェアやOS機能で実装する手法です。  
対極に存在するものの例としては、ハードウェアRAIDコントローラーやストレージベンダーが提供するSANストレージなどが挙げられます。  

## Azure Stack HCIとは？
この用語は、次の要素を併せ持ったシステムの名称です。
- Hyper-V
- Storage Space Direct
- オプションとしてのSotware Defined Network
  
また、前提として当該のシステムではWindows Serverではなく、 ***Azure Stack HCI OS***と呼ばれるOSが利用されていることを前提としています。  
ちなみに、同様の3種の機能を持つシステムをWindows Server OS環境で組むことも可能ですが、その場合には通常Azure Stack HCIと呼びません。  
~~しかし、一部のベンダーはOSがなんであってもAzure Stack HCIと呼んでいます。~~

## つまり...
S2DとAzure Stack HCIという2つの用語の関係は、単一の機能なのか、それを持つシステムであるかという違いです。(あとOSの種別も判定基準)

## しかし...
実際にはこれらの用語は、混合して使われてしまいがちな所があります。  具体的には、次のようなシーンです。  

#### Dell Technologiesから提供されている製品 **Storage Space Direct Ready Node** 
これはS2D機能を動かすことを目的とした、Dell PowerEdgeサーバーを指します。  
[Dell EMC Storage Spaces Direct (S2D) Ready Nodes for Microsoft Remote Desktop Services (RDS) –Reference Architecture](https://infohub.delltechnologies.com/en-us/section-assets/microsoft-storage-spaces-direct-ready-nodes-for-vdi-microsoft-rds-reference-architecture-1/)

**Dell AXノード**
これは、Azure Stack HCIを構成するための、Dell PowerEdgeサーバーを指します。(なお、OSはAzure Stack HCI OSまたはWindows Serverが選べます)  
[ついにリリース！ヽ(ﾟ∀ﾟ)ﾉ
      〜 New Azure Stack HCI ノード & Windows Server 2022 〜](https://japancatalog.dell.com/c/isg_blog_ax_windowsserver2022/)  

**Dell APEX Cloud Platform for Microsoft Azure**  
Azure Stack HCI OSを工場出荷時に導入して出荷されるHCIアプライアンス(Windows ServerOSは非対応)
- [Dell APEX Cloud Platform](https://www.dell.com/ja-jp/dt/apex/cloud-platforms/index.html)
- [Dell APEX Cloud Platform for Microsoft Azure](https://www.delltechnologies.com/asset/en-gb/solutions/apex/technical-support/acp-for-azure-spec-sheet.pdf)

## 参考になるページ
### Microsoft Learn
- [Windows Server の記憶域に関するドキュメント](https://learn.microsoft.com/ja-jp/windows-server/storage/storage)

- [記憶域スペース ダイレクト](https://learn.microsoft.com/ja-jp/windows-server/get-started/whats-new-in-windows-server-2016#storage-spaces-direct)

- [Azure Stack HCI の基礎](https://learn.microsoft.com/ja-jp/training/paths/azure-stack-hci-foundations/?source=recommendations)

### Microsoft
- [Azure Stack HCI](https://azure.microsoft.com/ja-jp/products/azure-stack/hci)

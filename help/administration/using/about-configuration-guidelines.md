---
title: 設定のガイドライン
description: Campaign Standard設定のガイドラインについて説明します。
page-status-flag: never-activated
uuid: 64c34729-5c98-4db0-9131-af6dd0e78fb4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
discoiquuid: 5587530a-2308-4be1-9f56-19eeb7a924d5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c2ed4b3c85ceef3b604a8f68d924c7e5d9fad900

---


# 設定のガイドライン {#about-configuration-guidelines}

## 互換性のあるブラウザー{#compatible-browsers}

Adobe Campaign標準は、コンピューターのほとんどのブラウザーと、タブレット用の主なオペレーティングシステムとの互換性があります。

Adobe Campaign標準は、タブレットでの表示モードとして横置きのみサポートします。

以下は、Adobe Campaign標準と互換性のあるブラウザーのリストです。

**コンピュータ：**

* Chrome（最新バージョン）
* Firefox（最新バージョン）
* Safari（最新バージョン）
* Microsoft Edge（最新バージョン）

**タブレット：**

* iOS（バージョン7以降）
* Android（バージョン4.4以降）

## Campaign Standard ネットワークエンドポイント {#campaign-standard-network-endpoints}

Campaign Standardで使用されるエンドポイントは次のとおりです。

| コンテキスト | URL |
|--- |--- |
| キャンペーンインスタンス | `https://*.experiencecloud.adobe.com` （テナントID * +クライアントドメイン）<br>`https://*.campaign.adobe.com` (キャンペーンインスタンステナント) |
| IMS | `https://adobeid-na1.services.adobe.com`<br>`https://*.adobelogin.com` |
| Experience Cloud | `https://experiencecloud.adobe.com` |
| トラッキング | `https://*.adobedtm.com`<br>`https://*.demdex.net`<br>`https://*.omtrdc.net` |
| Creative SDK for Image Editor | `https://dme0ih8comzn4.cloudfront.net`<br>`https://d42hh4005hpu.cloudfront.net/`<br>`https://cdn-creativesdk.adobe.io/`<br>`https://api-ag.aviary.com/`<br>`https://feather-client-files-aviary-prod-us-east-1.s3.amazonaws.com/` |
| アセットの統合 | `https://*.marketing-assets.adobe.com` |
| アドビの内部サービス | `https://*.adobe.io` |
| 調査 | `https://adobe.allegiancetech.com` |
| デフォルトのブランドURL（クライアント設定前） | `https://*.adobe-campaign.com` |

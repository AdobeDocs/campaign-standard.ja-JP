---
solution: Campaign Standard
product: campaign
title: エクスペリエンスデータモデルの概要
description: エクスペリエンスデータモデル(XDM)は、データをAdobe Experience Platformのソリューションや製品で使用する際に取り込むことができる、標準的なデータスキーマのセットです。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 7%

---


# エクスペリエンスデータモデルの概要{#experience-data-model-overview}

>[!IMPORTANT]
>
>Adobe Experience Platformデータコネクタは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 ご利用になる場合は、Adobeカスタマーケアにお問い合わせください。

エクスペリエンスデータモデル(XDM)は、データをAdobe Experience Platformのソリューションや製品で使用する際に取り込むことができる、標準的なデータスキーマのセットです。

XDMスキーマの作成と管理は、専用のAPIまたはXDMユーザーインターフェイスを使用して行うことができます。

## XDMワークスペース{#xdm-workspace}

XDM Workspaceでは、データスキーマの表示、作成、拡張を行うことができます。

XDMユーザーインターフェイスにアクセスするには、Adobe Experience Platformを開きます。 XDMスキーマを作成または拡張するには、「データモデル」ウィンドウにナビゲートします。

[XDM Workspaceの完全なドキュメント](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/api/getting-started.html)を参照してください。

![](assets/aep_xdmworkspace.png)

## XDM API {#xdm-api}

XDMスキーマAPIを使用して、次の操作を実行できます。

* 既存のスキーマのリストの表示
* 特定のスキーマの表示既存のスキーマの拡張
* 拡張子追加のフィールド
* 新しいスキーマの作成と更新
* 表示スキーマ記述子
* スキーマ記述子の作成、更新、削除

API呼び出しを操作するための詳細は、[デベロッパーガイド](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html)で入手できます。

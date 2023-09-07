---
title: エクスペリエンスデータモデルの概要
description: エクスペリエンスデータモデル (XDM) は、Adobe Experience Platformのソリューションや製品で使用するためにデータを取り込むことのできる、データスキーマの標準セットです。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: cc1aa669-30cd-4ea4-9fab-4d1b6c373744
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# エクスペリエンスデータモデルの概要 {#experience-data-model-overview}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector は現在ベータ版です。通知なしに頻繁に更新される可能性があります。 お客様は、これらの機能にアクセスするには、Azure 上でホストされている必要があります（現在、北米ではベータ版のみ）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

エクスペリエンスデータモデル (XDM) は、Adobe Experience Platformのソリューションや製品で使用するためにデータを取り込むことのできる、データスキーマの標準セットです。

XDM スキーマの作成と管理は、専用 API で、または XDM ユーザーインターフェイスで使用できます。

## XDM ワークスペース {#xdm-workspace}

XDM Workspace は、データスキーマを表示、作成および拡張する機能を提供します。

XDM ユーザーインターフェイスにアクセスするには、 Adobe Experience Platformを開きます。 データモデルウィンドウに移動して、XDM スキーマを作成または拡張します。

詳細を見る [XDM Workspace ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html).

![](assets/aep_xdmworkspace.png)

## XDM API {#xdm-api}

XDM スキーマ API を使用して、次のアクションを実行できます。

* 既存のスキーマのリストの表示
* 特定のスキーマの表示既存のスキーマの拡張
* 拡張機能にフィールドを追加する
* 新しいスキーマの作成と更新
* スキーマ記述子の表示
* スキーマ記述子の作成、更新、削除

API 呼び出しの操作に関する詳細は、 [開発者ガイド](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html).

---
title: エクスペリエンスデータモデルの概要
description: エクスペリエンスデータモデル(XDM)は、Adobe Experience Platformのソリューションや製品で使用するためにデータを取り込むことのできる、標準的なデータスキーマセットです。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: cc1aa669-30cd-4ea4-9fab-4d1b6c373744
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# エクスペリエンスデータモデルの概要 {#experience-data-model-overview}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connectorは現在ベータ版です。通知なしに頻繁に更新される可能性があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米でのみベータ版）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

エクスペリエンスデータモデル(XDM)は、Adobe Experience Platformのソリューションや製品で使用するためにデータを取り込むことのできる、標準的なデータスキーマセットです。

XDMスキーマの作成と管理は、専用のAPIまたはXDMユーザーインターフェイスで利用できます。

## XDMワークスペース {#xdm-workspace}

XDM Workspaceは、データスキーマを表示、作成および拡張する機能を備えています。

XDMユーザーインターフェイスにアクセスするには、 Adobe Experience Platformを開きます。 データモデルウィンドウに移動して、XDMスキーマを作成または拡張します。

[XDM Workspaceの完全なドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html)を参照してください。

![](assets/aep_xdmworkspace.png)

## XDM API {#xdm-api}

XDMスキーマAPIを使用して、次のアクションを実行できます。

* 既存のスキーマのリストの表示
* 特定のスキーマの表示既存のスキーマの拡張
* 拡張機能へのフィールドの追加
* 新しいスキーマの作成と更新
* スキーマ記述子の表示
* スキーマ記述子の作成、更新、削除

API呼び出しの操作に関する詳細については、『[開発者ガイド](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html)』を参照してください。

---
title: エクスペリエンスデータモデルの概要
description: Experience Data Model （XDM）は、Adobe Experience Platformのソリューションや製品で使用するためにデータを取り込む可能性のあるデータスキーマの標準セットです。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: cc1aa669-30cd-4ea4-9fab-4d1b6c373744
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# エクスペリエンスデータモデルの概要 {#experience-data-model-overview}

>[!IMPORTANT]
>
>現在、Adobe Experience Platform Data Connector はベータ版です。予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、お客様を Azure でホストする必要があります（現在は北米向けのベータ版のみ）。 へのアクセスを希望する場合は、Adobe カスタマーケアにお問い合わせください。

Experience Data Model （XDM）は、Adobe Experience Platformのソリューションや製品で使用するためにデータを取り込む可能性のあるデータスキーマの標準セットです。

XDM スキーマの作成と管理は、専用の API または XDM ユーザーインターフェイスで利用できます。

## XDM ワークスペース {#xdm-workspace}

XDM Workspaceでは、データスキーマの表示、作成、拡張を行うことができます。

XDM ユーザーインターフェイスにアクセスするには、Adobe Experience Platformを開きます。 データモデルウィンドウに移動して、XDM スキーマを作成または拡張します。

完全な [XDM Workspaceのドキュメント &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=ja) を参照してください。

![](assets/aep_xdmworkspace.png)

## XDM API {#xdm-api}

XDM スキーマ API を使用して、次のアクションを実行できます。

* 既存のスキーマのリストの表示
* 特定のスキーマの表示既存のスキーマの拡張
* 拡張機能へのフィールドの追加
* 新しいスキーマの作成と更新
* スキーマ記述子の表示
* スキーマ記述子の作成、更新、削除

API 呼び出しを操作する詳細については、[&#x200B; 開発者ガイド &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=ja) を参照してください。

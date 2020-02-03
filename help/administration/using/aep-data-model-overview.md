---
title: エクスペリエンスデータモデルの概要
description: エクスペリエンスデータモデル(XDM)は、データを取り込んでAdobe Experience Platformのソリューションおよび製品で使用するための標準的なデータスキーマセットです。
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 67223cf8eed46e2431c03674bd837262e37c7473

---


# エクスペリエンスデータモデルの概要 {#experience-data-model-overview}

>[!IMPORTANT]
>
>キャンペーン標準データサービスは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米向けベータ版のみ）。 ご希望の場合は、アドビカスタマーケアにお問い合わせください。

エクスペリエンスデータモデル(XDM)は、データを取り込んでAdobe Experience Platformのソリューションおよび製品で使用するための標準的なデータスキーマセットです。

XDMスキーマの作成と管理は、専用のAPIまたはXDMユーザーインターフェイスで行うことができます。

## XDMワークスペース {#xdm-workspace}

XDM Workspaceでは、データスキーマの表示、作成および拡張が可能です。

XDMユーザーインターフェイスにアクセスするには、Adobe Experience Platformを開きます。 XDMスキーマを作成または拡張するには、「データモデル」ウィンドウに移動します。

XDM Workspaceの完全なドキュメ [ントを参照してください](https://www.adobe.io/apis/experienceplatform/home/xdm/xdmservices.html#!api-specification/markdown/narrative/technical_overview/schema_registry/xdm_system/xdm_system_in_experience_platform.md)。

![](assets/aep_xdmworkspace.png)

## XDM API {#xdm-api}

XDMスキーマAPIを使用して、次の操作を実行できます。

* 既存のスキーマの一覧の表示
* 特定のスキーマを表示する既存のスキーマを拡張する
* 拡張子へのフィールドの追加
* 新しいスキーマの作成と更新
* スキーマ記述子の表示
* スキーマ記述子の作成、更新、削除

API呼び出しを操作するための詳細については、デベロッパーガイドを参 [照してください](https://www.adobe.io/apis/experienceplatform/home/xdm/xdmservices.html#!api-specification/markdown/narrative/technical_overview/schema_registry/schema_registry_developer_guide.md)。

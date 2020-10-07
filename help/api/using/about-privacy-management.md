---
title: プライバシー管理について
description: APIを使用したプライバシー管理について詳しく見る
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 4%

---


# プライバシー管理について {#about-privacy-management}

Campaign StandardAPIは、GDPRやCCPAなどのプライバシー規制に関するリクエストの自動処理を可能にする機能を提供します。

実行できるアクションは次のとおりです。

* 新しいプライバシーリクエストの作成、
* プライバシー要求の監視、
* プライバシーデータファイルの取得、
* プロファイルのCCPAオプトアウトステータスを管理します。

プライバシーAPIエンドポイントは **/privacy/privacyTool**&#x200B;です。 PrivacyToolリソースの説明と関連するフィルターは、リソースのメタデータで使用できます。 詳しくは、 [メタデータのメカニズムを参照してください](../../api/using/metadata-mechanism.md)。

CCPAオプトアウトは、 **ccpaOptOut** プロファイル属性を使用して管理します。

Adobe Campaign Standardおよびプライバシーコンプライアンスについて詳しくは、 [専用ドキュメントを参照してください](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html)。

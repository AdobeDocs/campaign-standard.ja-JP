---
title: プライバシー管理について
description: API を使用したプライバシー管理の詳細を説明します
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: 210289d44f0ad0ebf0b2654f6e9795adad7dd458
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---


# プライバシー管理について {#about-privacy-management}

Campaign StandardAPI は、GDPR や CCPA などのプライバシー規制に関連するリクエストを自動処理できる機能を提供します。

実行できるアクションは次のとおりです。

* 新しいプライバシーリクエストを作成し、
* プライバシーリクエストの監視
* プライバシーデータファイルの取得
* プロファイルの CCPA オプトアウトステータスを管理します。

プライバシー API エンドポイントは、 **/privacy/privacyTool**. PrivacyTool リソースの説明と関連フィルターは、リソースのメタデータ内で使用できます。 詳しくは、 [メタデータのメカニズム](../../api/using/metadata-mechanism.md).

CCPA のオプトアウトは、 **ccpaOptOut** プロファイル属性。

Adobe Campaign Standardおよびプライバシーコンプライアンスについて詳しくは、 [専用ドキュメント](../../start/using/privacy-requests.md).

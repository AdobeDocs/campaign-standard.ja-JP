---
title: プライバシーの管理について
description: API を使用したプライバシー管理の詳細
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: 210289d44f0ad0ebf0b2654f6e9795adad7dd458
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---


# プライバシーの管理について {#about-privacy-management}

Campaign StandardAPI は、GDPR や CCPA などのプライバシー規制に関連するリクエストの自動処理を可能にする機能を提供します。

実行できるアクションは次のとおりです。

* 新しいプライバシーリクエストを作成し、
* プライバシーリクエストの監視
* プライバシーデータファイルの取得。
* プロファイルの CCPA オプトアウトステータスを管理します。

プライバシー API エンドポイントは、**/privacy/privacyTool** です。 PrivacyTool リソースの説明と関連するフィルターを、リソースのメタデータで使用できます。 [ メタデータメカニズム ](../../api/using/metadata-mechanism.md) を参照してください。

CCPA オプトアウトは、**ccpaOptOut** プロファイル属性を使用して管理されます。

Adobe Campaign Standardとプライバシーコンプライアンスについて詳しくは、[ 専用ドキュメント ](../../start/using/privacy-requests.md) を参照してください。

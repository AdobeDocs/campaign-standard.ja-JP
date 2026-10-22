---
title: プライバシー管理について
description: APIを使用したプライバシー管理について詳しく見る
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 0%
---

# プライバシー管理について {#about-privacy-management}

Campaign Standard APIは、GDPRやCCPAなどのプライバシー規制に関連するリクエストを自動的に処理できる機能を提供します。

実行できるアクションは次のとおりです。

* 新しいプライバシーリクエストを作成し，
* プライバシーリクエスト，
* プライバシーデータファイルを取得し，
* プロファイルのCCPA オプトアウトステータスを管理します。

プライバシーAPI エンドポイントは&#x200B;**/privacy/privacyTool**&#x200B;です。 PrivacyTool リソースの説明と関連フィルターは、リソースメタデータで使用できます。 [ メタデータメカニズム ](../../api/using/metadata-mechanism.md)を参照してください。

CCPA オプトアウトは、**ccpaOptOut** プロファイル属性を使用して管理されます。

Adobe Campaign Standardとプライバシーのコンプライアンスについて詳しくは、[専用ドキュメント ](../../start/using/privacy-requests.md)を参照してください。

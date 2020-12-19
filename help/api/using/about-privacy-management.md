---
solution: Campaign Standard
product: campaign
title: プライバシー管理について
description: APIを使用したプライバシー管理について詳しく見る
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# プライバシー管理について{#about-privacy-management}

Campaign StandardAPIは、GDPRやCCPAなどのプライバシー規制に関するリクエストの自動処理を可能にする機能を提供します。

実行できるアクションは次のとおりです。

* 新しいプライバシーリクエストの作成、
* プライバシー要求の監視、
* プライバシーデータファイルの取得、
* プロファイルのCCPAオプトアウトステータスを管理します。

プライバシーAPIエンドポイントは&#x200B;**/privacy/privacyTool**&#x200B;です。 PrivacyToolリソースの説明と関連するフィルターは、リソースのメタデータで使用できます。 [メタデータのメカニズム](../../api/using/metadata-mechanism.md)を参照してください。

CCPAオプトアウトは、**ccpaOptOut**&#x200B;プロファイル属性を使用して管理します。

Adobe Campaign Standardとプライバシーのコンプライアンスについて詳しくは、[専用ドキュメント](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html)を参照してください。

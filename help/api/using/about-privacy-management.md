---
title: プライバシー管理について
description: APIを使用したプライバシー管理の詳細を説明します
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 4%

---


# プライバシー管理について {#about-privacy-management}

Campaign StandardAPIは、GDPRやCCPAなどのプライバシー規制に関連するリクエストを自動処理できる機能を提供します。

実行できるアクションは次のとおりです。

* 新しいプライバシーリクエストの作成
* プライバシーリクエストの監視
* プライバシーデータファイルの取得
* プロファイルのCCPAオプトアウトステータスを管理します。

プライバシーAPIエンドポイントは&#x200B;**/privacy/privacyTool**&#x200B;です。 PrivacyToolリソースの説明と関連フィルターは、リソースメタデータで使用できます。 [メタデータのメカニズム](../../api/using/metadata-mechanism.md)を参照してください。

CCPAのオプトアウトは、**ccpaOptOut**&#x200B;プロファイル属性を使用して管理します。

Adobe Campaign Standardとプライバシーのコンプライアンスについて詳しくは、[専用のドキュメント](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html)を参照してください。

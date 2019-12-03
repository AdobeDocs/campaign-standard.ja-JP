---
title: プライバシー管理について
description: APIを使用したプライバシー管理に関する詳細情報
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# プライバシー管理について {#about-privacy-management}

キャンペーン標準APIは、GDPRやCCPAなどのプライバシー規制に関連するリクエストの自動処理を可能にする機能を提供します。

実行できるアクションは次のとおりです。

* 新しいプライバシーリクエストの作成、
* プライバシー要求の監視、
* プライバシーデータファイルの取得、
* プロファイルのCCPAオプトアウトステータスを管理します。

プライバシーAPIエンドポイ **ントは/privacy/privacyToolです**。 PrivacyToolリソースの説明と関連するフィルターは、リソースメタデータで使用できます。 詳しくは、メ [タデータのメカニズムを参照し](../../api/using/metadata-mechanism.md)。

CCPAオプトアウトは、ccpaOptOutプロファイル属性を使 **用して管理** します。

Adobe Campaign Standardとプライバシーコンプライアンスについて詳しくは、専用ドキュメントを参照 [してください](https://helpx.adobe.com/campaign/kb/acs-privacy.html)。

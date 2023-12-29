---
title: Campaign Standard API の概要
description: Campaign にテクノロジーのパネルを搭載することで、統合を作成し、独自のエコシステムを構築します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 100%

---

# Campaign Standard API の基本を学ぶ {#get-started-apis}

Campaign Standard API は、Adobe Campaign Standard 向けの&#x200B;**統合を実現**&#x200B;し、Adobe Campaign Standard と使用するテクノロジーのパネルを連携させて&#x200B;**独自のエコシステムを構築**&#x200B;することを目的としています。

Adobe Campaign Standard API を使用すると、次の機能にアクセスできます。

<table><tr>
 <td valign="top"><a href="../../api/using/retrieving-profiles.md"><img width="60px" alt="conditions" src="assets/icon_profile.svg"/></a><p><a href="../../api/using/retrieving-profiles.md">プロファイル</a></p></td>
<td valign="top"><a href="../../api/using/creating-a-service.md"><img width="60px" alt="conditions" src="assets/icon_services.svg"/></a><p><a href="../../api/using/creating-a-service.md">サービスと購読</a></p></td>
<td valign="top"><a href="../../api/using/interacting-with-custom-resources.md"><img width="60px" alt="conditions" src="assets/icon_customresources.svg"/></a><p><a href="../../api/using/interacting-with-custom-resources.md">カスタムリソース</a></p></td>
<td valign="top"><a href="../../api/using/interacting-with-marketing-history.md"><img width="60px" alt="conditions" src="assets/icon_marketinghistory.svg"/></a><p><a href="../../api/using/interacting-with-marketing-history.md">マーケティング履歴</a></p></td>
</tr>
<tr>
<td valign="top"><a href="../../api/using/creating-a-privacy-request.md"><img width="60px" alt="conditions" src="assets/icon_privacy.svg"/></a><p><a href="../../api/using/creating-a-privacy-request.md">プライバシーの管理</a></p></td>
<td valign="top"><a href="../../api/using/managing-transactional-messages.md"><img width="60px" alt="conditions" src="assets/icon_transactionalmessage.svg"/></a><p><a href="../../api/using/managing-transactional-messages.md">トランザクションメッセージ</a></p></td>
<td valign="top"><a href="../../api/using/controlling-a-workflow.md"><img width="60px" alt="conditions" src="assets/icon_workflows.svg"/></a><p><a href="../../api/using/controlling-a-workflow.md">ワークフロー</a></p></td>
<td valign="top"><a href="../../api/using/retrieving-an-organizational-unit.md"><img width="60px" alt="conditions" src="assets/icon_units.svg"/></a><p><a href="../../api/using/retrieving-an-organizational-unit.md">組織単位</a></p></td>
</tr></table>

>[!NOTE]
>
>API 呼び出しを実行する前に、使用許諾契約に対応する拡張制限を確認してください。詳しくは、[このページ](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。

Campaign Standard API を使用するには、Adobe I/O アカウントが必要です。これは、適切な API 機能を探し、利用するために必須となる最初の手順です。
詳しくは、[この節](../../api/using/setting-up-api-access.md)を参照してください。

アドビが提供する API は、REST インターフェイスと JSON ペイロードを備えた&#x200B;**標準的な概念**&#x200B;を使用します 。

>[!NOTE]
>
>これらの例はすべて Postman で使用できますが、任意の REST クライアントをご利用いただけます。

このドキュメントでは、すべてのエンドポイントについて詳述するほか、API の操作に関する一般的な基本事項、完全な API リファレンス、コード例、クイックスタートガイドを紹介します。

API について不明な点や問題がある場合は、[アドビコミュニティ](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)で質問してください。

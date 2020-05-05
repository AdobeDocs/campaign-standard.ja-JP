---
title: Campaign StandardAPIの概要
description: キャンペーン標準APIについて詳しく説明します。
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
source-git-commit: 181f7114bd7b9d633de44687320f0c897e146862

---


# Get started with Campaign Standard APIs {#get-started-apis}

Campaign StandardAPIは、Adobe Campaign標準の **統合を** 作成し、標準を使用するテクノロジパネルと連携させて独自のエコシステム **(Adobe Campaign標準)を** 構築することを目的としています。

Adobe Campaign標準APIを使用すると、次の機能にアクセスできます。

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
>API呼び出しを実行する前に、使用許諾契約に対応するスケール制限を確認してください。 詳しくは、[このページ](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。

Campaign StandardAPIを使用するには、Adobe I/Oアカウントが必要です。 これは、次にAPI機能を検出するための必須の最初の手順です。
詳しくは、[この節](../../api/using/setting-up-api-access.md)を参照してください。

アドビが提供するAPIは、RESTインターフェイスとJSONペイロードを備えた **標準的な概念を使用します** 。

>[!NOTE]
>
>これらの例はすべてPostmanで使用できますが、お気に入りのRESTクライアントを自由に使用できます。

すべてのエンドポイントについて、このドキュメントで詳しく説明します。APIの操作に関する一般的な節、完全なAPIリファレンス、コード例、クイック開始ガイドが含まれています。

何か足りない場合や間違っている場合は、 [コミュニティに問い合わせてください](https://help-forums.adobe.com/content/adobeforums/en/campaign-forum/adobe-campaign.html)。

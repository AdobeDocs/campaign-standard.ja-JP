---
title: Campaign Standard API について
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
source-git-commit: 27ca2116c49f9c23a56c178a3e3f7baf2f755c45

---


# Campaign Standard API について{#about-campaign-standard-apis}

Campaign Standard APIは、Adobe Campaign Standardの統合を作成し、使用するテクノロジーのパネルとAdobe Campaign Standard ******** を連携させて独自のエコシステムを構築することを目的としています。

Adobe Campaign Standard APIを使用すると、次の機能にアクセスできます。

<table>
<tr>
    <td valign="top">
        <a href="../../api/using/retrieving-profiles.md"><img width="60px" alt="conditions" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/creating-a-service.md"><img width="60px" alt="conditions" src="assets/icon_services.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-custom-resources.md"><img width="60px" alt="conditions" src="assets/icon_customresources.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-marketing-history.md"><img width="60px" alt="conditions" src="assets/icon_marketinghistory.svg"/></a>
    </td>
</tr>
<tr>
<td>プロファイル</td>
<td>サービスと購読</td>
<td>カスタムリソース</td>
<td>マーケティング履歴</td>
</tr>
<tr>
    <td valign="top">
        <a href="../../api/using/creating-a-privacy-request.md"><img width="60px" alt="conditions" src="assets/icon_privacy.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/managing-transactional-messages.md"><img width="60px" alt="conditions" src="assets/icon_transactionalmessage.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/controlling-a-workflow.md"><img width="60px" alt="conditions" src="assets/icon_workflows.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/retrieving-an-organizational-unit.md"><img width="60px" alt="conditions" src="assets/icon_units.svg"/></a>
    </td>
</tr>
<tr>
<td>プライバシーの管理</td>
<td>トランザクションメッセージ</td>
<td>ワークフロー</td>
<td>組織単位</td>
</td>
</table>

>[!NOTE]
>
>API呼び出しを実行する前に、使用許諾契約に対応するスケール制限を確認してください。 詳しくは、[このページ](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。

Campaign Standard APIを使用するには、Adobe I/Oアカウントが必要です。 これは、今後API機能を見つけるための必須の最初の手順です。
詳しくは、[この節](../../api/using/setting-up-api-access.md)を参照してください。

提供するAPIは、RESTインターフェ **イスとJSONペイロードで** 、標準的な概念を使用します。

>[!NOTE]
>
>すべての例はPostmanで使用できますが、お気に入りのRESTクライアントを自由に使用できます。

このドキュメントでは、APIの操作、完全なAPIリファレンス、コード例、クイックスタートガイドに関する一般的なノーションを含む、すべてのエンドポイントについて詳しく説明しています。

何か足りないものや間違っているものがあれば、コミュニティにお問い合わ [せくださ](https://help-forums.adobe.com/content/adobeforums/en/campaign-forum/adobe-campaign.html)い。
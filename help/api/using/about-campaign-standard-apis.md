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
source-git-commit: ea78c0d4bc338eed81a4e0cd39dfdd76837aeb2c

---


# Campaign Standard API について{#about-campaign-standard-apis}

Campaign Standard APIは、Adobe Campaign Standardの統合を作成し、使用するテクノロジーのパネルとAdobe Campaign Standard ******** を連携させて独自のエコシステムを構築することを目的としています。

Adobe Campaign Standard APIを使用すると、以下の節で説明する様々な機能にアクセスできます。

<table>
<tr>
    <td valign="top">
        <a href="../../api/using/retrieving-profiles.md"><img alt="conditions" src="assets/icon_profile.png"/></a>
        <div><a href="../../api/using/retrieving-profiles.md"><strong>プロファイル</strong></a></div>
        <em>データベースのプロファイルを操作する方法を説明します。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/creating-a-service.md"><img alt="conditions" src="assets/icon_services.png"/></a>
        <div><a href="../../api/using/creating-a-service.md"><strong>サービスと購読</strong></a></div>
        <em>データベースのサービスを操作し、サブスクリプションを管理する方法を説明します。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-custom-resources.md"><img alt="conditions" src="assets/icon_customresources.png"/></a>
        <div><a href="../../api/using/interacting-with-custom-resources.md"><strong>カスタムリソース</strong></a></div>
        <em>データベースからカスタムリソースを操作する方法を説明します。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-marketing-history.md"><img alt="conditions" src="assets/icon_marketinghistory.png"/></a>
        <div><a href="../../api/using/interacting-with-marketing-history.md"><strong>マーケティング履歴</strong></a></div>
        <em>プロファイルのマーケティング履歴を操作する方法を説明します。</em>
    </td>
</tr>
<tr>
    <td valign="top">
        <a href="../../api/using/creating-a-privacy-request.md"><img alt="conditions" src="assets/icon_privacy.png"/></a>
        <div><a href="../../api/using/creating-a-privacy-request.md"><strong>プライバシー</strong></a></div>
        <em>プライバシー管理の詳細を表示します。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/managing-transactional-messages.md"><img alt="conditions" src="assets/icon_transactionalmessage.png"/></a>
        <div><a href="../../api/using/managing-transactional-messages.md"><strong>トランザクションメッセージ</strong></a></div>
        <em>トランザクションイベントを送信する方法について説明します。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/controlling-a-workflow.md"><img alt="conditions" src="assets/icon_workflows.png"/></a>
        <div><a href="../../api/using/controlling-a-workflow.md"><strong>ワークフロー</strong></a></div>
        <em>ワークフローを制御およびトリガーする方法について説明します。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/retrieving-an-organizational-unit.md"><img alt="conditions" src="assets/icon_units.png"/></a>
        <div><a href="../../api/using/retrieving-an-organizational-unit.md"><strong>組織単位と地理的単位</strong></a></div>
        <em>組織単位と地理的単位を操作する方法を説明します。</em>
    </td>
</tr>
</table>

Campaign Standard APIを使用するには、Adobe I/Oアカウントが必要です。 これは、今後API機能を見つけるための必須の最初の手順です。
詳しくは、[この節](../../api/using/setting-up-api-access.md)を参照してください。

提供するAPIは、RESTインターフェ **イスとJSONペイロードで** 、標準的な概念を使用します。

このドキュメントでは、APIの操作、コード例、クイックスタートガイドに関する一般的なノーションを含む、すべてのエンドポイントについて詳しく説明しています。 すべての例はPostmanで使用できますが、お気に入りのRESTクライアントを自由に使用できます。

>[!CAUTION]
>
>API呼び出しを実行する前に、使用許諾契約に対応するスケール制限を確認してください。 詳しくは、[このページ](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。

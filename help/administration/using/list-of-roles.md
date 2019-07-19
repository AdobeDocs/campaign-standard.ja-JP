---
title: ロールのリスト
seo-title: ロールのリスト
description: ロールのリスト
seo-description: ユーザに割り当てる役割のリストを見つけます。
page-status-flag: 常にアクティブ化されていない
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29ba0
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: ユーザーおよびセキュリティ
discoiquuid: ceaa3c94-9e1a-4271- b443- b00b4068929f
context-tags: ロール、概要;ロール、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# List of roles{#list-of-roles}

デフォルトでは、Adobe Campaignには一連のロールがあり、ユーザーおよびユーザーグループに割り当てられた個別の認証を定義できます。組織単位と組み合わせることで、ユーザーはインターフェイスをフィルタリングして表示し、様々な機能へのアクセスを定義できます。For more on this, refer to the [Roles and permissions table](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

![](assets/user_management_3.png)

Roles can be managed from the **[!UICONTROL Administration > Users & Security > Roles]** menu.

デフォルトの権限は次のとおりです。

* **[!UICONTROL Administration]**:汎用管理の右。
* **[!UICONTROL Datamodel]**:パブリケーションを実行し、カスタムリソースを作成する権利です。
* **[!UICONTROL Export]**:データをエクスポートするRight。
* **[!UICONTROL Generic import]**:データに対して汎用的なインポートを実行する権限です。For this to work, you need to link the **[!UICONTROL Generic import]** role to the **[!UICONTROL Workflow]** role.
* **[!UICONTROL Prepare deliveries]**:配信の準備、編集、配信の開始、配達確認の送信を行う権利。
* **[!UICONTROL Start deliveries]**:以前に準備した配信を検証するための権限。
* **[!UICONTROL Workflow]**:ワークフローを使用する権限。

>[!CAUTION]
>
>配信品質ロールは、アドビ管理者のみが使用します。ユーザーに対して許可しないでください。

**関連トピック:**

* [アクセス管理について](../../administration/using/about-access-management.md)
* [グループとユーザーの管理](../../administration/using/managing-groups-and-users.md)


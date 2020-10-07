---
title: 役割のリスト
description: ユーザーに割り当てることができる役割のリストを確認します。
page-status-flag: never-activated
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: ceaa3c94-9e1a-4271-b443-b00b4068929f
context-tags: role,overview;role,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 94%

---


# 役割のリスト{#list-of-roles}

Adobe Campaign には、ユーザーやユーザーグループに割り当てる単一権限を定義するための一連の役割がデフォルトで用意されています。

組織単位と役割を組み合わせることにより、ユーザーには該当するインターフェイスのみ表示され、様々な機能に対するユーザーのアクセスを定義できます。

詳しくは、[役割と権限の対応表](/help/administration/using/assets/acs_rights.pdf)を参照してください。この表には、選択した権限に応じて、インターフェイスで使用できる機能の詳細が示されています。

[![画像](assets/user_management_3.png)](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/users-and-security/assets/acs_rights.pdf)

役割は&#x200B;**[!UICONTROL Administration > Users & Security > Roles]**&#x200B;メニューから管理できます。

デフォルトの権限は次のとおりです。

* **[!UICONTROL Administration]**：一般的な管理権限
* **[!UICONTROL Datamodel]**：パブリケーションの実行とカスタムリソースの作成をおこなう権限
* **[!UICONTROL Generic import]**：データに対する一般的なインポートを実行する権限。この権限を有効にするには、「**[!UICONTROL Generic import]**」の役割を「**[!UICONTROL Workflow]**」の役割にリンクする必要があります。
* **[!UICONTROL Prepare deliveries]**：配信の作成、変更、準備、削除をおこなう権限。この役割を持つユーザーは、配信の準備はできますが、送信はできません。
* **[!UICONTROL Start deliveries]**：配信の作成、変更、準備、送信、削除をおこなう権限。
* **[!UICONTROL Workflow]**：ワークフローの実行（開始、停止、一時停止など）を管理する権限。この役割を持つユーザーは、ワークフロー内でも配信を送信できません。

**関連トピック：**

* [アクセス管理について](../../administration/using/about-access-management.md)
* [グループとユーザーの管理](../../administration/using/managing-groups-and-users.md)

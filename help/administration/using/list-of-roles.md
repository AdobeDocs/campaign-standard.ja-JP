---
title: 役割のリスト
description: ユーザーに割り当てることができる役割のリストを確認します。
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: role,overview;role,main
feature: Access Management
role: Admin
level: Experienced
exl-id: 00714c80-bdaf-4241-bf2f-51498ca1dbef
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 85%

---

# 役割のリスト{#list-of-roles}

Adobe Campaign には、ユーザーやユーザーグループに割り当てる単一権限を定義するための一連の役割がデフォルトで用意されています。

組織単位と役割を組み合わせることにより、ユーザーには該当するインターフェイスのみ表示され、様々な機能に対するユーザーのアクセスを定義できます。

役割は&#x200B;**[!UICONTROL Administration > Users & Security > Roles]**&#x200B;メニューから管理できます。

デフォルトの権限は次のとおりです。

* **[!UICONTROL Administration]**：一般的な管理権限

   >[!NOTE]
   >
   >Experience Cloudトリガーを操作する必要がある場合は、「Experience Cloudトリガー」メニューにアクセスするための&#x200B;**[!UICONTROL Administration]**&#x200B;権限が必要です。 Experience Cloudトリガーの詳細については、[ページ](../../integrating/using/about-adobe-experience-cloud-triggers.md)を参照してください。

* **[!UICONTROL Datamodel]**：パブリケーションの実行とカスタムリソースの作成をおこなう権限
* **[!UICONTROL Generic import]**：データに対する一般的なインポートを実行する権限。この権限を有効にするには、「**[!UICONTROL Generic import]**」の役割を「**[!UICONTROL Workflow]**」の役割にリンクする必要があります。
* **[!UICONTROL Prepare deliveries]**：配信の作成、変更、準備、削除をおこなう権限。この役割を持つユーザーは、配信の準備はできますが、送信はできません。
* **[!UICONTROL Start deliveries]**：配信の作成、変更、準備、送信、削除をおこなう権限。
* **[!UICONTROL Workflow]**：ワークフローの実行（開始、停止、一時停止など）を管理する権限。この役割を持つユーザーは、ワークフロー内でも配信を送信できません。

詳しくは、[役割と権限の対応表](/help/administration/using/assets/acs_rights.pdf)を参照してください。この表には、選択した権限に応じて、インターフェイスで使用できる機能の詳細が示されています。

[![画像](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)

**関連トピック：**

* [アクセス管理について](../../administration/using/about-access-management.md)
* [グループとユーザーの管理](../../administration/using/managing-groups-and-users.md)

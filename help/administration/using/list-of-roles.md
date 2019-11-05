---
title: 役割のリスト
description: ユーザーに割り当て可能なロールのリストを確認します。
page-status-flag: 非活性化の
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: ユーザーとセキュリティ
discoiquuid: ceaa3c94-9e1a-4271-b443-b00b4068929f
context-tags: 役割，概要；役割，メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 役割のリスト{#list-of-roles}

デフォルトでは、Adobe Campaignには一連のロールが用意されており、ユーザーおよびユーザーグループに割り当てられた一元的な承認を定義できます。 組織単位と組み合わせて、ユーザーはインターフェイスをフィルター表示し、様々な機能へのアクセスを定義できます。 詳しくは、「ロールと権限」の表 [を参照してください](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)。

[![画像](/help/administration/using/assets/user_management_3.png)](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

役割はメニューから管理でき **[!UICONTROL Administration > Users & Security > Roles]** ます。

デフォルトの権限は次のとおりです。

* **[!UICONTROL Administration]**:汎用管理権限。
* **[!UICONTROL Datamodel]**:パブリケーションを実行し、カスタムリソースを作成する権限。
* **[!UICONTROL Export]**: データのエクスポート権限.
* **[!UICONTROL Generic import]**:データに対して汎用インポートを実行する権限。 これを機能させるには、ロールをロールにリン **[!UICONTROL Generic import]** クする必要があ **[!UICONTROL Workflow]** ります。
* **[!UICONTROL Prepare deliveries]**:配信の作成、変更、準備および削除を行う権限。 このロールを持つユーザーは、配信を準備できますが、送信することはできません。
* **[!UICONTROL Start deliveries]**:配信の作成、変更、準備、送信および削除を行う権限。
* **[!UICONTROL Workflow]**:ワークフローの作成、変更、開始および削除を行う権限です。 このロールを持つユーザーは、ワークフロー内でも配信を送信できません。

>[!CAUTION]
>
>、、、 **[!UICONTROL Deliverability]**&#x200B;および **[!UICONTROL Command execution]**&#x200B;役割 **[!UICONTROL Export]**&#x200B;は、 **[!UICONTROL File access]** アドビ **[!UICONTROL Message Center push]** 管理者の内部使用のみを目的としています。 ユーザに与えるべきではありません。

**関連トピック：**

* [アクセス管理について](../../administration/using/about-access-management.md)
* [グループとユーザーの管理](../../administration/using/managing-groups-and-users.md)


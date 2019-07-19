---
title: ワークフローデータの使用
seo-title: ワークフローデータの使用
description: ワークフローデータの使用
seo-description: インポートまたはターゲット設定したデータを使用する様々な可能性について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 3dd66aaa-3a26-4214- b6a0-242c2b7fbc49
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: workflow- general- operation
discoiquuid: 90b250f1- f32d-4256-83ea-4c0627628610
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Using workflow data{#using-workflow-data}

データが識別され準備されたら、次のコンテキストで使用できます。

* **[!UICONTROL Update data]** このアクティビティにより、データベース内のフィールドの一括更新を実行できます。
* **[!UICONTROL Save audience]** アクティビティにより、既存のオーディエンスを更新したり、ワークフローでアップストリームで計算された母集団から新しいオーディエンスを作成したりできます。The audiences created or updated from this activity are **List** or **File** audiences. また、このアクティビティでは、Adobe Experience Cloudオーディエンス/セグメントとしてプロファイルをエクスポートできます。
* **[!UICONTROL Subscription Services]** このアクティビティにより、プロファイルを一括で取得してサービスにサブスクライブしたり、サービスから登録解除したりできます。
* **[!UICONTROL Extract file]** アクティビティでは、Adobe Campaignから外部ファイルの形式でデータを書き出すことができます。

プロファイルターゲットを定義したら、いくつかのアクティビティを使用して配信を作成および送信できます。

* **[!UICONTROL Email delivery]** アクティビティでは、ワークフローでの電子メールの送信を設定できます。This can be a **single send** email and sent just once, or it can be a **recurring** email.
* **[!UICONTROL SMS delivery]** アクティビティでは、ワークフローでのSMSの送信を設定できます。This can be a **single send** SMS and sent just once, or it can be a **recurring** SMS.
* **[!UICONTROL Mobile app delivery]** アクティビティにより、ワークフローでプッシュ通知を送信することができます。This can be a **single send** notification and sent just once, or it can be a **recurring** notification.


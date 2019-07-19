---
title: 内部通知の送信
seo-title: 内部通知の送信
description: 内部通知の送信
seo-description: Adobe Campaignユーザーにリアルタイムシステム通知を送信する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: f196f025- dbb9-4268-9d7d- ff626994b447
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: アプリケーション設定
discoiquuid: 4d51229a-745a-4f24- b1c2-22fa203b499c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Sending internal notifications{#sending-internal-notifications}

Adobe Campaignでは、アプリケーション内で直接重要なシステムアクティビティに関する通知を受信できます。リアルタイム通知は、関連する関係者を保持し、アプリケーション内からアクティビティ通知を即時かつ直接操作できるユーザーに提供します。チームの結果は、キャンペーンの高度性、効率性、スムーズな実行に役立ちます。

![](assets/pulse_3.png)

次のオブジェクトに対する通知を設定できます。

* **[!UICONTROL A/B Test emails]**:電子メール作成者および修飾子は、バリアントが選択された（自動モード）か、バリアントを選択する必要がある（手動モード）ことを通知します。通知をクリックすると、対応する電子メールが表示されます。通知はデフォルトで初期設定のA/Bテストテンプレートにアクティブ化されます。If you want to deactivate them, edit the properties of the email or the email template and uncheck the box located under **General &gt; Notifications**. For more information on A/B Test emails, refer to [Creating an AB Test](../../channels/using/designing-an-a-b-test-email.md). For more on email properties, refer to [List of email properties](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**:ワークフローがエラーになったときに、選択したセキュリティグループの各メンバーに通知が送信されます（電子メールおよびアプリ内通知）。通知または電子メールリンクをクリックすると、対応するワークフローが表示されます。通知はデフォルトで、デフォルトのワークフローテンプレートで非アクティブになります。If you want to activate them, edit the properties of the workflow or workflow template and add a security group under **General &gt; Execution &gt; Error management &gt; Supervisors**. For more information on security groups, refer to [Managing groups and users](../../administration/using/managing-groups-and-users.md). For more on workflow properties, refer to [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties).

   ![](assets/pulse_1.png)


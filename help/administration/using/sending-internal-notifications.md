---
solution: Campaign Standard
product: campaign
title: 内部通知の送信
description: Adobe Campaignユーザーにリアルタイムのシステム通知を送信する方法を説明します。
audience: administration
content-type: reference
topic-tags: application-settings
feature: インスタンス設定
role: 管理者
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 2%

---


# 内部通知の送信{#sending-internal-notifications}

Adobe Campaignを使用すると、重要なシステムアクティビティに関する通知をアプリケーション内で直接受信できます。 リアルタイムの通知により、関連する関係者に通知を受け取り、アプリケーション内からアクティビティ通知に対して即座に直接作動する機能をユーザーに提供します。 チームの成果は、高度な機敏性、効率性、キャンペーンの実行のスムーズさです。

![](assets/pulse_3.png)

次のオブジェクトに関する通知を設定できます。

* **[!UICONTROL A/B Test emails]**:電子メールの作成者と修飾子に、バリアントが選択された（自動モード）か、バリアントを選択する必要がある（手動モード）ことが通知されます。通知をクリックすると、対応する電子メールが表示されます。 通知は、標準のA/Bテストテンプレートでデフォルトでアクティブ化されます。 非アクティブ化する場合は、電子メールまたは電子メールテンプレートのプロパティを編集し、**一般/通知**&#x200B;の下にあるボックスのチェックを外します。 A/Bテスト用電子メールの詳細については、[ABテストの作成](../../channels/using/designing-an-a-b-test-email.md)を参照してください。 電子メールのプロパティについて詳しくは、[電子メールのプロパティのリスト](../../administration/using/configuring-email-channel.md#list-of-email-properties)を参照してください。

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**:選択したセキュリティグループの各メンバーは、ワークフローにエラーが発生した場合に通知（電子メールおよびアプリ内通知）を受け取ります。通知をクリックするか、電子メールリンクをクリックすると、対応するワークフローが表示されます。 デフォルトでは、そのまま使用できるワークフローテンプレートで通知は非アクティブ化されます。 これらをアクティブ化する場合は、ワークフローまたはワークフローテンプレートのプロパティを編集し、**一般>実行>エラー管理>スーパーバイザ**&#x200B;の下にセキュリティグループを追加します。 セキュリティグループの詳細については、[グループとユーザーの管理](../../administration/using/managing-groups-and-users.md)を参照してください。 ワークフローのプロパティについて詳しくは、[ワークフローのプロパティ](../../automating/using/managing-execution-options.md)を参照してください。

   ![](assets/pulse_1.png)

---
title: 内部通知の送信
description: リアルタイムのシステム通知をAdobe Campaignユーザーに送信する方法を説明します
audience: administration
role: Admin
level: Experienced
exl-id: 7e04275a-5413-4f03-b18c-b64ab482d7d5
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# 内部通知の送信{#sending-internal-notifications}

Adobe Campaignは、重要なシステムアクティビティに関する通知を、アプリケーション内で直接受け取ることができます。 リアルタイム通知では、関連する関係者に対する情報を保持し、ユーザーは、アプリケーション内からアクティビティ通知を直接、即座に実行できます。 チームの結果は、高度な俊敏性、効率性、およびキャンペーンのスムーズな実行です。

![](assets/pulse_3.png)

次のオブジェクトの通知を設定できます。

* **[!UICONTROL A/B Test emails]**:e メールの作成者と修飾子に、バリアントが選択された（自動モード）か、バリアントを選択する必要がある（手動モード）ことが通知されます。 通知をクリックすると、対応する E メールが表示されます。 標準の A/B テストテンプレートでは、通知はデフォルトでアクティブ化されます。 これらを非アクティブ化する場合は、E メールまたは E メールテンプレートのプロパティを編集し、以下にあるボックスのチェックを外します。 **一般/通知**. A/B テスト用 E メールについて詳しくは、 [AB テストの作成](../../channels/using/designing-an-a-b-test-email.md). E メールのプロパティについて詳しくは、 [E メールプロパティのリスト](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**:選択したセキュリティグループの各メンバーには、ワークフローにエラーが発生するたびに通知が送信されます（電子メールとアプリ内通知）。 通知または E メールのリンクをクリックすると、対応するワークフローが表示されます。 そのまま使用できるワークフローテンプレートでは、デフォルトで通知は非アクティブになっています。 これらをアクティブ化する場合は、ワークフローまたはワークフローテンプレートのプロパティを編集し、以下にセキュリティグループを追加します。 **「一般」>「実行」>「エラー管理」>「スーパーバイザー」**. セキュリティグループの詳細については、 [グループとユーザーの管理](../../administration/using/managing-groups-and-users.md). ワークフローのプロパティについて詳しくは、 [ワークフローのプロパティ](../../automating/using/managing-execution-options.md).

   ![](assets/pulse_1.png)

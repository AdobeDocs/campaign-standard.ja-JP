---
title: 内部通知の送信
description: Adobe Campaign ユーザーにリアルタイムシステム通知を送信する方法を説明します
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

Adobe Campaignでは、重要なシステムアクティビティに関する通知をアプリケーション内で直接受け取ることができます。 リアルタイム通知は、関連する関係者に情報を提供し、ユーザーがアプリケーション内からアクティビティ通知に対して直ちに直接行動できるようにします。 チームの結果として、キャンペーンの高度な俊敏性、効率、スムーズな実行が実現します。

![](assets/pulse_3.png)

通知は、次のオブジェクトに対して設定できます。

* **[!UICONTROL A/B Test emails]**：メールの作成者と修飾子には、バリアントが選択された（自動モード）か、バリアントを選択する必要がある（手動モード）ことが通知されます。 通知をクリックすると、対応するメールが表示されます。 通知は、標準の A/B テスト テンプレートでデフォルトで有効になっています。 これらを非アクティブにする場合は、メールまたはメールテンプレートのプロパティを編集し、**一般/通知** にあるボックスのチェックを外します。 A/B テストのメールについて詳しくは、[AB テストの作成 ](../../channels/using/designing-an-a-b-test-email.md) を参照してください。 メールプロパティについて詳しくは、[ メールプロパティのリスト ](../../administration/using/configuring-email-channel.md#list-of-email-properties) を参照してください。

  ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**：選択したセキュリティグループの各メンバーには、ワークフローでエラーが発生するたびに通知（メールおよびアプリ内通知）が送信されます。 通知またはメールリンクをクリックすると、対応するワークフローが表示されます。 標準のワークフローテンプレートでは、通知はデフォルトで非アクティブになります。 ワークフローをアクティブ化する場合は、ワークフローまたはワークフローテンプレートのプロパティを編集し、**一般/実行/エラー管理/スーパーバイザー** の下にセキュリティグループを追加します。 セキュリティグループについて詳しくは、[ グループとユーザーの管理 ](../../administration/using/managing-groups-and-users.md) を参照してください。 ワークフローのプロパティについて詳しくは、「[ ワークフローのプロパティ ](../../automating/using/managing-execution-options.md)」を参照してください。

  ![](assets/pulse_1.png)

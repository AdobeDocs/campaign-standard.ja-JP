---
title: 内部通知の送信
description: Adobe Campaignユーザーにリアルタイムのシステム通知を送信する方法について説明します。
page-status-flag: 非活性化の
uuid: f196f025-dbb9-4268-9d7d-ff626994b447
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: application-settings
discoiquuid: 4d51229a-745a-4f24-b1c2-22fa203b499c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 内部通知の送信{#sending-internal-notifications}

Adobe Campaignを使用すると、重要なシステムアクティビティに関する通知をアプリケーション内で直接受信できます。  リアルタイム通知は、関連する関係者に通知を受け、ユーザーに対して、アプリケーション内からアクティビティ通知に対して即座に直接対応する機能を提供します。 チームの成果は、高度な機敏性、効率性、キャンペーンのスムーズな実行です。

![](assets/pulse_3.png)

次のオブジェクトに対する通知を設定できます。

* **[!UICONTROL A/B Test emails]**:電子メールの作成者と修飾子に、バリアントが選択された（自動モード）か、バリアントを選択する必要がある（手動モード）ことが通知されます。 通知をクリックすると、対応する電子メールが表示されます。 デフォルトでは、そのまま使用できるA/Bテストテンプレートで通知がアクティブ化されます。 非アクティブ化する場合は、電子メールまたは電子メールテンプレートのプロパティを編集し、一般/通知の下にあるボックス **のチェックを外します**。 A/Bテスト電子メールの詳細については、「ABテストの作成」 [を参照してください](../../channels/using/designing-an-a-b-test-email.md)。 電子メールのプロパティについて詳しくは、「電子メールのプ [ロパティのリスト」を参照してくださ](../../administration/using/configuring-email-channel.md#list-of-email-properties)い。

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**:選択したセキュリティグループの各メンバーは、ワークフローにエラーが発生した場合は常に通知されます（電子メールおよびアプリ内通知）。 通知をクリックするか、電子メールリンクをクリックすると、対応するワークフローが表示されます。 デフォルトでは、そのまま使用できるワークフローテンプレートで通知が非アクティブ化されます。 これらをアクティブ化する場合は、ワークフローまたはワークフローテンプレートのプロパティを編集し、一般/実行/エラー管理/スーパーバイザ **ーの下にセキュリティグループを追加します**。 セキュリティグループの詳細については、「グループとユーザ [ーの管理」を参照してくださ](../../administration/using/managing-groups-and-users.md)い。 ワークフローのプロパティについて詳しくは、「ワークフローのプロパ [ティ」を参照してくださ](../../automating/using/executing-a-workflow.md#workflow-properties)い。

   ![](assets/pulse_1.png)


---
solution: Campaign Standard
product: campaign
title: 内部通知の送信
description: リアルタイムのシステム通知をAdobe Campaignユーザーに送信する方法を説明します。
audience: administration
content-type: reference
topic-tags: application-settings
feature: インスタンス設定
role: Admin
level: Experienced
exl-id: 7e04275a-5413-4f03-b18c-b64ab482d7d5
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 2%

---

# 内部通知の送信{#sending-internal-notifications}

Adobe Campaignは、重要なシステムアクティビティに関する通知をアプリケーション内で直接受け取る可能性を提供します。 リアルタイム通知では、関連する関係者に通知が届き、ユーザーは、アプリケーション内からアクティビティ通知に即座に直接対応できます。 チームの成果は、高度な俊敏性、効率性、キャンペーンの実行のスムーズ化です。

![](assets/pulse_3.png)

次のオブジェクトに対する通知を設定できます。

* **[!UICONTROL A/B Test emails]**:eメールの作成者と修飾子に、バリアントが選択された（自動モード）か、バリアントを選択する必要がある（手動モード）ことが通知されます。通知をクリックすると、対応するEメールが表示されます。 通知は、標準のA/Bテストテンプレートでデフォルトで有効化されます。 非アクティブ化する場合は、EメールまたはEメールテンプレートのプロパティを編集し、**一般/通知**&#x200B;の下にあるボックスのチェックを外します。 A/Bテスト用Eメールの詳細については、[ABテストの作成](../../channels/using/designing-an-a-b-test-email.md)を参照してください。 Eメールのプロパティについて詳しくは、[Eメールのプロパティのリスト](../../administration/using/configuring-email-channel.md#list-of-email-properties)を参照してください。

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**:選択したセキュリティグループの各メンバーは、ワークフローにエラーが発生するたびに通知（電子メールおよびアプリ内通知）を受け取ります。通知またはEメールリンクをクリックすると、対応するワークフローが表示されます。 通知は、デフォルトの標準のワークフローテンプレートで、デフォルトで非アクティブになっています。 これらをアクティブ化する場合は、ワークフローまたはワークフローテンプレートのプロパティを編集し、**一般/実行/エラー管理/スーパーバイザー**&#x200B;の下にセキュリティグループを追加します。 セキュリティグループの詳細については、[グループとユーザーの管理](../../administration/using/managing-groups-and-users.md)を参照してください。 ワークフローのプロパティについて詳しくは、[ワークフローのプロパティ](../../automating/using/managing-execution-options.md)を参照してください。

   ![](assets/pulse_1.png)

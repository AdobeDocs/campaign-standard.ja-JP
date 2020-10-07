---
title: 配達確認の送信
description: 配達確認の送信方法を説明します。
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 100%

---


# 配達確認の送信 {#sending-proofs}

## 配達確認について {#about-proofs}

配達確認は、メッセージをメインターゲットに送信する前にテストするための特別なメッセージです。配達確認の受信者は、メッセージ（内容と形式）の承認をおこないます。

配達確認の受信者には 2 種類あります。

* **テストプロファイル**：定義されたターゲット条件に一致しない追加の受信者をターゲットにできます。

   これをメッセージのオーディエンスに追加して、受信者データベースの不正使用を検出したり、E メールが確実に届くようにすることができます。詳しくは、[テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

   >[!NOTE]
   >
   >配達確認を送信するには、テストプロファイルをメッセージのオーディエンスに含める必要があります。

* **代替プロファイル**&#x200B;を使用すると、ターゲットプロファイルのいずれかの位置に自分を配置し、プロファイルが受け取るメッセージを正確に表示できます。詳しくは、[ターゲットプロファイルを使用した電子メールメッセージのテスト](../../sending/using/testing-messages-using-target.md)を参照してください。

   >[!NOTE]
   >
   >この機能は、E メールチャネルでのみ使用できます。

## 配達確認の送信 {#sending-a-proof}

配達確認を送信するには、次の手順に従います。

1. 配達確認受信者が設定されていることを確認します。
   * メッセージのオーディエンスに&#x200B;**テストプロファイル**&#x200B;を含める必要があります。
   * メッセージの準備が完了したら、**代替プロファイル**&#x200B;を追加する必要があります（[この節](../../sending/using/testing-messages-using-target.md)を参照）。

1. 「**[!UICONTROL Send a test]**」ボタンをクリックします。

   ![](assets/bat_select.png)

1. 使用する配達確認の種類を選択します。

   * **[!UICONTROL Email rendering]**：このオプションは、ターゲットのインボックスに応じてメッセージを受信する方法をテストする場合に選択します。詳しくは、[E メールのレンダリング](../../sending/using/email-rendering.md)を参照してください。
   * **[!UICONTROL Proof]**：このオプションは、メッセージをメインターゲットに送信する前にテストする場合に選択します。配達確認受信者は、配信の内容と形式の両方を確認して、承認をおこないます。
   * **[!UICONTROL Proof + Email rendering]**：このオプションは、前の 2 つのオプションを組み合わせたものです。

   ![](assets/bat_select1.png)

   >[!NOTE]
   >
   >E メールのレンダリングは、テストプロファイルでのみ使用できます。メッセージにテストプロファイルが追加されていない場合、選択できるのは「**[!UICONTROL Proof]**」オプションのみです。

1. 選択内容を確認します。

   配達確認は、設定された受信者に送信されます。

   ![](assets/bat_select2.png)

1. 「**[!UICONTROL Proofs]**」ドロップダウンリストを使用して、配達確認を表示できます。

   ![](assets/bat_view.png)

1. 概要にアクセスする配達確認を選択します。E メールの場合、配達確認タイプとして「**E メールのレンダリング**」オプションを選択した場合は、配達確認ラベルの右側に「**[!UICONTROL Access email rendering]**」アイコンが表示されます。[E メールのレンダリング](../../sending/using/email-rendering.md)を参照してください。

   ![](assets/bat_view2.png)

配達確認を受け取った人からのコメントに応じて、配信のコンテンツを変更するように求められる場合があります。変更がおこなわれたら、E メールの準備を一からやり直し、配達確認を再送信する必要があります。新しい各配達確認は、「**[!UICONTROL Show proofs]**」ボタンを使用してアクセスできます。

配信のコンテンツが完成するまで、必要な数の配達確認を送信する必要があります。この操作が完了したら、配信をメインターゲットに送信し、承認サイクルを終了することができます。

## 配達確認の件名行の設定 {#configuring-proofs-subject-line}

配達確認を送信すると、件名行にはデフォルトで&#x200B;**「配達確認」**&#x200B;プレフィックスと、配達確認の番号を示すカウンターが設定されます。

![](assets/proof-prefix.png)

使用するデフォルトの件名行を変更するには、次の手順に従います。

1. メッセージダッシュボードで、「**[!UICONTROL Open properties]**」ボタンをクリックします。
1. 「**[!UICONTROL Advanced parameters]**」セクションで、件名行にデフォルトで使用するプレフィックスを定義します。

件名行で配達確認の番号を非表示にするには、「**[!UICONTROL Hide proof prefix counter]**」オプションを有効にします。

>[!NOTE]
>
>配達確認のプレフィックス全体を非表示にする場合は、「**[!UICONTROL Subject line prefix]**」フィールドを空白のままにします。

![](assets/proof-prefix-configuration.png)

1. 「**[!UICONTROL Confirm]**」をクリックします。この設定は、デフォルトで、選択したメッセージに対して送信されるすべての配達確認に適用されます。

**関連トピック：**

* [テストの送信、E メールの準備と送信](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html)（ビデオ）
* [ターゲットプロファイルを使用した E メールメッセージのテスト](../../sending/using/testing-messages-using-target.md)
* [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)
* [メッセージのプレビュー](../../sending/using/previewing-messages.md)
* [E メールチャネルの設定](../../administration/using/configuring-email-channel.md)

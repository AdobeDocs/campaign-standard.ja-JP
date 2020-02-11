---
title: 配達確認の送信
description: 校正を送信する方法を説明します。
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff9d0c3ca42606f097a34b1835d285541061e57b

---


# 配達確認の送信 {#sending-proofs}

配達確認は、メインターゲットにメッセージを送信する前に、メッセージをテストできる特定のメッセージです。

証明の受信者は、メッセージ（内容とフォーム）の承認を担当します。 これらはテストプロファイルで **定義されます**。 詳しくは、テストプロファイルの管 [理を参照してください](../../audiences/using/managing-test-profiles.md)。

証明を送信するには、テストプロファイルをメッセージのオーディエンスに含める必要があります。

メッセージ内：

1. ボタンをクリッ **[!UICONTROL Send a test]** クします。

   ![](assets/bat_select.png)

1. 使用する校正の種類を選択します。

   * **[!UICONTROL Email rendering]**:対象となるインボックスに従ってメッセージを受信する方法をテストする場合は、このオプションを選択します。 詳しくは、電子メールのレンダリングを参 [照してください](../../sending/using/email-rendering.md)。
   * **[!UICONTROL Proof]**:メインターゲットにメッセージを送信する前にメッセージをテストする場合は、このオプションを選択します。 配達確認の受信者は、コンテンツと形式の両方を確認して、配信を承認する責任を負います。
   * **[!UICONTROL Proof + Email rendering]**:このオプションは、前の2つのオプションを組み合わせます。
   ![](assets/bat_select1.png)

1. 選択を確認します。

   校正がテストプロファイルに送信されます。

   ![](assets/bat_select2.png)

1. ドロップダウンリストを使用して、校正 **[!UICONTROL Proofs]** を表示することができます。

   ![](assets/bat_view.png)

1. 概要にアクセスする校正を選択します。 電子メールの場合、校正タイプとして「電子メー **ルレンダリング** 」オプションを選択した場合は **[!UICONTROL Access email rendering]** 、校正ラベルの右側にアイコンが表示されます。 電子メール [レンダリングを参照](../../sending/using/email-rendering.md)。

   ![](assets/bat_view2.png)

配達確認を受け取った人からのコメントに応じて、配信のコンテンツを変更するように求められる場合があります。 変更が行われたら、電子メールの準備を再開し、証明を再送信する必要があります。 各新しい校正には、ボタンを使用してアクセスで **[!UICONTROL Show proofs]** きます。

配信内容が完成するまで、必要な数の証明書を送信する必要があります。 この処理が完了したら、配信をメインターゲットに送信し、承認サイクルを閉じることができます。

**関連トピック：**

[テストの送信、電子メールビデオの準備と送信](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html) 。

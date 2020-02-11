---
title: テストプロファイルの管理
description: テストプロファイルの管理方法を説明します。
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


# テストプロファイルの管理 {#managing-test-profiles}

## テストプロファイルについて {#about-test-profiles}

テストプロファイルを使用すると、定義したターゲット条件に一致しない追加の受信者をターゲットに設定できます。 受信者データベースの不正使用を検出したり、電子メールが受信トレイに確実に届くように、メッセージのオーディエンスに追加されます。

テストプロファイルは、アドバンスメニューから管理できま **[!UICONTROL Profiles & audiences > Test profiles]**&#x200B;す。

テストプロファイルには架空の連絡先情報、または送信者によって制御される連絡先情報が含まれ、次のコンテキストでメッセージで使用できます。

* 校正を送 **信する**:配達確認は、受信者に確定された配信を送信する前にメッセージを確認するために使用される特定のメッセージです。 配信の内容と形式に関して、校正テストプロファイルが配信を確認します。 詳しくは、 [校正の送信を参照してくださ](../../sending/using/sending-proofs.md)い。
* 電子メー **ルレンダリング**:電子メールレンダリングテストプロファイルは、メッセージを受信したメッセージインボックスに従ってメッセージが表示される方法を確認するために使用されます。 例えば、Webメール、メッセージサービス、モバイルなど。 電子メール [レンダリングを参照](../../sending/using/email-rendering.md)。

   電子メ **ールレンダリング** (Email rendering use)は読み取り専用です。 この使用を使用したテストプロファイルは、Adobe Campaignの標準でのみ使用できます。

* トラッ **プ**:メッセージは、メインターゲットに送信されるのと同じように、テストプロファイルに送信されます。 トラップの [使用を参照してください](../../sending/using/using-traps.md)。
* メッセージ **をプレビューするには** 、次の手順に従います。メッセージをプレビューする際にテストプロファイルを選択して、パーソナライゼーション要素をテストできます。 詳しくは、メッ [セージのプレビューを参照してくださ](/help/sending/using/previewing-messages.md)い。

![](assets/test_profile.png)

## テストプロファイルの作成 {#creating-test-profiles}

1. アドバンスメニューのAdobe Campaignロゴから、 **Profiles &amp; audiences/Test profilesを選択して、テストプロファイルのリストにア** クセスします。

   ![](assets/test_profile_creation_1.png)

1. ダッシュボード **[!UICONTROL Test profiles]** で「作成」をクリ **ックしま**&#x200B;す。

   ![](assets/test_profile_creation_2.png)

1. このプロファイルのデータを入力します。

   ![](assets/test_profile_creation_3.png)

1. テストプロファイルに使用する用途を選択します。

   ![](assets/test_profile_creation_4.png)

1. 必要に応じて、連絡先チ **[!UICONTROL Email, Telephone, Mobile, Mobile app]**&#x200B;ャネルとテストプロファイルのアドレスを入力します。

   >[!NOTE]
   >
   >好みの電子メール形式を定義できます。ま **[!UICONTROL Text]** た **[!UICONTROL HTML]**&#x200B;は

1. このテストプロファイルをトランザクションメッセージのパーソナライゼーションのテストに使用する場合は、イベントタイプとこのイベントのデータを指定します。
1. をクリック **[!UICONTROL Create]** して、テストプロファイルを保存します。

次に、テストプロファイルがプロファイルのリストに追加されます。

**関連トピック：**

[テストプロファイルビデオの作成](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/test-profiles.html) （英語のみ）

## テストプロファイルの編集 {#editing-test-profiles}

テストプロファイルを編集し、そのプロファイルにリンクされているデータを参照する、または変更するには：

1. 画像をクリックして、編集するテストプロファイルを選択します。
1. フィールドを参照または変更します。

   ![](assets/test_profile_edit.png)

1. 変更を **[!UICONTROL Save]** 入力した場合は、をクリックします。または、画面上部のセクションでテストプロファイルの名前を選択し、テストプロ **[!UICONTROL Test profiles]** ファイルダッシュボードに戻ります。

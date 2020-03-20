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
source-git-commit: 767d4233236019213003961aae1abb317198e581

---


# テストプロファイルの管理 {#managing-test-profiles}

## テストプロファイルについて {#about-test-profiles}

テストプロファイルを使用すると、定義したターゲット条件に一致しない追加の受信者をターゲットに設定できます。 受信者データベースの不正な使用を検出したり、電子メールが受信トレイに確実に届くように、メッセージのオーディエンスに追加されます。

テストプロファイルは、アドバンスメニューから管理できま **[!UICONTROL Profiles & audiences > Test profiles]**&#x200B;す。

テストプロファイルには、架空の連絡先情報、または送信者によって制御される連絡先情報が含まれており、次のコンテキストでメッセージ内で使用できます。

* 校正を送 **信する**:配達確認は、受信者に最終的な配信を送信する前にメッセージを確認するために使用される特定のメッセージです。 配信の内容と形式に関して、配信の確認は、校正テストプロファイルが担当します。 詳しくは、 [校正の送信を参照してくださ](../../sending/using/sending-proofs.md)い。
* 電子メー **ルのレンダリング**:電子メールレンダリングテストプロファイルは、メッセージを受信したメッセージインボックスに従ってメッセージがどのように表示されるかを確認するために使用されます。 例えば、Webメール、メッセージサービス、モバイルなど。 電子メールの [レンダリングを参照](../../sending/using/email-rendering.md)。

   電子メー **ルのレンダリング** (Email rendering use)は読み取り専用です。 この使用によるテストプロファイルは、Adobe Campaignの標準でのみ使用できます。

* トラップと **して**:メッセージは、メインターゲットに送信されるのと同じように、テストプロファイルに送信されます。 トラップの使 [用を参照してくださ](../../sending/using/using-traps.md)い。
* メッセージ **をプレビューする** には：メッセージをプレビューする際にテストプロファイルを選択し、パーソナライゼーション要素をテストできます。 メッセージのプ [レビューを参照してくださ](/help/sending/using/previewing-messages.md)い。

![](assets/test_profile.png)

## テストプロファイルの作成 {#creating-test-profiles}

1. アドバンスメニューのAdobe Campaignロゴから、 **Profiles &amp; audiences/Test profilesを選択して** 、テストプロファイルのリストにアクセスします。

   ![](assets/test_profile_creation_1.png)

1. ダッシュボード **[!UICONTROL Test profiles]** で、「作成」をクリ **ックしま**&#x200B;す。

   ![](assets/test_profile_creation_2.png)

1. このプロファイルのデータを入力します。

   ![](assets/test_profile_creation_3.png)

1. テストプロファイルに使用する用途を選択します。

   ![](assets/test_profile_creation_4.png)

1. 必要に応じて、連絡先チ **[!UICONTROL Email, Telephone, Mobile, Mobile app]**&#x200B;ャネルとテストプロファイルの住所を入力します。

   >[!NOTE]
   >
   >次のように、好みの電子メール形式を定義できます。ま **[!UICONTROL Text]** た **[!UICONTROL HTML]**&#x200B;は

1. トランザクションメッセージのパーソナライゼーションのテストにこのテストプロファイルを使用する場合は、イベントタイプとこのイベントのデータを指定します。
1. をクリック **[!UICONTROL Create]** して、テストプロファイルを保存します。

その後、テストプロファイルがプロファイルのリストに追加されます。

**関連トピック：**

[テストプロファイルビデオの作成](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/test-profiles.html) （英語）

## テストプロファイルの編集 {#editing-test-profiles}

テストプロファイルを編集し、そのプロファイルにリンクされているデータを参照するか、変更するには：

1. 画像をクリックして、編集するテストプロファイルを選択します。
1. フィールドを確認または変更します。

   ![](assets/test_profile_edit.png)

1. 変更を **[!UICONTROL Save]** 入力した場合は、をクリックします。または、画面の上部にあるセクションでテストプロファイルの名前を選択し、テス **[!UICONTROL Test profiles]** トプロファイルのダッシュボードに戻ります。

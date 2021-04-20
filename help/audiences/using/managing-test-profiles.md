---
solution: Campaign Standard
product: campaign
title: テストプロファイルの管理
description: テストプロファイルを管理する方法を説明します。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Profiles
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 95%

---


# テストプロファイルの管理 {#managing-test-profiles}

## テストプロファイルについて {#about-test-profiles}

テストプロファイルを使用すると、定義済みのターゲティング条件に一致しない追加の受信者をターゲットにすることができます。テストプロファイルは、受信者データベースの不正使用を検出したり、E メールがインボックスに確実に届くようにしたりするために、メッセージのオーディエンスに追加されます。

![](assets/do-not-localize/how-to-video.png) [この機能をビデオで確認](#video)

テストプロファイルは、アドバンスメニュー&#x200B;**[!UICONTROL Profiles & audiences > Test profiles]**&#x200B;から管理できます。

テストプロファイルには架空の連絡先情報または送信者が制御できる連絡先情報が含まれています。その情報をメッセージで使用できるコンテキストは次のいずれかです。

* **配達確認**&#x200B;の送信のため：配達確認は、受信者に最終的な配信を送信する前にメッセージを確認するための特定のメッセージです。配達確認テストプロファイルには、配信の内容や形式をチェックする役割があります。詳しくは、[配達確認の送信](../../sending/using/sending-proofs.md)を参照してください。
* **E メールのレンダリング**&#x200B;のため：E メールレンダリングテストプロファイルは、メッセージを受信したメッセージインボックスに応じたメッセージの表示方法を確認するために使用します。例えば、Web メール、メッセージサービス、モバイルなどです。[E メールのレンダリング](../../sending/using/email-rendering.md)を参照してください。

   **E メールレンダリング**&#x200B;の使用は読み取り専用です。Adobe Campaign でそのまま使用できるのは、この用途のテストプロファイルのみです。

* **トラップ**&#x200B;として：メッセージは、メインターゲットに送信される場合と同じように、テストプロファイルに送信されます。[トラップの使用](../../sending/using/using-traps.md)を参照してください。
* メッセージの&#x200B;**プレビュー**&#x200B;のため：メッセージのプレビュー時にテストプロファイルを選択して、パーソナライゼーション要素をテストできます。[メッセージのプレビュー](/help/sending/using/previewing-messages.md)を参照してください。

![](assets/test_profile.png)

## テストプロファイルの作成 {#creating-test-profiles}

1. Adobe Campaign のロゴをクリックし、詳細設定メニューから **Profiles &amp; audiences／Test profiles** を選択して、テストプロファイルのリストにアクセスします。

   ![](assets/test_profile_creation_1.png)

1. **[!UICONTROL Test profiles]**&#x200B;ダッシュボードで、「**Create**」をクリックします。

   ![](assets/test_profile_creation_2.png)

1. このプロファイルに関するデータを入力します。

   ![](assets/test_profile_creation_3.png)

1. テストプロファイルの用途を選択します。

   ![](assets/test_profile_creation_4.png)

1. 必要に応じて、配信チャネル（**[!UICONTROL Email, Telephone, Mobile, Mobile app]**）とテストプロファイルのアドレスを入力します。

   >[!NOTE]
   >
   >望ましい E メールフォーマットを「**[!UICONTROL Text]**」か「**[!UICONTROL HTML]**」のいずれかで指定できます。

1. このテストプロファイルをトランザクションメッセージのパーソナライゼーションのテストに使用する場合は、このイベントのイベントタイプとデータを指定します。
1. 「**[!UICONTROL Create]**」をクリックして、テストプロファイルを保存します。

このテストプロファイルがプロファイルのリストに追加されます。

## テストプロファイルの編集 {#editing-test-profiles}

テストプロファイルを編集したり、テストプロファイルにリンクされているデータを参照または変更するには、次の手順に従います。

1. 編集するテストプロファイルを、画像をクリックして選択します。
1. フィールドを参照または変更します。

   ![](assets/test_profile_edit.png)

1. 変更内容を入力した場合は、「**[!UICONTROL Save]**」をクリックします。または、テストプロファイルの名前を選択した後、画面上部のセクションで「**[!UICONTROL Test profiles]**」を選択して、テストプロファイルダッシュボードに戻ります。

## チュートリアルビデオ {#video}

このビデオでは、テストプロファイルの作成方法を紹介します。

>[!VIDEO](https://video.tv.adobe.com/v/24094?quality=12)

追加のCampaign Standardハウツービデオは[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)で参照できます。

---
title: メールのレンダリング
description: メールのレンダリング機能を学習します。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: 31f4e557-55b3-4bf5-8d5d-9d412b7670a6
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 79%

---

# メールのレンダリング{#email-rendering}

「**[!UICONTROL Send]**」ボタンを押す前に、さまざまな Web クライアント、Web メールおよびデバイスでメッセージの表示が最適化されていることを確認してください。

この確認のために、Adobe Campaign ではレンダリングをキャプチャして専用のレポートで利用できるようにしています。これにより、異なるコンテキストで受信される可能性のある送信済みのメッセージをプレビューできます。

Adobe Campaign の「**メールのレンダリング**」で使用できるモバイル、メッセージングおよび Web メールクライアントは、Litmus の [Web サイト](https://litmus.com/email-testing)に記載されています（「**View all email clients**」をクリックしてください）。

## E メールのレンダリングの生成 {#checking-the-email-rendering-report}

メール配信を作成し、そのコンテンツとターゲット母集団を定義したら、以下の手順に従います。

1. 「**Audience**」をクリックして「**[!UICONTROL Test profiles]**」タブにアクセスします。

   ![](assets/email_rendering_05.png)

1. クエリエディターを使用して、「**メールのレンダリング**」用のテストプロファイルなど、使用するテストプロファイルを定義します。[テストプロファイル](../../audiences/using/managing-test-profiles.md)についてを参照してください。

   ![](assets/email_rendering_06.png)

1. クエリを確認して、変更を保存します。
1. アクションバーの「**[!UICONTROL Test]**」ボタンをクリックします。

   ![](assets/email_rendering_07.png)

1. この「**[!UICONTROL Email rendering]**」オプションを選択し、「**[!UICONTROL OK]**」をクリックします。

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >この「**[!UICONTROL Proof + Email rendering]**」オプションを使用すると、配達確認を送信し、メールのレンダリング機能を同時に使用できます。メッセージを配達確認の受信者に承認してもらうと同時に、対象となる受信トレイに応じてメッセージの受信方法をテストできます。この場合は、配達確認テストプロファイルも選択する必要があります。[テストプロファイル](../../audiences/using/managing-test-profiles.md)についてを参照してください。

   テスト配信が送信されます。

1. メッセージの送信後、数分後にレンダリングのサムネールが使用可能になります。これらにアクセスするには、「**[!UICONTROL Summary]**」ドロップダウンリストの「**[!UICONTROL Proofs]**」を選択します。

   ![](assets/email_rendering_03.png)

1. 「**[!UICONTROL Proofs]**」リストで、「**[!UICONTROL Access email rendering]**」アイコンをクリックします。

   ![](assets/email_rendering_04.png)

専用のメールのレンダリングレポートが表示されます。[メールのレンダリングレポートの説明](#email-rendering-report-description)を参照してください。

**関連トピック**：

* [メールの作成](../../channels/using/creating-an-email.md)
* [配達確認の送信](../../sending/using/sending-proofs.md)
* [クエリエディター](../../automating/using/editing-queries.md#about-query-editor)

## E メールのレンダリングレポート {#email-rendering-report-description}

このレポートは、受信者に表示されるメールのレンダリングを示します。メールのレンダリングは、ブラウザー、モバイルデバイス、メールアプリケーションなど、受信者がどの方法でメール配信を開くかによって異なります。

### E メールレンダリングトークン

使用できるレンダリングの数は、ライセンス契約に記載されています。各配信に **E メールのレンダリング** 「 」を有効にすると、使用可能なレンダリング（トークン）の数が 1 つ減ります。

トークンは、E メールのレンダリングレポート全体ではなく、個々のレンダリングを考慮します。つまり、

* **毎回** E メールのレンダリングレポートが生成され、メッセージングクライアントごとに 1 つのトークンが差し引かれます。Outlook 2000 レンダリング用のトークンと、Outlook レンダリング用のトークン、Apple Mail レンダリング用のトークンなどです。

* **同じ配信に対して**&#x200B;を生成した場合は、使用可能なトークンの数が、生成したレンダリングの数だけ再び減ります。

### レポートサマリ

レポート概要には、受信済みメッセージ、不要なメッセージ（スパム）、受信されていないメッセージまたは受信が保留されているメッセージの数が表示されます。

![](assets/inbox_rendering_report.png)

レポートは、3 つの部分に分かれています：**[!UICONTROL Mobile]**、**[!UICONTROL Messaging clients]**、および **[!UICONTROL Webmails]**。レポートを下へスクロールすると、これらの 3 つのカテゴリにグループ化されたすべてのレンダリングが表示されます。

![](assets/inbox_rendering_report_3.png)

各レポートの詳細を表示するには、対応するカードをクリックします。選択した受信方法のレンダリングが表示されます。

![](assets/inbox_rendering_report_2.png)

この「**[!UICONTROL Technical data]**」タブでは、メールの受信日や取得日、完全なヘッダーなどの詳細情報を取得できます。

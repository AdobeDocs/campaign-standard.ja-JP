---
title: E メールのレンダリング
description: E メールレンダリング機能を学習します。
page-status-flag: never-activated
uuid: c423e237-ad39-4797-ac3a-4320894a8f99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 2b5b13c8-2e51-4985-a161-c1d7f0fc32b4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3af649cfaae195ae5e75406ca3a0743b9b1f65d2
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 91%

---


# E メールのレンダリング{#email-rendering}

「**[!UICONTROL Send]**」ボタンを押す前に、さまざまな Web クライアント、Web メールおよびデバイスでメッセージの表示が最適化されていることを確認してください。

この確認のために、Adobe Campaign ではレンダリングをキャプチャして専用のレポートで利用できるようにしています。これにより、異なるコンテキストで受信される可能性のある送信済みのメッセージをプレビューできます。

Adobe Campaign の「**E メールのレンダリング**」で使用できるモバイル、メッセージングおよび Web メールクライアントは、Litmus の [Web サイト](https://litmus.com/email-testing)に記載されています（「**View all email clients**」をクリックしてください）。

## E メールのレンダリングレポートの確認{#checking-the-email-rendering-report}

E メール配信を作成し、そのコンテンツとターゲット母集団を定義したら、以下の手順に従います。

1. 「**Audience**」をクリックして「**[!UICONTROL Test profiles]**」タブにアクセスします。

   ![](assets/email_rendering_05.png)

1. クエリエディターを使用して、「**E メールのレンダリング**」用のテストプロファイルなど、使用するテストプロファイルを定義します。[テストプロファイル](../../audiences/using/managing-test-profiles.md)についてを参照してください。

   ![](assets/email_rendering_06.png)

1. クエリを確認して、変更を保存します。
1. アクションバーの「**[!UICONTROL Test]**」ボタンをクリックします。

   ![](assets/email_rendering_07.png)

1. この「**[!UICONTROL Email rendering]**」オプションを選択し、「**[!UICONTROL OK]**」をクリックします。

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >この「**[!UICONTROL Proof + Email rendering]**」オプションを使用すると、配達確認を送信し、E メールのレンダリング機能を同時に使用できます。メッセージを配達確認の受信者に承認してもらうと同時に、対象となる受信トレイに応じてメッセージの受信方法をテストできます。この場合は、配達確認テストプロファイルも選択する必要があります。[テストプロファイル](../../audiences/using/managing-test-profiles.md)についてを参照してください。

   テスト配信が送信されます。

1. メッセージの送信後、数分後にレンダリングのサムネールが使用可能になります。これらにアクセスするには、「**[!UICONTROL Summary]**」ドロップダウンリストの「**[!UICONTROL Proofs]**」を選択します。

   ![](assets/email_rendering_03.png)

1. 「**[!UICONTROL Proofs]**」リストで、「**[!UICONTROL Access email rendering]**」アイコンをクリックします。

   ![](assets/email_rendering_04.png)

専用の E メールのレンダリングレポートが表示されます。[E メールのレンダリングレポートの説明](#email-rendering-report-description)を参照してください。

**関連トピック**：

* [E メールの作成](../../channels/using/creating-an-email.md)
* [配達確認の送信](../../sending/using/sending-proofs.md)
* [クエリエディター](../../automating/using/editing-queries.md#about-query-editor)

## E メールのレンダリングレポートの説明{#email-rendering-report-description}

このレポートは、受信者に表示される E メールのレンダリングを示します。E メールのレンダリングは、ブラウザー、モバイルデバイス、メールアプリケーションなど、受信者がどの方法で E メール配信を開くかによって異なります。

>[!NOTE]
>
>使用できるレンダリングの数は、ライセンス契約に記載されています。「**E メールのレンダリング**」が有効な配信ごとに、使用可能なレンダリング（トークン）の数が 1 つ減ります。
>
>トークンは、電子メールレンダリングレポート全体ではなく、個々のレンダリングごとに割り当てられます。つまり、次のような意味です。
>
>**受信ボックスレンダリングレポートが生成されるたびに、メッセージングクライアントあたり 1 つのトークンが差し引かれます（Outlook 2000 レンダリングに 1 トークン、Outlook レンダリングに 1 トークン、Apple Mail レンダリングに 1 トークン、というようになります）。**
>
>**同じ配信の場合**、電子メールレンダリングを再び生成すると、使用可能なトークン数は、生成されたレンダリングの数だけ再度減少します。


レポート概要には、受信済みメッセージ、不要なメッセージ（スパム）、受信されていないメッセージまたは受信が保留されているメッセージの数が表示されます。

![](assets/inbox_rendering_report.png)

レポートは、3 つの部分に分かれています：**[!UICONTROL Mobile]**、**[!UICONTROL Messaging clients]**、および **[!UICONTROL Webmails]**。レポートを下へスクロールすると、これらの 3 つのカテゴリにグループ化されたすべてのレンダリングが表示されます。

![](assets/inbox_rendering_report_3.png)

各レポートの詳細を表示するには、対応するカードをクリックします。選択した受信方法のレンダリングが表示されます。

![](assets/inbox_rendering_report_2.png)

この「**[!UICONTROL Technical data]**」タブでは、E メールの受信日や取得日、完全なヘッダーなどの詳細情報を取得できます。

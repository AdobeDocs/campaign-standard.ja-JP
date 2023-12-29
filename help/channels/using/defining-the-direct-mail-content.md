---
title: ダイレクトメールのコンテンツの定義
description: ダイレクトメール配信のコンテンツを定義する方法を説明します。
audience: channels
content-type: reference
topic-tags: direct-mail
context-tags: delivery,directMailContent,back
feature: Direct Mail
role: User
level: Intermediate
exl-id: 0a4c45ea-acc2-424f-8596-73376e344172
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 96%

---

# ダイレクトメールのコンテンツの定義{#defining-the-direct-mail-content}

コンテンツの定義をおこなうには、作成ウィザードの最後の画面でおこなうか、配信ダッシュボードの「**コンテンツ**」セクションをクリックします。

![](assets/direct_mail_6.png)

**[!UICONTROL Content]** 定義画面は、ダイレクトメールチャネルごとに異なります。この画面には「**[!UICONTROL Extraction]**」、「**[!UICONTROL File structure]**」、「**[!UICONTROL Header]**」、「**[!UICONTROL Footer]**」の 4 つのタブがあります。

![](assets/direct_mail_11.png)

## 抽出の定義 {#defining-the-extraction}

1. 最初に、抽出ファイルの名前を定義します。「**[!UICONTROL Output file]**」フィールドの右側にあるボタンをクリックし、目的のラベルを入力します。パーソナライゼーションフィールド、コンテンツブロックおよび動的テキストを使用できます（[コンテンツの定義](../../designing/using/personalization.md#example-email-personalization)を参照）。例えば、配信 ID や抽出日を使用してラベルを完成させることができます。

   ![](assets/direct_mail_12.png)

1. 出力列を追加するには、**[!UICONTROL +]** または「**[!UICONTROL Add an element]**」ボタンをクリックします。**[!UICONTROL Output columns]** を使用すると、出力ファイルに書き出すプロファイル情報（列）を定義できます。

   >[!IMPORTANT]
   >
   >住所はダイレクトメールプロバイダーにとって重要なものなので、プロファイルに住所が含まれていることを確認してください。また、プロファイル情報の「**[!UICONTROL Address specified]**」ボックスがオンになっていることも確認してください。[レコメンデーション](../../channels/using/about-direct-mail.md#recommendations)を参照してください。

   ![](assets/direct_mail_13.png)

1. 必要な数の列を作成します。列の式とラベルをクリックすると、列を編集できます。

>[!NOTE]
>
>出力列の定義の詳細については、[ファイル抽出](../../automating/using/extract-file.md)ワークフローのアクティビティの節を参照してください。

## ファイル構造の定義 {#defining-the-file-structure}

「**ファイル構造**」タブでは、書き出すファイルの出力、日付、数値の形式を設定できます。

![](assets/direct_mail_14.png)

>[!NOTE]
>
>使用可能なオプションの詳細については、[ファイル抽出](../../automating/using/extract-file.md)ワークフローアクティビティの各節を参照してください。

## ヘッダーとフッターの定義 {#defining-the-header-and-footer}

抽出ファイルの先頭または末尾に情報を追加することが必要となる場合があります。この場合は、**[!UICONTROL Content]**&#x200B;設定画面の「**[!UICONTROL Header]**」タブと「**[!UICONTROL Footer]**」タブを使用します。

![](assets/direct_mail_7.png)

例えば、ダイレクトメールプロバイダーの場合、送信者情報をファイルのヘッダーに含めることがあります。フッターとヘッダーは、配信のコンテキストで利用できる情報を使用してパーソナライズできます。詳しくは、[コンテンツの定義](../../designing/using/personalization.md#example-email-personalization)を参照してください。

送信者のアドレスは、ダイレクトメールプロパティの「**[!UICONTROL Send]**」セクションまたはテンプレートレベルで定義します。

![](assets/direct_mail_24.png)

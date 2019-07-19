---
title: URLからのコンテンツの読み込み
seo-title: URLからのコンテンツの読み込み
description: URLからのコンテンツの読み込み
seo-description: 電子メールの作成時に、既存のURLからコンテンツを読み込む方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 7db6c20f-7004-4fb8- add9-362eab3d2795
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: デザイン
content-type: 参照
topic-tags: ロードコンテンツ
discoiquuid: 738b7c8a-88eb-491c- a4d0-078b0959b973
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Importing content from a URL{#importing-content-from-a-url}

URLからコンテンツを読み込む前に、以下の要件に従っていることを確認してください。

* コンテンツは、このURLから公開する必要があります。
* For security reasons, only URLs beginning with **[!UICONTROL https]** are allowed.
* すべてのリソース（画像、CSS）が絶対リンクとHTTPSで設定されていることを確認してください。そうしないと、電子メールを送信した後、ミラーページがリソースなしで表示されます。以下に、絶対リンク定義の例を示します。

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>URLからのコンテンツの読み込みは、電子メールチャネルのみで行うことができます。

既存のコンテンツフォームをURLで取得するには、次の手順に従います。

1. From the Email Designer home page, select the **[!UICONTROL Import from URL]** button.

   ![](assets/email_designer_importfromurl.png)

1. コンテンツを取得するURLを定義します。
1. **[!UICONTROL Confirm]**&#x200B;をクリックします。

**関連トピック:**

[URL](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#Workingwithexistingcontent) ビデオからのコンテンツの読み込み

## Retrieving content from a URL automatically at preparation time {#retrieving-content-from-a-url-automatically-at-preparation-time}

メッセージの準備時にURLからコンテンツを読み込むと、電子メールが準備されるたびに最新のHTMLコンテンツを取得できます。このように、定期的な電子メールのコンテンツは、送信時に常に最新の状態になります。また、コンテンツがまだ準備されていない場合でも、特定の日付でスケジュールされたメッセージを作成することもできます。

準備時にコンテンツを取得するには、次の手順に従います。

1. **[!UICONTROL Content imported during preparation]** このオプションを選択します。

   ![](assets/email_designer_importfromurl2.png)

1. URLコンテンツは読み取り専用としてエディターに表示されます。

   >[!CAUTION]
   >
   >この手順では、コンテンツエディターのHTML表示を考慮しないでください。これは準備段階で取得されます。

1. To preview the URL content that has been retrieved, open the message once it is created then click the **[!UICONTROL Preview]** button.

コンテンツを取得するリモートURLをパーソナライズできます。これを行うには、次の手順に従います。

1. Click the email label on top of the screen to acces the Email Designer **[!UICONTROL Properties]** tab.
1. **[!UICONTROL Remote URL]** フィールドを検索します。

   ![](assets/email_designer_importfromurl4.png)

1. 目的のパーソナライゼーションフィールド、コンテンツブロックまたは動的テキストを挿入します。

   **[!UICONTROL Current date - YYYYMMDD]** 例えば、コンテンツブロックで日付を挿入できます。

   >[!NOTE]
   >
   >The available personalization fields are linked to **Delivery** attributes only (email creation date, status, campaign label...).


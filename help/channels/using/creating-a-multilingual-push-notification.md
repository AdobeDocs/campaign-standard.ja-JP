---
title: 多言語プッシュ通知の作成
seo-title: 多言語プッシュ通知の作成
description: 多言語プッシュ通知の作成
seo-description: 多言語プッシュ通知を作成して、ユーザーを好みの言語や地域にターゲット設定します。
page-status-flag: 常にアクティブ化されていない
uuid: d4aff741- e969-47c6- bae8-787c6c673191
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: プッシュ通知
discoiquuid: f9bb2235- d388-4025-9ace-734beb0c1961
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Creating a multilingual push notification{#creating-a-multilingual-push-notification}

## About multilingual push notification {#about-multilingual-push-notification}

ユーザーの好みの言語と地域に基づいてメッセージを送信して、プッシュ通知コンテンツをパーソナライズします。コンテンツエディターで多言語プッシュ通知コンテンツバリアントを直接インポートし、単一の配信で多言語プッシュ通知を送信できます。

この機能は、プッシュ通知に使用する配信テンプレートに応じて、受信者のプロファイルまたはシステム言語の環境設定で指定された優先言語のいずれかを利用します。特定のユーザーに言語の環境設定が入力されていない場合、多言語プッシュ通知の作成時に定義されるデフォルトのバリアントが使用されます。For more information on how to manage your profiles and subscribers, refer to this [guide](../../audiences/using/about-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

プッシュ通知配信に多言語コンテンツバリアントを使用するには、次の手順に従います。

* [手順1:多言語コンテンツバリアントのアップロード](../../channels/using/creating-a-multilingual-push-notification.md#step-1--upload-multilingual-content-variant)
* [手順2:多言語コンテンツバリアントを使用したプッシュ通知のプレビューとファイナライズ](../../channels/using/creating-a-multilingual-push-notification.md#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [手順3:多言語プッシュ通知配信の送信と分析](../../channels/using/creating-a-multilingual-push-notification.md#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Step 1: Upload multilingual content variant {#step-1--upload-multilingual-content-variant}

多言語プッシュ通知をパーソナライズする前に、まず多言語配信テンプレートにコンテンツバリアントをアップロードし、配信を作成する必要があります。

>[!NOTE]
>
>また、言語バリアントごとに手動でバリアントを作成する場合は、この手順をスキップすることもできます。

1. In the **[!UICONTROL Marketing activities]**, click the **[!UICONTROL Create]** button then select **[!UICONTROL Push notification]**.
1. Select the template **[!UICONTROL Send multilingual push to Campaign profiles]** if you want to target the Adobe Campaign profiles who have subscribed to your mobile application or the template **[!UICONTROL Send multilingual push to app subscriber]** to send a push notification to all users who have opted in to receive notifications from your mobile application.

   ![](assets/multivariant_push_2.png)

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   ドロップダウンには、SDK V4およびAdobe Experience Platform SDKアプリケーションの両方が表示されることに注意してください。

1. **[!UICONTROL Audiences]** ウィンドウで、クエリーをドラッグ&amp;ドロップして、オーディエンスを微調整します。

   The queries added depend on the chosen template: if you chose the **[!UICONTROL Send multilingual push to Campaign profiles]** template you can query known recipients of your mobile application. Whereas if you chose the **[!UICONTROL Send multilingual push to app subscriber]** template, you can query all subscribers of a particular app who have opted in.

   ![](assets/push_notif_audience.png)

1. **[!UICONTROL Manage Content Variants]** ウィンドウで、ファイルをドラッグ&amp;ドロップするか、コンピューターからファイルを選択します。

   The file has to be UTF8 encoded and must have a specific layout which can be found by clicking the **[!UICONTROL Download the sample file]** option. ロケール値に適切な構文も使用する必要があります。For more information regarding the file format and the supported locales, refer to this [technote](http://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. After uploading your file, the language variants are automatically populated in the **[!UICONTROL Variants]** tab. Note that you can provide a **[!UICONTROL Default variant]** in the file which will be your default content variant if no preferred language is specified for the targeted user.

   ![](assets/multivariant_push_5.png)

1. **[!UICONTROL Variant selection]** タブには、配信テンプレートに応じて考慮される言語の優先順位を決定するスクリプトが表示されます。これは、変更を必要としないままのスクリプトです。
1. If you want to add more variants not present in the imported file, you can do so by clicking the **[!UICONTROL Add an element]** button and add as many new language variants as needed.

   ファイルからアップロードされたもの以外のバリアントを追加すると、この言語にリンクされたコンテンツは一切表示されません。コンテンツを配信ダッシュボードで直接編集する必要があります。

   ![](assets/multivariant_push_6.png)

1. Click **[!UICONTROL Create]** when the configuration is done. You can always come back to the **[!UICONTROL Content variant]** window and make some changes from your delivery dashboard.

   ![](assets/multivariant_push_8.png)

多言語プッシュ通知をパーソナライズできるようになりました。

## Step 2: Preview and finalize a push notification using multilingual content variants {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

コンテンツバリアントを含むファイルをアップロードした後、プッシュ通知配信から様々なバリアントをプレビューできるようになりました。

ファイルからアップロードされたものに加えて、より多くのバリアントを作成して編集することもできます。

1. In the **[!UICONTROL Content]** window from the delivery dashboard, the drop-down allows you to preview your push notification content depending on the chosen language.

   ![](assets/multivariant_push_7.png)

1. 特定の言語に対してコンテンツバリアントが指定されていない場合は、プレビューの下のベルアイコンをクリックして、この言語バリアントにコンテンツを追加します。

   By clicking the **[!UICONTROL Content]** window, the push notification represents the content from the language selected in the drop down. このウィンドウで行った変更は、1言語にのみ影響します。

1. コンテンツバリアントをクリックして、パーソナライゼーションフィールドなどのようにカスタマイズすることもできます。

   For more information on how to customize your push notification, refer to this [section](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Click the **[!UICONTROL Content variant]** window if you want to add or delete language variants.

   新しい言語を追加することで、追加された言語にリンクされているプッシュ通知にコンテンツを手動で追加する必要があります。

   ![](assets/multivariant_push_10.png)

多言語プッシュ通知配信を送信できるようになりました。

## Step 3: Send and analyze multilingual push notification delivery {#step-3--send-and-analyze-multilingual-push-notification-delivery}

多言語コンテンツバリアントプッシュ通知がユーザーに送信できるようになりました。

1. To start preparing the send, click the **[!UICONTROL Prepare]** button.
1. When the preparation is finished with no warnings, you can click the **[!UICONTROL Confirm]** button to start sending your multilingual push.

   ![](assets/multivariant_push_12.png)

1. After successfully sending your push notification, click the **[!UICONTROL Reports]** icon then **[!UICONTROL Dynamic reports]** to analyze the success of your delivery.

   ![](assets/multivariant_push_13.png)

1. Select **[!UICONTROL Push notification report]**.
1. Drag and drop the **[!UICONTROL Variant]** dimension to your panel to start filtering your data.

   ![](assets/multivariant_push_11.png)

受信者に多言語プッシュ通知配信の影響を測定できるようになりました。

**関連トピック:**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)


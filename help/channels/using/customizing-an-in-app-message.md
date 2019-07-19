---
title: アプリ内メッセージのカスタマイズ
seo-title: アプリ内メッセージのカスタマイズ
description: アプリ内メッセージのカスタマイズ
seo-description: アプリ内メッセージを様々なオプションでカスタマイズする方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 1d9c08ed-4de5-440d- bf51-4a437eec67d5
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: アプリ内メッセージ
discoiquuid: c9c3e033- e319-447b-8d87- ff7dd4941876
context-tags: delivery， inAppContent， back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Customizing an In-App message{#customizing-an-in-app-message}

アプリ内メッセージを微調整するために、Adobe Campaignではアプリ内のデザイン中に高度なオプションのセットにアクセスできます。

アプリ内コンテンツエディタでは、次の2つのアプリ内メッセージモードを選択できます。

* [メッセージテンプレート](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-message-template):このテンプレートを使用すると、画像やビデオ、アクションボタンを使用してアプリ内アプリを完全にカスタマイズできます。
* [カスタムメッセージ](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-custom-html-message):このテンプレートを使用して、カスタムHTMLを読み込むことができます。

![](assets/inapp_customize_1.png)

**関連トピック:**

* [アプリ内メッセージの送信](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)
* [アプリ内レポート](../../reporting/using/in-app-report.md)

## Customizing with a message template {#customizing-with-a-message-template}

### Layout {#layout}

**[!UICONTROL Layout]** ドロップダウンには、メッセージのニーズに応じて選択する4つのオプションがあります。

* **[!UICONTROL Full page]**:この種類のレイアウトは、オーディエンスデバイスの画面全体をカバーします。

   メディア（画像、ビデオ）、テキストおよびボタンコンポーネントをサポートしています。

* **[!UICONTROL Large modal]**:このレイアウトは大きな警告形式のウィンドウに表示され、アプリケーションはバックグラウンドでも表示されます。

   メディア（画像、ビデオ）、テキストおよびボタンコンポーネントをサポートしています。

* **[!UICONTROL Small modal]**:このレイアウトは小さいアラートタイプウィンドウとして表示され、アプリケーションはバックグラウンドで表示されます。

   メディア（画像、ビデオ）、テキストおよびボタンコンポーネントをサポートしています。

* **[!UICONTROL Alert]**:この種類のレイアウトは、ネイティブのOSアラートメッセージとして表示されます。

   テキストおよびボタンコンポーネントのみサポートできます。

* **[!UICONTROL Local notification]**:この種類のレイアウトはバナーメッセージとして表示されます。

   サウンド、テキストおよび宛先のみをサポートできます。For more on local notification, refer to [Customizing a local notification message type](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type).

各タイプのレイアウトは、スマートフォン、タブレット、プラットフォームなどの様々なデバイスでプレビューできます。例えば、コンテンツエディターの右側のウィンドウでは、横置きや縦置きなどの横置きや縦置きなどがあります。

![](assets/inapp_customize_4.png)

### Media {#media}

**[!UICONTROL Media]** このドロップダウンを使用すると、アプリ内メッセージにメディアを追加して、エンドユーザー向けの説得力のあるエクスペリエンスを作成できます。

1. Select your **[!UICONTROL Media Type]** between image and video.
1. **[!UICONTROL Image]** メディアの種類については、サポートされている形式に基づいて **[!UICONTROL Media URL]** フィールドにURLを入力します。

   If needed, you can also enter the path to a **[!UICONTROL Bundled image]** which can be used if the device is offline.

   ![](assets/inapp_customize_5.png)

1. **[!UICONTROL Video]** メディアの種類について、 **[!UICONTROL Media URL]** フィールドにURLを入力します。

   Then, enter your **[!UICONTROL Video poster]** to be used while the video is downloading on the audience devices or until users tap the play button.

   ![](assets/inapp_customize_6.png)

### Text {#text}

必要に応じて、アプリ内メッセージにメッセージのタイトルとコンテンツを追加することもできます。アプリ内メッセージをパーソナライズするには、異なるパーソナライゼーションフィールド、コンテンツブロック、動的テキストをコンテンツに追加できます。

1. **[!UICONTROL Text]** ドロップダウンで **[!UICONTROL Message title]** 、フィールドにタイトルを追加します。

   ![](assets/inapp_customize_9.png)

1. **[!UICONTROL Message content]** フィールドにコンテンツを追加します。
1. To further personalize your text, click the ![](assets/edit_darkgrey-24px.png) icon to add personalization fields.

   ![](assets/inapp_customize_8.png)

1. メッセージコンテンツを入力し、必要に応じてパーソナライゼーションフィールドを追加します。

   For more information on personalization field, refer to this [section](../../designing/using/inserting-a-personalization-field.md).

   ![](assets/inapp_customize_10.png)

1. プレビューウィンドウでメッセージの内容を確認します。

   ![](assets/inapp_customize_11.png)

### Buttons {#buttons}

アプリ内メッセージには、2つまでのボタンを追加できます。

1. **[!UICONTROL Buttons]** ドロップダウンで **[!UICONTROL Primary]** 、カテゴリに最初のボタンのテキストを入力します。

   ![](assets/inapp_customize_12.png)

1. Choose which of the two actions **[!UICONTROL Dismiss]** and **[!UICONTROL Redirect]** will be assigned to your primary button.
1. **[!UICONTROL Secondary]** カテゴリ内で、テキストを入力して必要に応じて、アプリ内の2つ目のボタンを追加します。
1. 2番目のボタンに関連付けられているアクションを選択します。
1. If you chose the **[!UICONTROL Redirect]** action, enter your web URL or deeplink in the **[!UICONTROL Destination URL]** field.

   ![](assets/inapp_customize_13.png)

1. Enter your web URL or deeplink in the **[!UICONTROL Destination URL]** field, if you chose the **[!UICONTROL Redirect]** action,
1. プレビューウィンドウでメッセージの内容を確認するか、「プレビュー」ボタンをクリックします。

   Refer to the [Previewing the In-App message](../../channels/using/customizing-an-in-app-message.md#previewing-the-in-app-message) page.

   ![](assets/inapp_customize_11.png)

### 設定 {#settings}

1. **[!UICONTROL Settings]** カテゴリで、ライトとダークの間の背景色を選択します。
1. Choose to display or not a close button with the **[!UICONTROL Show close button]** option to provide users a way to dismiss the In-App message.
1. **[!UICONTROL Button alignment]** オプションを使用してボタンの整列を水平または垂直にする場合に選択します。
1. アプリ内メッセージを自動的に閉じるか、数秒後に表示しないかを選択します。

   ![](assets/inapp_customize_7.png)

## Customizing a local notification message type {#customizing-a-local-notification-message-type}

ローカル通知は、特定の時刻にのみアプリによってトリガーされ、イベントによってはトリガーされます。インターネットにアクセスしなくても、アプリで何かが発生したことをユーザーに通知します。

ローカル通知をカスタマイズするには:

1. **[!UICONTROL Content]** ページから、カテゴリ **[!UICONTROL Local notification]** 内で選択 **[!UICONTROL Layout]** します

   ![](assets/inapp_customize_17.png)

1. **[!UICONTROL Text]** カテゴリの下で **[!UICONTROL Message title]** 、および&#x200B;**[!UICONTROL Message content]**

   ![](assets/inapp_customize_18.png)

1. **[!UICONTROL Advanced option]** カテゴリの下で **[!UICONTROL Wait to display]** 、イベントがトリガーされたときに、ローカル通知が画面に表示されるまでの時間を秒単位で選択します。
1. **[!UICONTROL Sound]** このフィールドに、ローカル通知の受信時にモバイルデバイスによって再生される、拡張子なしのサウンドファイルのファイル名を入力します。

   ファイルがモバイルアプリケーションのパッケージで定義されている場合、サウンドファイルは通知を配信するときに再生されます。それ以外の場合は、デバイスのデフォルトのサウンドが再生されます。

   ![](assets/inapp_customize_19.png)

1. Specify a destination to redirect your users when they interact with your local notification in the **[!UICONTROL Deeplink URL]** field.
1. キー値ペアの形式でペイロードでカスタムデータを渡すには、カスタムのフィールドをローカル通知に追加します。**[!UICONTROL Custom fields]** カテゴリで、ボタンを **[!UICONTROL Create an element]** クリックします。
1. Enter your **[!UICONTROL Keys]** then the **[!UICONTROL Values]** associated with each key.

   カスタムフィールドの処理と目的は、完全にモバイルアプリです。

1. In the **[!UICONTROL Apple options]** category, fill in the **[!UICONTROL Category]** fields to add a category ID for custom actions if available in your Apple mobile application.

## Customizing with a custom HTML message {#customizing-with-a-custom-html-message}

>[!NOTE]
>
>カスタムHTMLメッセージはコンテンツのパーソナライゼーションをサポートしていません。

**[!UICONTROL Custom message]** このモードでは、事前設定済みのHTMLメッセージのいずれかを直接インポートできます。

そのためには、コンピューターからファイルをドラッグ&amp;ドロップするか、選択するだけです。

Your file must have a specific layout which can be found by clicking the **Download the sample file** option.

![](assets/inapp_customize_16.png)

Adobe Campaignでのインポートが正常に完了するためのカスタムHTML要件のリストも参照できます。

![](assets/inapp_customize_3.png)

HTMLが読み込まれたら、プレビューウィンドウの様々なデバイスでファイルのプレビューを確認できます。

## Previewing the In-App message {#previewing-the-in-app-message}

アプリ内メッセージを送信する前に、テストプロファイルでテストして、ターゲットオーディエンスが配信を受信したときにどのように表示されるかを確認できます。

1. Click the **[!UICONTROL Preview]** button.

   ![](assets/inapp_sending_2.png)

1. Click the **[!UICONTROL Select a test profile]** button and select one of your test profiles to start previewing your delivery. For more information on test profiles, refer to this [section](../../sending/using/managing-test-profiles-and-sending-proofs.md).
1. Android、iPhone Phone、タブレットなどの様々なデバイスでメッセージを確認します。パーソナライゼーションフィールドで適切なデータを取得しているかどうかも確認できます。

   ![](assets/inapp_sending_3.png)

1. 配信レポートでメッセージを送信し、その影響を測定できるようになりました。For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).


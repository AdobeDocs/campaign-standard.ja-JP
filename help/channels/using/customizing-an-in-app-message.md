---
title: インアプリメッセージのカスタマイズ
seo-title: インアプリメッセージのカスタマイズ
description: インアプリメッセージのカスタマイズ
seo-description: さまざまなオプションでインアプリメッセージをカスタマイズする方法について説明します。
page-status-flag: 決して活性化されていない
uuid: 1d9c08ed-4de5-440d- bf51-4a437eec67d5
contentOwner: ソビア
products: SG_キャンペーン/標準
audience: チャンネル
content-type: 参照
topic-tags: アプリ内メッセージング
discoiquuid: c9c3e033- e319-447b-8d87- ff7dd4941876
context-tags: 配信， InAppContent，バック
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 43183a3adc35da3dac807a888f1b694fbb9a623c

---


# インアプリメッセージのカスタマイズ{#customizing-an-in-app-message}

In- Appメッセージを微調整するために、Adobe Campaignでは、インアプリのデザイン中に一連の詳細オプションにアクセスできます。

インアプリコンテンツエディタでは、2つのIn- Appメッセージモードを選択できます。

* [メッセージテンプレート](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-message-template):このテンプレートを使用すると、In- Appをイメージやビデオおよびアクションボタンで完全にカスタマイズできます。
* [カスタムメッセージ](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-custom-html-message):このテンプレートを使用すると、カスタムHTMLをインポートできます。

![](assets/inapp_customize_1.png)

**関連トピック:**

* [In- Appメッセージの送信](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)
* [インアプリレポート](../../reporting/using/in-app-report.md)

## メッセージテンプレートを使用したカスタマイズ {#customizing-with-a-message-template}

### レイアウト {#layout}

**[!UICONTROL Layout]** ドロップダウンでは、メッセージングのニーズに応じて、次の4つのオプションを選択できます。

* **[!UICONTROL Full page]**:このタイプのレイアウトは、視聴者デバイスの画面全体をカバーします。

   メディア（イメージ、ビデオ）、テキスト、ボタンのコンポーネントをサポートします。

* **[!UICONTROL Large modal]**:このレイアウトは大きな警告スタイルウィンドウに表示され、アプリケーションはバックグラウンドで表示されます。

   メディア（イメージ、ビデオ）、テキスト、ボタンのコンポーネントをサポートします。

* **[!UICONTROL Small modal]**:このレイアウトは小さな警告型ウィンドウとして表示され、アプリケーションはバックグラウンドで表示されます。

   メディア（イメージ、ビデオ）、テキスト、ボタンのコンポーネントをサポートします。

* **[!UICONTROL Alert]**:このタイプのレイアウトはネイティブOSアラートメッセージとして表示されます。

   テキストコンポーネントとボタンコンポーネントのみサポートできます。

* **[!UICONTROL Local notification]**:このタイプのレイアウトは、バナーメッセージとして表示されます。

   サウンド、テキスト、および変換先のみをサポートできます。ローカル通知の詳細については、「 [ローカル通知メッセージの種類のカスタマイズ」を](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)参照してください。

各タイプのレイアウトは、電話、タブレット、プラットフォームなどのさまざまなデバイスでプレビューできます。例えば、AndroidやiOSなどの場合は、コンテンツエディタの右ウィンドウに表示されます。

![](assets/inapp_customize_4.png)

### メディア {#media}

**[!UICONTROL Media]** ドロップダウンを使用すると、インアプリメッセージにメディアを追加してエンドユーザーにとって魅力的なエクスペリエンスを作成できます。

1. イメージとビデオ **[!UICONTROL Media Type]** の間を選択します。
1. **[!UICONTROL Image]** メディアタイプの場合は、サポートされている形式に基づいて、フィールド **[!UICONTROL Media URL]** にURLを入力します。

   必要に応じて、デバイスがオフラインになっている場合に使用できるパス **[!UICONTROL Bundled image]** を入力することもできます。

   ![](assets/inapp_customize_5.png)

1. **[!UICONTROL Video]** メディアの種類については、フィールド **[!UICONTROL Media URL]** にURLを入力します。

   次に、視聴者デバイスでビデオをダウンロードするとき、またはユーザーが再生ボタンをタップするまで、使用 **[!UICONTROL Video poster]** するように入力します。

   ![](assets/inapp_customize_6.png)

### テキスト {#text}

必要に応じて、メッセージのタイトルとコンテンツをIn- Appメッセージに追加することもできます。In- Appメッセージをより適切にカスタマイズするには、異なるパーソナル化フィールド、コンテンツブロック、およびダイナミックテキストをコンテンツに追加します。

1. **[!UICONTROL Text]** ドロップダウンで、フィールド **[!UICONTROL Message title]** にタイトルを追加します。

   ![](assets/inapp_customize_9.png)

1. フィールド **[!UICONTROL Message content]** にコンテンツを追加します。
1. テキストをさらにカスタマイズするには、アイコンをクリック ![](assets/edit_darkgrey-24px.png) してパーソナル化フィールドを追加します。

   ![](assets/inapp_customize_8.png)

1. 必要に応じて、メッセージの内容を入力し、パーソナル化フィールドを追加します。

   パーソナル化フィールドの詳細については、この [セクションを](../../designing/using/inserting-a-personalization-field.md)参照してください。

   ![](assets/inapp_customize_10.png)

1. プレビューウィンドウでメッセージの内容を確認します。

   ![](assets/inapp_customize_11.png)

### ボタン {#buttons}

In- Appメッセージには、最大2つのボタンを追加できます。

1. **[!UICONTROL Buttons]** ドロップダウンで、カテゴリ **[!UICONTROL Primary]** 内の最初のボタンのテキストを入力します。

   ![](assets/inapp_customize_12.png)

1. 2つのアクション **[!UICONTROL Dismiss]** のどちらかを選択 **[!UICONTROL Redirect]** し、プライマリボタンに割り当てます。
1. カテゴリ **[!UICONTROL Secondary]** 内で、必要に応じてテキストを入力して、2番目のボタンをIn- Appに追加します。
1. 2番目のボタンに関連付けられたアクションを選択します。
1. **[!UICONTROL Redirect]** アクションを選択した場合は、フィールドにWeb **[!UICONTROL Destination URL]** URLまたはデジインクを入力します。

   ![](assets/inapp_customize_13.png)

1. このアクションを選択した場合は **[!UICONTROL Destination URL]** 、フィールドにWeb **[!UICONTROL Redirect]** URLまたはdeepinkを入力します。
1. プレビューウィンドウでメッセージの内容を確認するか、「プレビュー」ボタンをクリックします。

   "In- App"メッセージ [](../../channels/using/customizing-an-in-app-message.md#previewing-the-in-app-message) ページのプレビューを参照してください。

   ![](assets/inapp_customize_11.png)

### 設定 {#settings}

1. カテゴリ **[!UICONTROL Settings]** で、明暗間の背景色を選択します。
1. ユーザーにIn- Appメッセージを閉じる方法を提供する **[!UICONTROL Show close button]** オプションを持つ閉じるボタンを表示するかどうかを選択します。
1. ボタンの配置を水平または垂直にする **[!UICONTROL Button alignment]** オプションを選択します。
1. 数秒後にIn- Appメッセージを自動却下できるかどうかを選択します。

   ![](assets/inapp_customize_7.png)

## ローカル通知メッセージ型のカスタマイズ {#customizing-a-local-notification-message-type}

ローカル通知は、特定の時刻のアプリによってのみトリガーされ、イベントによってのみトリガーされます。インターネットにアクセスすることなく、アプリで何かが発生していることをユーザーに警告します。

ローカル通知をカスタマイズするには:

1. ページ **[!UICONTROL Content]** から、カテゴリ **[!UICONTROL Local notification]** 内で選択し **[!UICONTROL Layout]** ます

   ![](assets/inapp_customize_17.png)

1. カテゴリ **[!UICONTROL Text]** の下に、と **[!UICONTROL Message title]** と入力 **[!UICONTROL Message content]**&#x200B;します。

   ![](assets/inapp_customize_18.png)

1. カテゴリ **[!UICONTROL Advanced option]** の下で **[!UICONTROL Wait to display]** 、イベントが発生した後にローカル通知が画面に表示される時間を秒単位で選択します。
1. フィールド **[!UICONTROL Sound]** 内に、ローカル通知が受信されたときにモバイルデバイスによって再生されるサウンドファイルのファイル名を入力します。

   このサウンドファイルは、ファイルがモバイルアプリケーションのパッケージで定義されている場合に通知を配信するときに再生されます。それ以外の場合は、デバイスのデフォルトサウンドが再生されます。

   ![](assets/inapp_customize_19.png)

1. ユーザーがフィールド **[!UICONTROL Deeplink URL]** 内のローカル通知と対話するときに、ユーザーをリダイレクトする宛先を指定します。
1. ペイロード内のカスタムデータをキー値ペアの形式で渡すには、ローカル通知にカスタムフィールドを追加します。**[!UICONTROL Custom fields]** カテゴリで、 **[!UICONTROL Create an element]** ボタンをクリックします。
1. 各キーに関連付けられたその **[!UICONTROL Keys]****[!UICONTROL Values]** 後に入力します。

   カスタムフィールドの取り扱いと目的は、完全にモバイルアプリになっていることに注意してください。

1. カテゴリ **[!UICONTROL Apple options]** 内で **[!UICONTROL Category]** 、Appleモバイルアプリケーションで使用可能なカスタムアクションのカテゴリIDを追加するフィールドを入力します。

## カスタムHTMLメッセージを使用したカスタマイズ {#customizing-with-a-custom-html-message}

>[!NOTE]
>
>カスタムHTMLメッセージはコンテンツのパーソナル化をサポートしていません。

**[!UICONTROL Custom message]** このモードでは、構成済みのHTMLメッセージのいずれかを直接インポートできます。

そのためには、コンピュータからファイルをドラッグアンドドロップまたは選択するだけです。

ファイルには、「サンプルファイル **をダウンロード」** オプションをクリックして検索できる特定のレイアウトが必要です。

![](assets/inapp_customize_16.png)

また、Adobe Campaignで正常にインポートするためのカスタムHTML要件のリストも検索できます。

![](assets/inapp_customize_3.png)

HTMLをインポートすると、プレビューウィンドウ内の別のデバイスにファイルのプレビューが表示されます。

## In- Appメッセージのプレビュー {#previewing-the-in-app-message}

In- Appメッセージを送信する前に、テストプロファイルでテストして、対象対象者が配信を受信したときに表示される内容を確認できます。

1. ボタンをクリック **[!UICONTROL Preview]** します。

   ![](assets/inapp_sending_2.png)

1. **[!UICONTROL Select a test profile]** ボタンをクリックし、テストプロファイルの1つを選択して、配信のプレビューを開始します。テストプロファイルの詳細については、この [セクションを](../../sending/using/managing-test-profiles-and-sending-proofs.md)参照してください。
1. Android、iPhone電話、タブレットなどのさまざまなデバイスでメッセージを確認します。パーソナル化フィールドが正しいデータを取得しているかどうかを確認することもできます。

   ![](assets/inapp_sending_3.png)

1. メッセージを送信し、その影響を配信レポートで測定できるようになりました。For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).


---
title: In-Appメッセージのカスタマイズ
seo-title: In-Appメッセージのカスタマイズ
description: In-Appメッセージのカスタマイズ
seo-description: In-Appメッセージをさまざまなオプションでカスタマイズする方法を説明します。
page-status-flag: 未活性化の
uuid: 1d9c08ed-4de5-440d-bf51-4a437eec67d5
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: チャンネル
content-type: 参照
topic-tags: アプリ内メッセージング
discoiquuid: c9c3e033-e319-447b-8d87-ff7dd4941876
context-tags: 配信，inAppContent，戻る
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# In-Appメッセージのカスタマイズ{#customizing-an-in-app-message}

In-Appメッセージを微調整するには、Adobe Campaignを使用して、In-Appのデザイン中に一連の詳細なオプションにアクセスできます。

In-Appコンテンツエディタでは、2つのIn-Appメッセージモードを選択できます。

* [メッセージテンプレート](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-message-template):このテンプレートを使用すると、画像やビデオ、アクションボタンを使用してIn-Appを完全にカスタマイズできます。
* [カスタムメッセージ](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-custom-html-message):このテンプレートを使用すると、カスタムHTMLをインポートできます。

![](assets/inapp_customize_1.png)

**関連トピック：**

* [In-Appメッセージを送信しています](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)
* [In-Appレポート](../../reporting/using/in-app-report.md)

## メッセージテンプレートを使用したカスタマイズ {#customizing-with-a-message-template}

### レイアウト {#layout}

このドロ **[!UICONTROL Layout]** ップダウンには、メッセージングのニーズに応じて、次の4つのオプションが用意されています。

* **[!UICONTROL Full page]**:この種類のレイアウトは、対象ユーザーデバイスの画面全体をカバーします。

   メディア（イメージ、ビデオ）、テキスト、ボタンの各コンポーネントをサポートします。

* **[!UICONTROL Large modal]**:このレイアウトは、大きな警告スタイルのウィンドウに表示され、アプリケーションはバックグラウンドで表示されます。

   メディア（イメージ、ビデオ）、テキスト、ボタンの各コンポーネントをサポートします。

* **[!UICONTROL Small modal]**:このレイアウトは、小さな警告の種類のウィンドウとして表示され、アプリケーションはバックグラウンドで表示されたままです。

   メディア（イメージ、ビデオ）、テキスト、ボタンの各コンポーネントをサポートします。

* **[!UICONTROL Alert]**:このタイプのレイアウトは、ネイティブのOS警告メッセージとして表示されます。

   テキストとボタンのコンポーネントのみをサポートできます。

* **[!UICONTROL Local notification]**:この種類のレイアウトは、バナーメッセージとして表示されます。

   サウンド、テキスト、宛先のみをサポートできます。 ローカル通知の詳細については、「ローカル通知メ [ッセージタイプのカスタマイズ」を参照してくださ](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)い。

各タイプのレイアウトは、電話、タブレット、プラットフォーム（Android、iOSなど）、向き（横長、縦長など）など、コンテンツエディタの右側のウィンドウに異なるデバイスでプレビューできます。

![](assets/inapp_customize_4.png)

### メディア {#media}

このドロ **[!UICONTROL Media]** ップダウンでは、In-Appメッセージにメディアを追加して、エンドユーザーにとって魅力的なエクスペリエンスを作成できます。

1. イメージとビデ **[!UICONTROL Media Type]** オの間を選択します。
1. メディア·タ **[!UICONTROL Image]** イプの場合は、サポートされる形式に基づい **[!UICONTROL Media URL]** て、フィールドにURLを入力します。

   必要に応じて、デバイスがオフラインの場合に使用で **[!UICONTROL Bundled image]** きるのへのパスを入力することもできます。

   ![](assets/inapp_customize_5.png)

1. メディア·タ **[!UICONTROL Video]** イプの場合は、フィールドにURLを入力 **[!UICONTROL Media URL]** します。

   次に、ビデオが対象デ **[!UICONTROL Video poster]** バイスでダウンロード中、またはユーザーが再生ボタンをタップするまで、使用するユーザーを入力します。

   ![](assets/inapp_customize_6.png)

### テキスト {#text}

必要に応じて、In-Appメッセージにメッセージタイトルとコンテンツを追加することもできます。 In-Appメッセージをよりカスタマイズするには、異なる個人用設定フィールド、コンテンツブロック、および動的テキストをコンテンツに追加します。

1. ドロップダウ **[!UICONTROL Text]** ンで、フィールドにタイトルを追加 **[!UICONTROL Message title]** します。

   ![](assets/inapp_customize_9.png)

1. フィールドにコンテンツを追加 **[!UICONTROL Message content]** します。
1. テキストをさらにパーソナライズするには、アイコンをク ![](assets/edit_darkgrey-24px.png) リックして個人用設定フィールドを追加します。

   ![](assets/inapp_customize_8.png)

1. メッセージの内容を入力し、必要に応じて個人用設定フィールドを追加します。

   個人用設定フィールドの詳細については、このセクションを参照して [ください](../../designing/using/personalization.md#inserting-a-personalization-field)。

   ![](assets/inapp_customize_10.png)

1. プレビューウィンドウでメッセージの内容を確認します。

   ![](assets/inapp_customize_11.png)

### ボタン {#buttons}

In-Appメッセージには、最大2つのボタンを追加できます。

1. ドロップダウ **[!UICONTROL Buttons]** ンリストに、カテゴリ内の最初のボタンのテキストを入力 **[!UICONTROL Primary]** します。

   ![](assets/inapp_customize_12.png)

1. 2つのアクションの中から、ど **[!UICONTROL Dismiss]** のアクション **[!UICONTROL Redirect]** をプライマリボタンに割り当てるかを選択します。
1. カテゴリ **[!UICONTROL Secondary]** で、必要に応じてテキストを入力して、In-Appに2番目のボタンを追加します。
1. 2つ目のボタンに関連付けられているアクションを選択します。
1. アクションを選択した場 **[!UICONTROL Redirect]** 合は、フィールドにWeb URLまたは詳細を入力 **[!UICONTROL Destination URL]** します。

   ![](assets/inapp_customize_13.png)

1. アクションを選択した場合は、フィールドにWeb URL **[!UICONTROL Destination URL]** または詳細を入力し **[!UICONTROL Redirect]** ます。
1. プレビューウィンドウでメッセージの内容を確認するか、[プレビュー]ボタンをクリックします。

   「In-Appメッセ [ージのプレビュー](../../channels/using/customizing-an-in-app-message.md#previewing-the-in-app-message) 」ページを参照。

   ![](assets/inapp_customize_11.png)

### 設定 {#settings}

1. カテゴリ **[!UICONTROL Settings]** で、明るい色と暗い色の間の背景色を選択します。
1. In-Appメッセージを閉じる方法をユーザーに提供す **[!UICONTROL Show close button]** るためのオプションを付けて閉じるボタンを表示するかどうかを選択します。
1. このオプションを使用して、ボタンの配置を水平または垂直にするかどうかを選択 **[!UICONTROL Button alignment]** します。
1. In-Appメッセージを自動的に破棄するか、数秒後に終了しないかを選択します。

   ![](assets/inapp_customize_7.png)

## ローカル通知メッセージタイプのカスタマイズ {#customizing-a-local-notification-message-type}

ローカル通知は、特定の時刻にアプリが起動し、イベントに応じて起動できます。 インターネットにアクセスしなくても、アプリで何かが起こっていることをユーザーに警告します。

ローカル通知をカスタマイズするには、次の手順に従います。

1. ページから、 **[!UICONTROL Content]** カテゴリ内のを **[!UICONTROL Local notification]** 選択しま **[!UICONTROL Layout]** す。

   ![](assets/inapp_customize_17.png)

1. カテゴリの **[!UICONTROL Text]** 下に、とを入力し **[!UICONTROL Message title]** ます **[!UICONTROL Message content]**。

   ![](assets/inapp_customize_18.png)

1. カテゴリの **[!UICONTROL Advanced option]** フィールドで、イ **[!UICONTROL Wait to display]** ベントがトリガされた後にローカル通知を画面に表示する時間（秒）を選択します。
1. フィールド **[!UICONTROL Sound]** に、ローカル通知を受信したときにモバイルデバイスが再生するサウンドファイルのファイル名を拡張子と共に入力します。

   サウンドファイルは、モバイルアプリケーションのパッケージでファイルが定義されている場合に、通知を配信する際に再生されます。 それ以外の場合は、デバイスのデフォルトのサウンドが再生されます。

   ![](assets/inapp_customize_19.png)

1. フィールドでローカル通知を操作する際に、ユーザーをリダイレクトする宛先を指定 **[!UICONTROL Deeplink URL]** します。
1. キー値ペアの形式でペイロード内のカスタムデータを渡すには、ローカル通知にカスタムフィールドを追加します。 カテゴリで、 **[!UICONTROL Custom fields]** ボタンをクリック **[!UICONTROL Create an element]** します。
1. 各キーに関連 **[!UICONTROL Keys]** 付けられ **[!UICONTROL Values]** たを入力します。

   カスタムフィールドの処理と目的は、モバイルアプリに完全に依存していることに注意してください。

1. カテゴリで、Apple **[!UICONTROL Apple options]** モバイルアプリケーション **[!UICONTROL Category]** で使用可能なカスタムアクションのカテゴリIDを追加するフィールドに入力します。

## カスタムHTMLメッセージを使用したカスタマイズ {#customizing-with-a-custom-html-message}

>[!NOTE]
>
>カスタムHTMLメッセージは、コンテンツの個人用設定をサポートしていません。

このモ **[!UICONTROL Custom message]** ードでは、事前に設定したHTMLメッセージの1つを直接インポートできます。

そのためには、コンピュータからファイルをドラッグアンドドロップまたは選択するだけです。

ファイルには、[サンプルファイルをダウンロード]オプションをクリックして、特定のレイア **ウトが必要です** 。

![](assets/inapp_customize_16.png)

また、Adobe Campaignで読み込みを成功させるためのカスタムHTML要件のリストも表示されます。

![](assets/inapp_customize_3.png)

HTMLを読み込むと、プレビューウィンドウ内の別のデバイスでファイルのプレビューを検索できます。

## In-Appメッセージのプレビュー {#previewing-the-in-app-message}

In-Appメッセージを送信する前に、テストプロファイルを使用してテストを行い、配信を受け取った対象ユーザーが表示する内容を確認できます。

1. ボタンをクリック **[!UICONTROL Preview]** します。

   ![](assets/inapp_sending_2.png)

1. ボタンをクリ **[!UICONTROL Select a test profile]** ックし、テストプロファイルの1つを選択して、配信のプレビューを開始します。 テストプロファイルの詳細については、このセクションを参照して [ください](../../sending/using/managing-test-profiles-and-sending-proofs.md)。
1. Android、iPhone、タブレットなど、さまざまなデバイスでメッセージを確認します。 また、個人用設定フィールドが適切なデータを取得しているかどうかを確認することもできます。

   ![](assets/inapp_sending_3.png)

1. これで、メッセージを送信し、配信レポートでその影響を測定できます。 For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).


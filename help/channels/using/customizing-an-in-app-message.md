---
title: アプリ内メッセージのカスタマイズ
description: アプリ内メッセージを様々なオプションでカスタマイズする方法を説明します。
page-status-flag: never-activated
uuid: 1d9c08ed-4de5-440d-bf51-4a437eec67d5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: in-app-messaging
discoiquuid: c9c3e033-e319-447b-8d87-ff7dd4941876
context-tags: delivery,inAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1269ee2041e0857b077424ba7f50fbfa9519ae7b

---


# アプリ内メッセージのカスタマイズ{#customizing-an-in-app-message}

アプリ内メッセージを微調整するために、Adobe Campaignでは、アプリ内メッセージのデザイン時に一連の高度なオプションにアクセスできます。

アプリ内コンテンツエディターでは、アプリ内メッセージモードを2つ選択できます。

* [Message Template](#customizing-with-a-message-template):このテンプレートを使用すると、画像やビデオ、アクションボタンを使用して、アプリ内を完全にカスタマイズできます。
* [Custom Message](#customizing-with-a-custom-html-message):このテンプレートを使用して、カスタムHTMLを読み込むことができます。

![](assets/inapp_customize_1.png)

>[!NOTE]
>
> アプリ内メッセージのレンダリングは、Android API 19以降のバージョンでのみサポートされます。

**関連トピック：**

* [アプリ内メッセージの送信](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)
* [アプリ内レポート](../../reporting/using/in-app-report.md)
* [ローカル通知追跡の実装](https://helpx.adobe.com/campaign/kb/local-notification-tracking.html)

## メッセージテンプレートを使用したカスタマイズ {#customizing-with-a-message-template}

### レイアウト {#layout}

ドロッ **[!UICONTROL Layout]** プダウンには、メッセージのニーズに応じて次の4つの選択肢が表示されます。

* **[!UICONTROL Full page]**:このタイプのレイアウトは、オーディエンスデバイスの画面全体をカバーします。

   メディア（画像、ビデオ）、テキストおよびボタンのコンポーネントをサポートします。

* **[!UICONTROL Large modal]**:このレイアウトは、大きな警告スタイルのウィンドウに表示され、アプリケーションはバックグラウンドで表示されます。

   メディア（画像、ビデオ）、テキストおよびボタンのコンポーネントをサポートします。

* **[!UICONTROL Small modal]**:このレイアウトは、小さな警告タイプのウィンドウとして表示され、アプリケーションはバックグラウンドで表示されます。

   メディア（画像、ビデオ）、テキストおよびボタンのコンポーネントをサポートします。

* **[!UICONTROL Alert]**:このタイプのレイアウトは、ネイティブのOS警告メッセージとして表示されます。

   テキストおよびボタンコンポーネントのみをサポートできます。

* **[!UICONTROL Local notification]**:このタイプのレイアウトは、バナーメッセージとして表示されます。

   サウンド、テキスト、出力先のみをサポートします。 ローカル通知の詳細については、「ローカル通知メッセージ [タイプのカスタマイズ」を参照してくださ](#customizing-a-local-notification-message-type)い。

各タイプのレイアウトは、スマートフォン、タブレット、プラットフォーム（AndroidやiOSなど）や、コンテンツエディターの右ウィンドウの横置きや縦置きなど、様々なデバイスでプレビューできます。

![](assets/inapp_customize_4.png)

### メディア {#media}

このドロ **[!UICONTROL Media]** ップダウンを使用すると、アプリ内メッセージにメディアを追加して、エンドユーザーにとって魅力的なエクスペリエンスを作成できます。

1. 画像とビデ **[!UICONTROL Media Type]** オの間で選択します。
1. メディアタ **[!UICONTROL Image]** イプについては、サポートされている形式に **[!UICONTROL Media URL]** 基づいて、URLを入力します。

   必要に応じて、デバイスがオフラインの場合に使用で **[!UICONTROL Bundled image]** きる、のパスを入力することもできます。

   ![](assets/inapp_customize_5.png)

1. メディアタ **[!UICONTROL Video]** イプのフィールドにURLを入力し **[!UICONTROL Media URL]** ます。

   次に、ビデオがオーディエ **[!UICONTROL Video poster]** ンスデバイスでダウンロード中のとき、またはユーザーが再生ボタンをタップするまで、使用するユーザーを入力します。

   ![](assets/inapp_customize_6.png)

### テキスト {#text}

必要に応じて、アプリ内メッセージにメッセージのタイトルとコンテンツを追加することもできます。 アプリ内メッセージをよりパーソナライズするために、コンテンツに異なるパーソナライゼーションフィールド、コンテンツブロックおよび動的テキストを追加できます。

1. ドロップダウ **[!UICONTROL Text]** ンで、フィールドにタイトルを追加 **[!UICONTROL Message title]** します。

   ![](assets/inapp_customize_9.png)

1. フィールドにコンテンツを追加 **[!UICONTROL Message content]** します。
1. テキストをさらにパーソナライズするには、アイコンをクリックし ![](assets/edit_darkgrey-24px.png) てパーソナライゼーションフィールドを追加します。

   ![](assets/inapp_customize_8.png)

1. メッセージの内容を入力し、必要に応じてパーソナライゼーションフィールドを追加します。

   For more information on personalization field, refer to this [section](../../designing/using/personalization.md#inserting-a-personalization-field).

   ![](assets/inapp_customize_10.png)

1. プレビューウィンドウでメッセージの内容を確認します。

   ![](assets/inapp_customize_11.png)

### ボタン {#buttons}

アプリ内メッセージには、最大2つのボタンを追加できます。

1. ドロップダ **[!UICONTROL Buttons]** ウンで、カテゴリ内の最初のボタンのテキストを入力 **[!UICONTROL Primary]** します。

   ![](assets/inapp_customize_12.png)

1. 2つのアクションのうちどれを主 **[!UICONTROL Dismiss]** 要ボタ **[!UICONTROL Redirect]** ンに割り当てるかを選択します。
1. 必要に応じ **[!UICONTROL Secondary]** て、カテゴリにテキストを入力し、アプリ内に2つ目のボタンを追加します。
1. 2つ目のボタンに関連付けられているアクションを選択します。
1. アクションを選択した **[!UICONTROL Redirect]** 場合は、Web URLまたはディープリンクをフィールドに入力 **[!UICONTROL Destination URL]** します。

   ![](assets/inapp_customize_13.png)

1. アクションを選択した場合は、Web URLまたは **[!UICONTROL Destination URL]** ディープリンクをフィールドに入力 **[!UICONTROL Redirect]** します。
1. プレビューウィンドウで、または「プレビュー」ボタンをクリックして、メッセージの内容を確認します。

   アプリ内メッセ [ージのプレビューページを参照](#previewing-the-in-app-message) 。

   ![](assets/inapp_customize_11.png)

### 設定 {#settings}

1. カテゴリ **[!UICONTROL Settings]** で、明暗の背景色を選択します。
1. アプリ内メッセージを閉じる方法をユーザーに提供す **[!UICONTROL Show close button]** る閉じるボタンを表示するかどうかを選択します。
1. このオプションを使用して、ボタンの配置を水平または垂直にするかどうかを選 **[!UICONTROL Button alignment]** 択します。
1. アプリ内メッセージを数秒後に自動的に閉じるかどうかを選択します。

   ![](assets/inapp_customize_7.png)

## ローカル通知メッセージタイプのカスタマイズ {#customizing-a-local-notification-message-type}

ローカル通知は、特定の時間とイベントに応じて、アプリによってのみトリガーされます。 ユーザーは、インターネットにアクセスできなくても、アプリで何かが起きていることをユーザーに通知します。
ローカル通知の追跡方法については、このページを参照してく [ださい](https://helpx.adobe.com/campaign/kb/local-notification-tracking.html)。

ローカル通知をカスタマイズするには：

1. ページか **[!UICONTROL Content]** ら、カテゴリ内 **[!UICONTROL Local notification]** のを選択しま **[!UICONTROL Layout]** す。

   ![](assets/inapp_customize_17.png)

1. カテゴリ **[!UICONTROL Text]** の下で、とを入力し **[!UICONTROL Message title]** ます **[!UICONTROL Message content]**。

   ![](assets/inapp_customize_18.png)

1. カテゴリ **[!UICONTROL Advanced option]** のフィールドで、 **[!UICONTROL Wait to display]** イベントがトリガーされた後にローカル通知が画面に表示される時間（秒）を選択します。
1. このフィー **[!UICONTROL Sound]** ルドに、ローカル通知を受信したときにモバイルデバイスで再生されるサウンドファイルのファイル名と拡張子を入力します。

   ファイルがモバイルアプリケーションのパッケージで定義されている場合、サウンドファイルは通知の配信時に再生されます。 それ以外の場合は、デバイスのデフォルトのサウンドが再生されます。

   ![](assets/inapp_customize_19.png)

1. フィールドでローカル通知を操作する際にユーザーをリダイレクトする宛先を指定 **[!UICONTROL Deeplink URL]** します。
1. キーと値のペアの形式でペイロードのカスタムデータを渡すには、カスタムフィールドをローカル通知に追加します。 カテゴリ内 **[!UICONTROL Custom fields]** で、ボタンをクリック **[!UICONTROL Create an element]** します。
1. 各キーに関 **[!UICONTROL Keys]** 連付けら **[!UICONTROL Values]** れたを入力します。

   カスタムフィールドの処理と目的は、モバイルアプリケーションによって完全に決まります。

1. カテゴリ内 **[!UICONTROL Apple options]** のフィールドに入力し、Apple **[!UICONTROL Category]** のモバイルアプリケーションでカスタムアクションが使用可能な場合は、そのカテゴリIDを追加します。

## カスタムHTMLメッセージによるカスタマイズ {#customizing-with-a-custom-html-message}

>[!NOTE]
>
>カスタムHTMLメッセージは、コンテンツのパーソナライゼーションをサポートしていません。

このモ **[!UICONTROL Custom message]** ードでは、事前設定済みのHTMLメッセージの1つを直接読み込むことができます。

そのためには、ファイルをドラッグ&amp;ドロップするか、コンピューターから選択するだけで済みます。

ファイルには、「サンプルファイルをダウンロード」オプションをクリックして見つけられる特定のレ **イアウトが必要です** 。

![](assets/inapp_customize_16.png)

また、Adobe Campaignでのインポートを成功させるためのカスタムHTML要件のリストを確認することもできます。

![](assets/inapp_customize_3.png)

HTMLを読み込むと、プレビューウィンドウの異なるデバイスでファイルのプレビューを見つけることができます。

## アプリ内メッセージのプレビュー {#previewing-the-in-app-message}

アプリ内メッセージを送信する前に、テストプロファイルを使用してテストを行い、配信を受け取ったターゲットのオーディエンスに対して何が表示されるかを確認できます。

1. ボタンをクリッ **[!UICONTROL Preview]** クします。

   ![](assets/inapp_sending_2.png)

1. 配信のプレビ **[!UICONTROL Select a test profile]** ューを開始するには、ボタンをクリックし、テストプロファイルを1つ選択します。 For more information on test profiles, refer to this [section](../../audiences/using/managing-test-profiles.md).
1. Android、iPhone、タブレットなど、様々なデバイスでメッセージを確認します。 また、パーソナライゼーションフィールドが正しいデータを取得しているかどうかを確認することもできます。

   ![](assets/inapp_sending_3.png)

1. 配信レポートを使用して、メッセージを送信し、その影響を測定できるようになりました。 For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).


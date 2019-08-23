---
title: 電子メールの件名行のパーソナライズ
seo-title: 電子メールの件名行のパーソナライズ
description: 電子メールの件名行のパーソナライズ
seo-description: 電子メールの件名をパーソナライズしたり、異なる件名行を試したり、オープンレートを見積もることができます。
page-status-flag: 常にアクティブ化されていない
uuid: 345b5f4b-8c-4f8e- bce7-0e9b40a44932
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: デザイン
content-type: 参照
topic-tags: personalizing- content
discoiquuid: f7a5e935-54cf-422e-8459-27221409a200
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# 電子メールの件名行のパーソナライズ{#personalizing-the-subject-line-of-an-email}

## 電子メールの件名をパーソナライズする {#personalizing-an-email-subject}

メッセージを準備して送信するには、メッセージの件名が必須です。

>[!NOTE]
>
>件名行が空の場合、メッセージダッシュボードおよび電子メールデザイナーに警告が表示されます。

電子メールの件名を設定するには、電子メールDesignerホームページ（ホームアイコンからアクセス可能）の **[!UICONTROL Properties]** タブに進み **[!UICONTROL Subject]** 、セクションに入力します。

![](assets/email_designer_subject.png)

また、対応するアイコンをクリックして、パーソナライゼーションフィールド、コンテンツブロックおよび動的コンテンツを件名行に追加することもできます。

**関連トピック:**

* [パーソナライゼーションフィールドの挿入](../../designing/using/inserting-a-personalization-field.md)
* [コンテンツブロックの追加](../../designing/using/adding-a-content-block.md)
* [電子メールでの動的コンテンツの定義](../../designing/using/defining-dynamic-content-in-an-email.md)

## 予測件名行 {#predictive-subject-line}

電子メールを編集する際、異なる件名行を試してから、送信する前にそのオープンレートの見積もりを行うことができます。

この機能はデフォルトで無効になっています。最初のモデルが読み込まれるときに有効になります。モデルは、特定の業界に固有のトレーニングデータセットの結果です。モデルを使用すると、新しい件名行が送信されたときに、電子メールのオープンレートを予測できます。

>[!NOTE]
>
>この機能は、電子メールメッセージおよび英語のコンテンツのみを含むデータベースで使用できます。トレーニングされたモデルは一貫性がなく、インスタンスに他の言語の電子メールが含まれていると、誤った結果につながります。サブジェクトをテストできるオプションは、モデルが既にインスタンスで使用可能な場合にのみ表示されます。

### 件名のテスト {#testing-a-subject}

件名行をテストするには:

1. 電子メールを作成または開きます。
1. コンテンツを開き、対応する入力フィールドに電子メールの件名を入力します。
1. ボタンを **[!UICONTROL Test subject]** クリックして、ウィンドウに **[!UICONTROL Test your subject line]** アクセスします。このウィンドウからも件名を編集できます。
1. オープンレート予測に考慮する正しいモデルを選択します。特定の業界に対応するいくつかのモデルが使用できます。
1. **[!UICONTROL Test]**&#x200B;をクリックします。

件名が分析されます。

>[!NOTE]
>
>件名行が短すぎると、分析できず、エラーメッセージが表示されます。

いくつかのインジケーターが計算され、次のようなツールセットが表示されます。

* **予想されるオープンレート**:このグラフでは、電子メールが現在の件名と共に予想されるオープンレートを把握できます。
* **件名の長さ**:このインジケーターを使用すると、件名の現在の長さが正しいか、またはより長く、短くなければならないかを確認できます。
* **色付きの単語**:件名をテストする場合、緑色で強調表示されている単語は、オープンレートの予測を増やすために最も貢献する単語です。赤でハイライトされている単語は、オープンレート予測を増やすまでに最低限貢献している単語です。件名に単語を追加または削除すると、ハイライトされている単語が変更されます。
* **カテゴリと単語の提案**:ウィンドウの下部には、選択したモデルに関連する多数の関連カテゴリが表示されます。これらのカテゴリは重要度順に並べ替えられ、サブジェクトにチェック記号を使用して関連付けられた単語が含まれているかどうかを確認できます。各カテゴリには、より関連性の高い、オープン率を高めるために使用できる提案語のセットが含まれています。これらの単語は、特定のカテゴリで最も頻繁に使用される単語です。

>[!NOTE]
>
>パーソナライゼーションフィールドと句読点は、件名分析から削除されます。ダイナミック/条件テキストの場合、すべてのバリアントは1つの件名として見なされます。

![](assets/predictive_subject_line_example.png)

### モデルの読み込み {#importing-models}

デフォルトでは、Adobe Campaignサーバー上で実行されているモデルはありません。モデルを取得して機能をアクティブにするには、次の2つの方法があります。

* 以前の電子メールメッセージのデータから、ローカルモデルをトレーニングできます。

   * 既にAdobe Campaignを使用している場合、ローカルモデルには既に送信済みのメッセージが自動的にトレーニングされます。
   * Adobe Campaignを初めて使用する場合、4列を含む以前のシステム/ESPからCSVファイルを抽出できます。date， subject， send， open.これを行うには **[!UICONTROL Administration]** 、&gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Subject Line Import]** に移動して、連続する画面に表示される指示に従います。件名のアップロードが完了したら、以下の説明に従ってローカルモデルをインポートします。ローカルモデルは、アップロードしたデータを使用して自動的にトレーニングされます。
   * Adobe Campaignを初めて使用していて、前述のようにCSVファイルを取得できない場合は、事前にトレーニングされたモデルを使用するか、システム内で十分な配信データを使用してローカルモデルをトレーニングすることができます。現在のデータセットには、パターンを認識し、モデルをトレーニングするために十分なデータが含まれているかどうかが自動的に判断されます。

      >[!NOTE]
      >
      >独自のモデルをトレーニングするために必要な件名行が定義されていません。これをトレーニングできるようにするには、件名行を変化させ、重複しないようにする必要があります。処理するデータが足りない場合、システムはモデルをトレーニングできません。インスタンスには1つのトレーニングモデルのみを使用できます。
   ローカルモデルをトレーニングするには、ここから [subjectLineTraining.xmlをダウンロード](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) し、 [パッケージインポート](../../automating/using/managing-packages.md) 機能を使用してAdobe Campaignインスタンスにアップロードします。技術ワークフローは、自動的にトレーニングを行います。

   初めてモデルをトレーニングしたい場合は、管理者が **[!UICONTROL SubjectLine Training workflow]****[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Workflows]** メニューから開始するように強制できます。

   モデルがアップロードされ、トレーニングされると、その機能は自動的にアクティブ化され、メッセージの件名行フィールドの横に新しいオプションが表示されます。

   その後、技術ワークフローは自動的に毎週引き続きモデルをトレーニングします。

* 特定の産業（医療など）に特有の事前にトレーニングされたモデルをインポートできます。パッケージ [インポート](../../automating/using/managing-packages.md) 機能を使用します。これらのモデルは [、ここで](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) 使用でき、トレーニングを行うことはできません。

   モデルがアップロードされると、その機能が自動的にアクティブ化され、メッセージの件名行フィールドの横に新しいオプションが表示されます。

>[!NOTE]
>
>トレーニングモデルの読み込みと生成は、管理者のみが実行できます。

使用できるモデルは次のとおりです。

* 化粧業界:subjectInsightCosmetic.xml
* スーパーマーケット業界:subjectInsightSupermarket.xml
* 医療業界:subjectInsightMedical.xml
* トレーニングモデル:subjectlineRainling. xml。

**関連トピック:**

* [Adobe Sensei予測による件名行の最適化](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Createcompellingcontenttailoredtoeveryindividual)

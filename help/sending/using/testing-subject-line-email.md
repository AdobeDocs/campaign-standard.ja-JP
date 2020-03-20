---
title: 電子メールの件名行のテスト
description: 電子メールデザイナで電子メールの件名行を定義する方法を確認します。
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6f89b420f0f98c13da1bfff8f9b1b29e015aef89

---

# 電子メールの件名行のテスト {#testing-a-subject}


## 予測対象行について {#about-predictive-subject-line}

電子メールを編集する際に、送信する前に別の件名を試して、開封率の見積もりを得ることができます。

この機能は、デフォルトで無効になっています。 最初のモデルを読み込むと有効になります。 モデルとは、特定の業界に固有のトレーニングデータセットの結果です。 モデルを使用すると、新しい件名行が送信された場合の電子メールの開封率を予測できます。

>[!NOTE]
>
>この機能は、電子メールメッセージおよび英語のコンテンツのみを含むデータベースで使用できます。 トレーニングされたモデルは一貫性がなく、インスタンスに他の言語の電子メールが含まれている場合は誤った結果を招きます。 サブジェクトをテストするオプションは、モデルが既にインスタンスで使用可能な場合にのみ表示されます。

モデルの読み込みについて詳しくは、この節を参照して [ください](#importing-models)。

## 件名行のテスト {#testing-subject-line}

件名をテストするには、次の手順に従います。

1. 電子メールを作成するか、開きます。
1. コンテンツを開き、対応する入力フィールドに電子メールの件名を入力します。
1. ボタンをクリッ **[!UICONTROL Test subject]** クして、ウィンドウにアクセ **[!UICONTROL Test your subject line]** スします。 このウィンドウでは、件名を編集できます。
1. オープンレート予測に考慮する正しいモデルを選択します。 いくつかのモデルが用意されており、それぞれが特定の業界に対応しています。 モデルの使用について詳しくは、この節を参照して [ください](#importing-models)。
1. クリック **[!UICONTROL Test]**.

その後、被験者が分析されます。

>[!NOTE]
>
>件名が短すぎると、分析できず、エラーメッセージが表示されます。

いくつかのインジケータが計算され、次の操作に役立つツールが表示されます。

* **予想開放率**:このグラフでは、現在の件名を含む電子メールの開封率を把握できます。
* **件名の長さ**:このインジケーターを使用すると、対象の現在の長さが正しいか、長くする必要があるか短くする必要があるかを確認できます。
* **色付きの単語**:被検者をテストする場合、緑色でハイライトされた単語は、開放率予測の増加に最も貢献する単語です。 赤で強調表示された単語は、開放率予測の増加に最も貢献しない単語です。 件名内の単語を追加または削除すると、ハイライト表示された単語が変更されます。
* **カテゴリと単語の提案**:ウィンドウの下部に、選択したモデルの関連カテゴリが多数表示されます。 これらのカテゴリは重要度の順に並べ替えられ、チェック記号を使用して関連付けられた単語が件名に含まれているかどうかを確認できます。 各カテゴリには、より関連性が高く、オープン率を高めるために、件名に使用できる推奨単語のセットが含まれています。 これらの単語は、特定のカテゴリで最も頻繁に使用される単語です。

>[!NOTE]
>
>パーソナライゼーションフィールドと句読点は、サブジェクト分析から削除されます。 動的/条件付きテキストの場合、すべてのバリエーションが1つの件名行と見なされます。

![](assets/predictive_subject_line_example.png)

## モデルの読み込み {#importing-models}

デフォルトでは、お使いのAdobe Campaignサーバー上で実行されているモデルはありません。 モデルを取得し、フィーチャーをアクティブにする方法は2つあります。

* 以前の電子メールメッセージのデータからローカルモデルをトレーニングできます。
* 特定の業界（医療など）に特有のトレーニングを受けたモデルをインポートできます。パッケージの読 [み込み機能を使用](../../automating/using/managing-packages.md) 。

### ローカルモデルのトレーニング {#training-local-model}

* 既にAdobe Campaignを使用している場合は、既に送信したメッセージに関するローカルモデルのトレーニングが自動的に行われます。
* Adobe Campaignを初めて使用する場合は、4つの列を含むCSVファイルを以前のシステム/ESPから抽出できます。日付、件名、開く、送信済み これを行うには、// **[!UICONTROL Administration]** >に移動 **[!UICONTROL Channels]** し **[!UICONTROL Email]** 、続く **[!UICONTROL Subject Line Import]** 画面の指示に従います。 件名のアップロードが完了したら、以下の説明に従ってローカルモデルを読み込みます。 ローカルモデルは、アップロードしたデータを使用して自動的にトレーニングを受けます。
* Adobe Campaignを初めて使用する場合で、上述のCSVファイルを取得できない場合は、事前にトレーニングされたモデルを使用するか [](#pre-trained-models) 、ローカルモデルをトレーニングするのに十分な配信データがシステムに存在するまで待ちます。 現在のデータセットに、パターンを認識し、モデルをトレーニングするのに十分なデータが含まれているかどうかを自動的に判断します。

>[!NOTE]
>
>独自のモデルをトレーニングするために必要な件名行の数が定義されていません。 For more on this, see [Troubleshooting](#troubleshooting).
>
>インスタンスには、トレーニングを受けたモデルを1つだけ持つことができます。

ローカルモデルをトレーニングするには：
1. ここからsubjectLineTraining.xmlをダウンロードし [](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) 、パッケージのインポ [ート機能を使用して](../../automating/using/managing-packages.md) 、Adobe Campaignインスタンスにアップロードします。 テクニカルワークフローが自動的にトレーニングを行います。
1. モデルのトレーニングを初めて行う場合、管理者は、 > >メニューから **[!UICONTROL SubjectLine Training workflow]** を強制的に開始す **[!UICONTROL Administration]** るよう **[!UICONTROL Application settings]** に設定で **[!UICONTROL Workflows]** きます。
1. モデルがアップロードされ、トレーニングされると、この機能が自動的にアクティブ化され、メッセージの件名行フィールドの横に新しいオプションが表示されます。
1. その後、技術ワークフローは自動的に毎週モデルのトレーニングを継続します。

### 事前にトレーニングを受けたモデルの読み込み {#pre-trained-models}

これらのモデルにアクセスするには、こ [こをクリック](https://support.neolane.net/webApp/extranetLogin) し、に進みま **[!UICONTROL Download Center]**&#x200B;す。 パッケージの [読み込み機能を使用して](../../automating/using/managing-packages.md) 、モデルをAdobe Campaignインスタンスにアップロードします。

使用できるモデルは次のとおりです。

* 化粧品業界：subjectInsightCosmetic.xml
* スーパーマーケット業界：subjectInsightSuperpart.xml
* 医療業界：subjectInsightMedical.xml
* トレーニングするモデル：subjectlineTraining.xmlを参照してください。

これらのモデルはトレーニングできません。

モデルがアップロードされると、この機能が自動的にアクティブ化され、メッセージの件名行フィールドの横に新しいオプションが表示されます。

>[!NOTE]
>
>トレーニングモデルの読み込みと生成は、管理者のみが実行できます。

## トラブルシューティング {#troubleshooting}

予測対象明細は、公開率を使用してアップロードしたすべての対象明細を考慮に入れた機械学習プロセスです。 これにより、新しい件名行が送信された場合の電子メールの開封率を予測できます。

独自のモデルをトレーニングするには、モデルのトレーニングに使用する件名行の数に関係なく、件名行を変更し、重複しないようにする必要があります。

主題の線の質は重要です。 処理に十分な品質データがない場合や、前の件名行がすべて類似しすぎる場合は、モデルをトレーニングできず、エラーメッセージが表示される場合があります。 つまり、既存のレコードセットでは、信頼性の高い予測提案を提供できないことを意味します。

この場合は、アップロードするデータを確認し、モデルを効率的にトレーニングできるように件名行が十分に変化していることを確認します。

<!--Some clients have reported this issue: I have had the subject line training workflow running for about a year now.  It has trained on 883 records and I am still seeing the message "The existing dataset is not enough to generate a model."  I do get an error in the workflow every time it runs "XML-110009 Unable to find the element 'runwf' of path '/' (document with schema 'serverConf')".

For this, campaign takes the subject line as training data and tries to come up with significant enough model to predict open rate with 95% confidence.

The 400 subject line number is mention with at least and is only indicative, model generation will also depend on quality of these lines.

It may happen that even 10k subject lines don't lead to model generation if they are too similar.

It means that it can be case that you don't have enough subject lines to generate the model and it is giving this error.

If you are getting an error/warning message, it means that your existing set of records is not enough for the predictive subject module to give a high confidence suggestion.

Adobe recommends reviewing the data you are uploading as the similarity of the subject lines might be the issue.-->

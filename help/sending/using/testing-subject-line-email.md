---
title: E メールの件名行のテスト
description: 電子メールデザイナーで電子メールの件名行を定義する方法を確認します。
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 2%

---

# E メールの件名行のテスト {#testing-a-subject}


## 予測の件名行について {#about-predictive-subject-line}

電子メールを編集する際は、送信前に別の件名行を試して、開放率の見積もりを受け取ることができます。

この機能はデフォルトで無効になっています。 最初のモデルを読み込むと有効になります。 モデルは、特定の業界に固有のトレーニングデータセットの結果です。 モデルを使用すると、新しい件名行が送信された場合の電子メールの開封率を予測できます。

>[!NOTE]
>
>この機能は、電子メールメッセージおよび英語の内容のみを含むデータベースで使用できます。 トレーニングを受けたモデルが一貫性を失い、インスタンスに他の言語の電子メールが含まれる場合は、誤った結果が生じます。 サブジェクトをテストできるオプションは、インスタンスでモデルが既に使用可能な場合にのみ表示されます。

モデルの読み込みについて詳しくは、この [節を参照してください](#importing-models)。

## 件名行のテスト {#testing-subject-line}

件名をテストするには、次の手順に従います。

1. 電子メールを作成するか、開きます。
1. コンテンツを開き、対応する入力フィールドに電子メールの件名を入力します。
1. Click the **[!UICONTROL Test subject]** button to access the **[!UICONTROL Test your subject line]** window. このウィンドウでは、件名を編集できます。
1. オープンレート予測を考慮に入れる正しいモデルを選択します。 いくつかのモデルがあり、それぞれが特定の業界に対応しています。 モデルの使用について詳しくは、この [節を参照してください](#importing-models)。
1. 「**[!UICONTROL Test]**」をクリックします。

その後、被験者が分析されます。

>[!NOTE]
>
>件名が短すぎる場合は、分析できず、エラーメッセージが表示されます。

いくつかのインジケーターが計算され、以下の作業を行うのに役立つ一連のツールが表示されます。

* **予測開放率**:このグラフでは、現在の件名で電子メールに期待できる開放率を把握できます。
* **件名の長さ**:このインジケーターを使用すると、件名の現在の長さが正しいか、長くする必要があるか短くする必要があるかを確認できます。
* **色付きの単語**:被検者をテストする場合、緑色で強調表示されている単語は、開放率予測の増加に最も貢献する単語です。 赤で強調表示されている単語は、開放率予測の増加に最も貢献しない単語です。 件名に単語を追加または削除すると、ハイライト表示されている単語が変更されます。
* **カテゴリと単語の提案**:ウィンドウの下部に向かって、選択したモデルに関連するカテゴリが多数表示されます。 これらのカテゴリは重要度の順に並べ替えられ、チェック記号を使用して関連付けられた単語が件名に含まれているかどうかを確認できます。 各カテゴリには、より関連性が高く、開放率を高めるために、主題で使用できる推奨単語のセットが含まれています。 これらの単語は、特定のカテゴリで最も頻繁に使用される単語です。

>[!NOTE]
>
>パーソナライゼーションフィールドと句読点は、件名の分析から削除されます。 動的/条件付きテキストの場合、すべてのバリアントが1つの件名行と見なされます。

![](assets/predictive_subject_line_example.png)

## モデルの読み込み {#importing-models}

デフォルトでは、Adobe Campaignサーバー上で実行されているモデルはありません。 モデルを取得してフィーチャーをアクティブにする方法は2つあります。

* 以前の電子メールメッセージのデータからローカルモデルをトレーニングできます。
* 特定の業種（医療など）に固有のトレーニング済みモデルをインポートできます。 [パッケージの読み込み](../../automating/using/managing-packages.md) 機能を使用する。

### ローカルモデルのトレーニング {#training-local-model}

* 既にAdobe Campaignを使用している場合は、既に送信したメッセージに関するローカルモデルのトレーニングが自動的に行われます。
* Adobe Campaignを初めて使用する場合は、4つの列を含む以前のシステム/ESPからCSVファイルを抽出できます。日付、件名、開く、送信済み。 これを行うには、 > > **[!UICONTROL Administration]** > **[!UICONTROL Channels]** >に移動し、続く画面 **[!UICONTROL Email]****[!UICONTROL Subject Line Import]** の指示に従います。 件名のアップロードが完了したら、以下の説明に従ってローカルモデルを読み込みます。 ローカルモデルは、アップロードしたデータを使用して自動的にトレーニングを受けます。
* Adobe Campaignに慣れておらず、上記のCSVファイルを取得できない場合は、 [事前にトレーニングされたモデルを使用するか](#pre-trained-models) 、ローカルモデルのトレーニングに十分な配信データがシステムに存在するまで待つことができます。 パターンを認識し、モデルをトレーニングするのに十分なデータが現在のデータセットに含まれているかどうかを自動的に判断します。

>[!NOTE]
>
>独自のモデルをトレーニングするために必要な件名行の数が定義されていません。 For more on this, see [Troubleshooting](#troubleshooting).
>
>インスタンスには、トレーニングを受けたモデルを1つだけ持つことができます。

ローカルモデルをトレーニングするには：
1. subjectLineTraining.xmlを [ここからダウンロードし](https://experience.adobe.com/#/downloads/content/software-distribution/jp/campaign.html) 、 [パッケージインポート](../../automating/using/managing-packages.md) 機能を使用してAdobe Campaignインスタンスにアップロードします。 テクニカルワークフローが自動的にトレーニングを行います。
1. 初めてモデルをトレーニングする場合、管理者は **[!UICONTROL SubjectLine Training workflow]** > **[!UICONTROL Administration]** > **[!UICONTROL Application settings]****[!UICONTROL Workflows]** メニューからを強制的に開始させることができます。
1. モデルがアップロードされトレーニングされると、この機能は自動的にアクティブ化され、メッセージの件名フィールドの横に新しいオプションが表示されます。
1. その後、技術的なワークフローは、自動的に毎週モデルのトレーニングを継続します。

### 事前にトレーニングを受けたモデルのインポート {#pre-trained-models}

これらのモデルにアクセスするには、 [ここをクリックします](https://experience.adobe.com/#/downloads/content/software-distribution/jp/campaign.html)。 モデルをAdobe Campaignインスタンスにアップロードするには、 [パッケージの読み込み](../../automating/using/managing-packages.md) 機能を使用します。

使用できるモデルは次のとおりです。

* 化粧品業界：subjectInsightCosmetic.xml
* スーパーマーケット業界：subjectInsightSuperpark.xml
* 医療業界：subjectInsightMedical.xml
* トレーニング対象モデル：subjectlineTraining.xmlを参照してください。

これらのモデルはトレーニングできません。

モデルがアップロードされると、その機能は自動的にアクティブ化され、メッセージの件名フィールドの横に新しいオプションが表示されます。

>[!NOTE]
>
>トレーニングを受けたモデルのインポートと生成は、管理者のみが実行できます。

## トラブルシューティング {#troubleshooting}

予測の件名行は、自動学習プロセスです。自動学習では、自動でアップロードしたすべての件名行と自動入力率が考慮されます。 これにより、新しい件名行が送信された場合の電子メールの開封率を予測できます。

独自のモデルをトレーニングするには、モデルのトレーニングに使用する件名行の数に関係なく、件名行を変更し、重複を持たないようにする必要があります。

主題の質は不可欠です。 処理に十分な品質データがない場合、または前の件名行がすべて類似しすぎる場合は、モデルをトレーニングできず、エラーメッセージが表示される場合があります。 つまり、既存のレコードセットでは、信頼性の高い予測提案を提供できません。

この場合、アップロードするデータを確認し、モデルを効率的にトレーニングできるように、件名が十分に変化していることを確認してください。

<!--Some clients have reported this issue: I have had the subject line training workflow running for about a year now.  It has trained on 883 records and I am still seeing the message "The existing dataset is not enough to generate a model."  I do get an error in the workflow every time it runs "XML-110009 Unable to find the element 'runwf' of path '/' (document with schema 'serverConf')".

For this, campaign takes the subject line as training data and tries to come up with significant enough model to predict open rate with 95% confidence.

The 400 subject line number is mention with at least and is only indicative, model generation will also depend on quality of these lines.

It may happen that even 10k subject lines don't lead to model generation if they are too similar.

It means that it can be case that you don't have enough subject lines to generate the model and it is giving this error.

If you are getting an error/warning message, it means that your existing set of records is not enough for the predictive subject module to give a high confidence suggestion.

Adobe recommends reviewing the data you are uploading as the similarity of the subject lines might be the issue.-->

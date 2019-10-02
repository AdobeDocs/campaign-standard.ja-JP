---
title: 電子メールの件名行のテスト
seo-title: 電子メールの件名行のテスト
description: 電子メールの件名行のテスト
seo-description: 電子メールデザイナーで電子メールの件名行を定義する方法を確認します。
page-status-flag: 非活性化の
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 送信
content-type: 参照
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8b85bbad7458286252a2900ce730288f6e52442e

---

# 件名のテスト {#testing-a-subject}

件名をテストするには、次の手順に従います。

1. 電子メールを作成するか、開きます。
1. コンテンツを開き、対応する入力フィールドに電子メールの件名を入力します。
1. ボタンをクリッ **[!UICONTROL Test subject]** クして、ウィンドウにアクセ **[!UICONTROL Test your subject line]** スします。 このウィンドウからは、件名を編集できます。
1. オープンレート予測に考慮する正しいモデルを選択します。 特定の業界に対応するいくつかのモデルが用意されています。
1. Click **[!UICONTROL Test]**.

その後、被験者が分析されます。

>[!NOTE]
>
>件名が短すぎると、分析できず、エラーメッセージが表示されます。

いくつかのインジケーターが計算され、以下の作業を行うのに役立つツールが表示されます。

* **予測開放率**:このグラフでは、現在の件名を含む電子メールの開封率を把握できます。
* **件名の長さ**:このインジケーターを使用すると、対象の現在の長さが正しいか、長くする必要があるか短くする必要があるかを確認できます。
* **色付きの単語**:サブジェクトをテストする場合、緑色でハイライトされている単語は、開放率予測の増加に最も貢献する単語です。 赤でハイライトされている単語は、開放率予測の増加に最も貢献していない単語です。 件名内の単語を追加または削除すると、ハイライト表示されている単語が変更されます。
* **サーチクエリ**:ウィンドウの下部には、選択したモデルに関連するカテゴリが多数表示されます。 これらのカテゴリは重要度の順に並べ替えられ、チェック記号を使用して関連付けられた単語が件名に含まれているかどうかを確認できます。 各カテゴリには、より関連性を高め、開放率を上げるために、サブジェクトで使用できる推奨単語のセットが含まれています。 These words are the words that are used the most often in a given category.

>[!NOTE]
>
>Personalization fields and punctuation marks are stripped from the subject analysis. In the case of dynamic/conditional text, all variants are considered as one subject line.

![](assets/predictive_subject_line_example.png)

## Importing models {#importing-models}

By default, there is no model running on your Adobe Campaign server. There are two ways to get a model and activate the feature:

* You can train a local model from the data of your previous email messages:

   * If you are already using Adobe Campaign, the local model will be automatically trained on the messages that you have already sent.
   * If you are new to Adobe Campaign, you can extract a CSV file from your previous system/ESP that contains 4 columns: date, subject, sent, opens. To do that, go to  &gt;  &gt;  &gt;  and follow the instructions provided on the successive screens. **[!UICONTROL Administration]****[!UICONTROL Channels]****[!UICONTROL Email]****[!UICONTROL Subject Line Import]** When the subject upload is complete, import a local model as described below. The local model is automatically trained with the data you uploaded.
   * If you are new to Adobe Campaign and cannot get a CSV file as described above, you can use a pre-trained model or wait until you have enough delivery data in your system to train a local model. The system will automatically determine whether your current data set contains enough data to recognize patterns and to train the model.

      >[!NOTE]
      >
      >There is no defined number of subject lines needed to train your own model. これを訓練するには、対象線を変え、重複を持たない必要があります。 処理に必要なデータがない場合、システムはモデルをトレーニングできません。 インスタンスには、トレーニングを受けたモデルを1つだけ持つことができます。
   ローカルモデルをトレーニングするには、ここからsubjectLineTraining.xmlをダウンロ [ードし](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) 、パッケージのインポート機能を使用 [して](../../automating/using/managing-packages.md) 、Adobe Campaignインスタンスにアップロードします。 テクニカルワークフローが自動的にトレーニングを行います。

   モデルを初めてトレーニングする場合、管理者は、 &gt; &gt;メニューから **[!UICONTROL SubjectLine Training workflow]** を強制的に開始す **[!UICONTROL Administration]** ること **[!UICONTROL Application settings]** ができ **[!UICONTROL Workflows]** ます。

   モデルがアップロードされ、トレーニングされると、この機能が自動的にアクティブ化され、メッセージの件名行フィールドの横に新しいオプションが表示されます。

   その後、技術ワークフローは自動的に毎週モデルのトレーニングを続けます。

* 特定の業種（医療など）に特有のトレーニングを受けたモデルをインポートできます。パッケージのイ [ンポート機能](../../automating/using/managing-packages.md) 。 これらのモデルはここで [入手でき](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) 、トレーニングはできません。

   モデルがアップロードされると、その機能が自動的にアクティブ化され、メッセージの件名行フィールドの横に新しいオプションが表示されます。

>[!NOTE]
>
>トレーニングを受けたモデルのインポートと生成は、管理者のみが実行できます。

使用できるモデルは次のとおりです。

* 化粧品業界：subjectInsightCosmetic.xml
* スーパー業界：subjectInsightSuperpart.xml
* 医療業界：subjectInsightMedical.xml
* トレーニングするモデル：subjectlineTraining.xml。
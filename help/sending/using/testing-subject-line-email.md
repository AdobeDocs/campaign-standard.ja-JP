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
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3fc0d9d7e90a31ffb34efc33d6f5c148ba5aac90

---

# Testing the subject line of an email {#testing-a-subject}

件名をテストするには、次の手順に従います。

1. Create or open your email.
1. Open the content and enter the subject of the email in the corresponding input field.
1. Click the **[!UICONTROL Test subject]** button to access the **[!UICONTROL Test your subject line]** window. You can still edit the subject from this window.
1. Select the correct model to be taken into account for the open rate prediction. Several models are available, each corresponding to a specific industry.
1. Click **[!UICONTROL Test]**.

Your subject is then analyzed.

>[!NOTE]
>
>If the subject line is too short, it cannot be analyzed and an error message is displayed.

Several indicators are calculated and a set of tools are displayed to help you:

* **Predicted open rate: This chart gives you an idea of the open rate you can expect for the email with its current subject.**
* **Subject length: This indicator lets you see if the current length of the subject is correct or whether it would need to be longer or shorter.**
* **Colored words: When testing the subject, words highlighted in green are the words that contribute the most to increasing the open rate prediction.** Words highlighted in red are the words that contribute the least to increasing the open rate prediction. 件名内の単語を追加または削除すると、ハイライト表示されている単語が変更されます。
* **サーチクエリ**:ウィンドウの下部には、選択したモデルに関連するカテゴリが多数表示されます。 これらのカテゴリは重要度の順に並べ替えられ、チェック記号を使用して関連付けられた単語が件名に含まれているかどうかを確認できます。 Each category contains a set of suggested words that could be used in your subject to make it more relevant and increase the open rate. これらの単語は、特定のカテゴリで最も頻繁に使用される単語です。

>[!NOTE]
>
>パーソナライゼーションフィールドと句読点は、サブジェクト分析から削除されます。 動的/条件付きテキストの場合、すべてのバリアントが1つの件名行と見なされます。

![](assets/predictive_subject_line_example.png)

## モデルの読み込み {#importing-models}

デフォルトでは、Adobe Campaignサーバー上で実行されているモデルはありません。 モデルを取得してフィーチャーをアクティブにする方法は2つあります。

* 以前の電子メールメッセージのデータからローカルモデルをトレーニングできます。

   * 既にAdobe Campaignを使用している場合は、既に送信したメッセージに関するローカルモデルのトレーニングが自動的に実施されます。
   * Adobe Campaignを初めて使用する場合は、4つの列を含むCSVファイルを以前のシステム/ESPから抽出できます。日付、件名、送信済み、開く。 それには、&gt; &gt; &gt;に移動し **[!UICONTROL Administration]** 、続く画 **[!UICONTROL Channels]****[!UICONTROL Email]****[!UICONTROL Subject Line Import]** 面に表示される指示に従います。 件名のアップロードが完了したら、以下の説明に従ってローカルモデルを読み込みます。 ローカルモデルは、アップロードしたデータを使用して自動的にトレーニングを受けます。
   * Adobe Campaignを初めて使用する場合で、上記のCSVファイルを取得できない場合は、事前にトレーニングされたモデルを使用するか、ローカルモデルをトレーニングするのに十分な配信データがシステムにあるまで待つことができます。 現在のデータセットに、パターンを認識し、モデルをトレーニングするのに十分なデータが含まれているかどうかを自動的に判断します。

      >[!NOTE]
      >
      >独自のモデルをトレーニングするために必要な件名行の数が定義されていません。 これを訓練するには、対象線を変え、重複を持たない必要があります。 処理に必要なデータがない場合、システムはモデルをトレーニングできません。 インスタンスには、トレーニングを受けたモデルを1つだけ持つことができます。
   ローカルモデルをトレーニングするには、ここからsubjectLineTraining.xmlをダウンロ [ードし](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) 、パッケージのインポート機能を使用 [して](../../automating/using/managing-packages.md) 、Adobe Campaignインスタンスにアップロードします。 テクニカルワークフローが自動的にトレーニングを行います。

   モデルを初めてトレーニングする場合、管理者は、 &gt; &gt;メニューから **[!UICONTROL SubjectLine Training workflow]** を強制的に開始す **[!UICONTROL Administration]** ること **[!UICONTROL Application settings]** ができ **[!UICONTROL Workflows]** ます。

   モデルがアップロードされ、トレーニングされると、この機能が自動的にアクティブ化され、メッセージの件名行フィールドの横に新しいオプションが表示されます。

   その後、技術ワークフローは自動的に毎週モデルのトレーニングを続けます。

* You can import pre-trained models that are specific to certain industries (medical, etc.) パッケージのイ [ンポート機能](../../automating/using/managing-packages.md) 。 これらのモデルはここで [入手でき](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) 、トレーニングはできません。

   モデルがアップロードされると、その機能が自動的にアクティブ化され、メッセージの件名行フィールドの横に新しいオプションが表示されます。

>[!NOTE]
>
>Importing and generating trained models can only be performed by an administrator.

The models that are available for use are:

* Cosmetic industry: subjectInsightCosmetic.xml
* Supermarket industry: subjectInsightSupermarket.xml
* Medical industry: subjectInsightMedical.xml
* Model to train: subjectlineTraining.xml.

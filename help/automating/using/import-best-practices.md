---
solution: Campaign Standard
product: campaign
title: ベストプラクティスのインポート
description: データをデータベースにインポートする際に従うベストプラクティスの詳細を説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 72%

---


# ベストプラクティスのインポート {#import-best-practices}

>[!CAUTION]
>
>この機能を使用する際は、Adobe Campaign契約に従って、SFTPストレージ、DBストレージ、およびアクティブなプロファイルの制限に留意してください。

次に説明するいくつかのシンプルなルールに注意して従うと、データベース内のデータの一貫性を確保し、データベースの更新中またはデータを読み込む際の一般的なエラーを避けるのに非常に役立ちます。

## インポートテンプレートの使用 {#using-import-templates}

Most import workflows should contain the following activities: **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**.

インポートテンプレートを使用すると、同様のインポートを準備したり、データベース内のデータの一貫性を確保したりするのに非常に便利です。

In many projects, imports are built without **[!UICONTROL Deduplication]** activity because the files used in the project do not have duplicates. 複数のファイルをインポートすると、重複が発生する場合があります。そうなると、重複排除は困難になります。そのため、すべてのインポートワークフローで重複排除ステップを設けることは、優れた予防措置となります。

受信データは一貫性があり正しいとか、IT 部門や Adobe Campaign スーパーバイザーが対処するとは思わないでください。プロジェクトの間、データクレンジングに留意してください。データをインポートする際には、重複排除し、紐付けし、一貫性を維持します。

データのインポート用に設計された汎用ワークフローテンプレートの例を [例で示します。ワークフローテンプレートのインポート](../../automating/using/creating-import-workflow-templates.md) 」セクション。

>[!NOTE]
>
>また、 [インポートテンプレートを使用することもできます](../../automating/using/importing-data-with-import-templates.md)。 これらは、管理者が定義したワークフローテンプレートです。アクティブ化すると、読み込むデータを含むファイルを指定できるのはオファーのみになります。

**関連トピック：**

* [ファイルを読み込みアクティビティ](../../automating/using/load-file.md)
* [調整アクティビティ](../../automating/using/reconciliation.md)
* [Segmentation アクティビティ](../../automating/using/segmentation.md)
* [重複排除 - 重複アクティビティ](../../automating/using/deduplication.md)
* [データアクティビティの更新](../../automating/using/update-data.md)

## フラットファイルフォーマットの使用 {#using-flat-file-formats}

インポートで最も効率的なフォーマットは、フラットファイルです。フラットファイルは、データベースレベルで、一括モードでインポートできます。

次に例を示します。

* 区切り記号：タブまたはセミコロン
* 最初の行は見出し
* 文字列の区切り記号なし
* 日付フォーマット：YYYY/MM/DD HH:mm:SS

インポートするファイルの例：

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

## 圧縮の使用 {#using-compression}

可能であれば、インポートおよびエクスポートに zip 形式のファイルを使用します。GZIPはデフォルトでサポートされています。 ファイルの読み込み時に前処理を追加できます。また、データ抽出時に後処理を追加する場合は、ワークフローアクティビティ **[!UICONTROL Load file]** とワー **[!UICONTROL Extract file]** クフローを使用します。

**関連トピック：**

* [ファイルを読み込みアクティビティ](../../automating/using/load-file.md)
* [ファイルを抽出アクティビティ](../../automating/using/extract-file.md)

## 差分モードでのインポート {#importing-in-delta-mode}

通常のインポートは、差分モードで行う必要があります。 つまり、毎回、テーブル全体ではなく、新規または変更されたデータのみが Adobe Campaign に送信されるようにします。

完全インポートは、最初の読み込みにのみ使用する必要があります。

## 一貫性の維持 {#maintaining-consistency}

Adobe Campaign データベースのデータの一貫性を維持するには、次の原則に従います。

* インポートされたデータが Adobe Campaign の参照テーブルに一致する場合、ワークフローでそのテーブルと紐付けされる必要があります。一致しないレコードは、却下される必要があります。
* インポートされたデータが常に&#x200B;**「正規化」**&#x200B;されている（E メール、電話番号、ダイレクトメールアドレス）ことと、この正規化が信頼でき、何年にもわたって変更されないことを確認します。該当しない場合、データベースに何らかの重複が現れる可能性が高く、Adobe Campaign には「あいまい」一致をおこなうツールがないので、重複を管理および削除することが非常に難しくなります。
* 重複の作成を避けるために、トランザクションデータは、紐付けキーを持ち、既存のデータと紐付けされている必要があります。
* **関連ファイルを順番どおりにインポートします**。お互いに依存する複数のファイルでインポートが構成されている場合、ワークフローでファイルが正しい順番でインポートされていることを確認する必要があります。あるファイルが失敗すると、他のファイルはインポートされません。
* データをインポートする際には、**重複排除**&#x200B;し、紐付けし、一貫性を維持します。

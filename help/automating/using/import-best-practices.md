---
title: インポートのベストプラクティス
description: データをデータベースに読み込む際のベストプラクティスについて説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
exl-id: bb651b91-145f-4e87-92dd-a8b04662e380
TQID: https://experienceleague.adobe.com/mfBrdOii5qQZfqOs8VR4zuFM9CacwW-YwaYJm4U-Lt4
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 566
ht-degree: 75%

---

# インポートのベストプラクティス {#import-best-practices}

>[!CAUTION]
>
>この機能を使用する際は、Adobe Campaignの契約に従って、SFTP ストレージ、DB ストレージ、およびアクティブなプロファイルの制限に注意してください。

次に説明するいくつかのシンプルなルールに注意して従うと、データベース内のデータの一貫性を確保し、データベースの更新時またはデータのエクスポート時の一般的なエラーを避けるのに非常に有効です。

## インポートテンプレートの使用 {#using-import-templates}

ほとんどの読み込みワークフローには、次のアクティビティを含める必要があります：**[!UICONTROL Load file]**、**[!UICONTROL Reconciliation]**、**[!UICONTROL Segmentation]**、**[!UICONTROL Deduplication]**、**[!UICONTROL Update data]**。

インポートテンプレートを使用すると、同様のインポートを準備したり、データベース内のデータの一貫性を確保したりするのに非常に便利です。

多くのプロジェクトでは、プロジェクトで使用されるファイルに重複がないので、**[!UICONTROL Deduplication]** アクティビティなしでインポートが作成されます。 複数のファイルをインポートすると、重複が発生する場合があります。 そうなると、重複排除は困難になります。 そのため、すべてのインポートワークフローで重複排除ステップを設けることは、優れた予防措置となります。

受信データは一貫性があり正しいとか、IT 部門や Adobe Campaign スーパーバイザーが対処するとは思わないでください。 プロジェクトの間、データクレンジングに留意してください。 データをインポートする際には、重複排除し、紐付けし、一貫性を維持します。

データのインポート用に設計された汎用ワークフローテンプレートの例については、[例：ワークフローテンプレートのインポート ](../../automating/using/creating-import-workflow-templates.md) セクションを参照してください。

>[!NOTE]
>
>[ テンプレートの読み込み](../../automating/using/importing-data-with-import-templates.md)も使用できます。 これらは、管理者が定義したワークフローテンプレートです。一度アクティブ化すると、読み込むデータを含むファイルを指定するオプションのみが提供されます。

**関連トピック：**

* [ファイルを読み込みアクティビティ](../../automating/using/load-file.md)
* [紐付けアクティビティ](../../automating/using/reconciliation.md)
* [セグメント化アクティビティ](../../automating/using/segmentation.md)
* [重複排除 - 重複アクティビティ](../../automating/using/deduplication.md)
* [データアクティビティの更新](../../automating/using/update-data.md)

## フラットファイルフォーマットの使用 {#using-flat-file-formats}

インポートで最も効率的なフォーマットは、フラットファイルです。 フラットファイルは、データベースレベルで、一括モードでインポートできます。

次に例を示します。

* 区切り記号：タブまたはセミコロン
* 最初の行はヘッダー
* 文字列の区切り記号なし
* 日付形式：`YYYY/MM/DD HH:mm:SS`

インポートするファイルの例：

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

## 圧縮の使用 {#using-compression}

可能な限り、圧縮されたファイルをインポートおよびエクスポートに使用します。 GZIP がデフォルトでサポートされています。 **[!UICONTROL Load file]**&#x200B;および&#x200B;**[!UICONTROL Extract file]**&#x200B;のワークフローアクティビティで、ファイルを読み込む場合は前処理を、データを抽出する場合は後処理をそれぞれ追加できます。

**関連トピック：**

* [ファイルを読み込みアクティビティ](../../automating/using/load-file.md)
* [ファイルを抽出アクティビティ](../../automating/using/extract-file.md)

## 差分モードでのインポート {#importing-in-delta-mode}

定期的インポートは、差分モードでおこなう必要があります。 つまり、毎回、テーブル全体ではなく、新規または変更されたデータのみが Adobe Campaign に送信されるようにします。

完全インポートは、最初の読み込みにのみ使用する必要があります。

## 一貫性の維持 {#maintaining-consistency}

Adobe Campaign データベースのデータの一貫性を維持するには、次の原則に従います。

* インポートされたデータが Adobe Campaign の参照テーブルに一致する場合、ワークフローでそのテーブルと紐付けされる必要があります。 一致しないレコードは、却下される必要があります。
* インポートされたデータが常に&#x200B;**「正規化」**&#x200B;されている（メール、電話番号、ダイレクトメールアドレス）ことと、この正規化が信頼でき、何年にもわたって変更されないことを確認します。 該当しない場合、データベースに何らかの重複が現れる可能性が高く、Adobe Campaign には「あいまい」一致をおこなうツールがないので、重複を管理および削除することが非常に難しくなります。
* 重複の作成を避けるために、トランザクションデータは、紐付けキーを持ち、既存のデータと紐付けされている必要があります。
* **関連ファイルを順番どおりにインポートします**。 お互いに依存する複数のファイルでインポートが構成されている場合、ワークフローでファイルが正しい順序でインポートされていることを確認する必要があります。 あるファイルが失敗すると、他のファイルはインポートされません。
* データをインポートする際には、**重複排除**&#x200B;し、紐付けし、一貫性を維持します。

---
title: リストのエクスポート
description: 'Adobe Campaignでは、リストとして表示されたデータを概要画面から直接ファイルに書き出し、後で使用することができます。 '
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: b39ce1f6-0c5b-4270-86a1-b79c49cd199c
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 7%

---

# リストのエクスポート{#exporting-lists}

Adobe Campaignでは、将来の使用のためにリストをファイルに直接書き出すことができます。 ファイルにリストを書き出すと、**[!UICONTROL Export audits]** メニューにログエントリが生成されます。 エクスポートの監査について詳しくは、[エクスポートの監査](../../administration/using/auditing-export-logs.md)の節を参照してください。

![](assets/do-not-localize/how-to-video.png) [リストの設定方法をビデオで確認](#video)

「リストを書き出し」オプションを使用すると、デフォルトで 100,000 行まで書き出すことができ、**Nms_ExportListLimit** オプションで定義できます。 このオプションは、機能管理者が **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** メニューで管理できます。

書き出しリストは、**[!UICONTROL EXPORT (export)]** の役割を持つユーザーの **リスト** モードビューを持つすべての画面で使用できます。

1. 選択した **リスト** 画面に移動します。 例えば、テストプロファイルの概要画面 ( **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]** )。
1. 画面が **リスト** モードであることを確認します。

   ![](assets/export_list_mode_switch.png)

1. 右上隅の **[!UICONTROL Configure list]** ボタンを使用して、リストの列をエクスポートする順序に整理します。 設定された列に加えて、リソースのプライマリキーもエクスポートされます。
1. 必要に応じて、フィルターを適用できます。 これをおこなうには、左上隅の「 」ボタンをクリックして、検索ペインを表示します。

   異なるリソースを含むリストからエクスポートを実行する場合は、1 つのタイプのリソースのみがリストに表示されるように、フィルターを適用する必要があります。

1. 必要に応じて、選択した列を並べ替えます。
1. エクスポートボタン ![](assets/exportlistbutton.png) を選択します。

   書き出しを確認するポップアップが表示されます。 エクスポートを確認すると、ファイルが自動的にコンピューターにダウンロードされます。

ファイルは CSV 形式で、拡張子に.TXT を付けて生成されます。 この名前は、書き出されたリソースと書き出し日に従って付けられます。 例：profileBase_20150426_120253.txt という名前は、2015 年 4 月 26 日の 12:02:53 に実行されるプロファイルエクスポートに適用されます。 UTF-8 形式でエンコードされます。

数値および日付は、エクスポートを実行するユーザーのローカル時間（ロケール）を考慮に入れます。 例：DD-MM-YYYY または MM-DD-YYYY。

これより大きい書き出しを実行するには、専用のワークフローを作成する必要があります。 [ ファイルの抽出 ](../../automating/using/extract-file.md) の節を参照してください。

**例**

次の例は、以下に定義するプロファイルリストから実行されるエクスポートです。

* 表示される列（順序）:姓、名、生年月日、E メールアドレス。
* 名前はアルファベット順に並べ替えられます。

![](assets/export_list_example1.png)

生成されたファイルは、次のように表示されます（最初の 10 件のレコード）。

```
Last name;First name;Birth date;Email;Zip code
Abalo;Patrick;11/11/1941 02:00:00;patrick.a@testmail.com;29200
Abasq;Joel;21/08/1977 02:00:00;abasq.joel@testmail.com;92160
Abernot;John;12/07/1963 01:00:00;john.abernot@testmail.com;78510
Abiven;Christian;16/03/1975 01:00:00;chris.a@mailtest.com;35000
Abouvier;Peter;02/07/1975 01:00:00;pabouvier@mailtest.com;94560
Accardi;Mike;22/06/1948 01:00:00;mike.accardi@mail.com;76400
Accremont;Frank;27/04/1947 01:00:00;accr.frank@mailtest.com;13500
Adam;Daniel;17/09/1953 01:00:00;danieladam@mail.com;17000
Adama;Pascal;22/01/1990 01:00:00;adapascal@mailtest.com;75012
Adama;Henry;22/09/1992 02:00:00;henry.adama@mail.com;64120
```

**関連トピック：**

* [役割](../../administration/using/list-of-roles.md)
* [リストのカスタマイズ](../../start/using/customizing-lists.md)

## チュートリアルビデオ {#video}

このビデオでは、リストの設定方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/25288/?quality=12)

追加のCampaign Standardハウツービデオは [ こちら ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja) からご覧いただけます。

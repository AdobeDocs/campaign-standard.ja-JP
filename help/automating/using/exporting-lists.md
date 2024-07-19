---
title: リストのエクスポート
description: Adobe Campaignでは、概要画面からリストとして表示されたデータをファイルに直接書き出して、後で使用できます。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: b39ce1f6-0c5b-4270-86a1-b79c49cd199c
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# リストのエクスポート{#exporting-lists}

Adobe Campaignでは、リストをファイルに直接エクスポートして、後で使用できます。 ファイルにリストを書き出すと、**[!UICONTROL Export audits]** メニューにログエントリが生成されます。 エクスポートの監査について詳しくは、[エクスポートの監査](../../administration/using/auditing-export-logs.md)の節を参照してください。

![](assets/do-not-localize/how-to-video.png) [ ビデオでリストを設定する方法を確認する ](#video)

エクスポートリストオプションを使用すると、デフォルトで、**Nms_ExportListLimit** オプションで定義された最大 100,000 行をエクスポートできます。 このオプションは、機能管理者が **[!UICONTROL Administration]** / **[!UICONTROL Application settings]** / **[!UICONTROL Options]** メニューで管理できます。

リストの書き出しは、**[!UICONTROL EXPORT (export)]** の役割を持つユーザー向けに、**リスト** モードのビューを持つすべての画面で使用できます。

1. 選択した **リスト** 画面に移動します。 例えば、テストプロファイルの概要画面（**[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**）が表示されます。
1. 画面が **リスト** モードであることを確認します。

   ![](assets/export_list_mode_switch.png)

1. 右上隅の「**[!UICONTROL Configure list]**」ボタンを使用して、リスト内の列を書き出す順序に整理します。 設定済みの列に加えて、リソースのプライマリキーも書き出されます。
1. 必要に応じて、フィルターを適用できます。 これを行うには、左上隅のボタンをクリックして検索ペインを表示します。

   異なるリソースを含むリストから書き出しを実行する場合は、1 つのタイプのリソースのみがリストに表示されるようにフィルターを適用する必要があります。

1. 選択した列を並べ替えます。
1. 「書き出し」ボタン ![](assets/exportlistbutton.png) を選択します。

   書き出しを確認するポップアップが表示されます。 書き出しを確認すると、ファイルが自動的にコンピューターにダウンロードされます。

ファイルは、拡張子が.TXT の CSV 形式で生成されます。 この名前は、書き出されたリソースと書き出し日に応じて付けられます。 例：名前 profileBase_20150426_120253.txt は、2015 年 4 月 26 日の 12:02:53 に実行されたプロファイル書き出しに適用されます。 UTF-8 形式でエンコードされます。

数値と日付は、書き出しを実行するユーザーのローカル時間（ロケール）を考慮に入れます。 例：DD-MM-YYYY または MM-DD-YYYY

これを超える書き出しを実行するには、専用のワークフローを作成する必要があります。 [ ファイルの抽出 ](../../automating/using/extract-file.md) の節を参照してください。

**例**

次に、以下で定義するプロファイルリストから実行する書き出しの例を示します。

* 表示される列（順序）：姓、名、生年月日、メールアドレス。
* 名前はアルファベット順に並べ替えられます。

![](assets/export_list_example1.png)

生成されるファイルは次のように表示されます（最初の 10 件のレコード）。

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

その他のCampaign Standardチュートリアルビデオについては、[ こちら ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja) を参照してください。

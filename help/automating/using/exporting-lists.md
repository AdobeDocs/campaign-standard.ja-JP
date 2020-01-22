---
title: リストの書き出し
description: 'Adobe Campaignを使用すると、リストとして表示されたデータを概要画面から直接ファイルにエクスポートし、将来の使用に備えることができます。 '
page-status-flag: never-activated
uuid: c64fe706-bd6e-4746-958e-f94226f4e2cb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 12c874da-435f-44b6-a3c8-873301e177cc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# リストの書き出し{#exporting-lists}

Adobe Campaignでは、リストをファイルに直接エクスポートして、将来的に使用できます。 ファイル内のリストを書き出すと、メニューにログエントリが生成さ **[!UICONTROL Export audits]**れます。 エクスポート監査の詳細については、「エクスポートの監査[](../../administration/using/auditing-export-logs.md)」を参照してください。

書き出しリストオプションを使用すると、デフォルトで100,000行まで書き出すことができ、 **Nms_ExportListLimit** オプションで定義できます。 このオプションは、機能管理者が//メニューの下で管 **[!UICONTROL Administration]**理で**[!UICONTROL Application settings]** き **[!UICONTROL Options]**ます。

書き出しリストは、ロールを持つユーザーに対して、リス **トモード** ビューを持つすべての画面で使用で **[!UICONTROL EXPORT (export)]**きます。

1. 選択したリスト画面に **移動** 。 例えば、テストプロファイルの概要画面( **[!UICONTROL Profiles & audiences]**>**[!UICONTROL Test profiles]** )。
1. 画面がリストモードになっていることを **確認します** 。

   ![](assets/export_list_mode_switch.png)

1. リストの列を、右上隅のボタンを使用して、書き出す **[!UICONTROL Configure list]**順序に整理します。 設定済みの列に加えて、リソースの主キーもエクスポートされます。
1. 必要に応じて、フィルターを適用できます。 これを行うには、左上隅のボタンをクリックして検索ペインを表示します。

   異なるリソースを含むリストからエクスポートする場合は、1種類のリソースのみがリストに表示されるようにフィルタを適用する必要があります。

1. 必要に応じて、選択した列を並べ替えます。
1. 書き出しボタンを選択しま ![](assets/exportlistbutton.png)す。

   書き出しを確認するポップアップが表示されます。 書き出しを確認すると、ファイルが自動的にコンピューターにダウンロードされます。

iOSでエクスポートを実行しない限り、ファイルはCSV形式で生成されます。この場合、生成されるファイルはTXT形式です。 この名前は、エクスポートされたリソースとエクスポート日に従って付けられます。 例：profilebase_20150426_120253.csvという名前は、2015年4月26日の12:02:53に実行されるプロファイルエクスポートに適用されます。 UTF-8形式でエンコードされます。

数値と日付は、エクスポートを実行するユーザーのローカル時間（ロケール）を考慮に入れます。 例：DD-MM-YYYYまたはMM-DD-YYYY。

これよりも大きい書き出しを実行するには、専用のワークフローを作成する必要があります。 「ファイルの抽出」の節 [を参照してください](../../automating/using/extract-file.md) 。

**例**

次の例は、以下に定義したプロファイルリストから実行されるエクスポートです。

* 表示される列（順番）:姓、名、生年月日、電子メールアドレス。
* 名前はアルファベット順に並べ替えられます。

![](assets/export_list_example1.png)

生成されるファイルは、次のように表示されます（最初の10件のレコードに対して）。

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
* [リストビデオの設定](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/configure-a-list.html)

---
title: リストの書き出し
seo-title: リストの書き出し
description: リストの書き出し
seo-description: 'Adobe Campaignでは、リストとして表示されたデータを、将来使用できるようにファイル内で直接ファイルに書き出すことができます。 '
page-status-flag: 常にアクティブ化されていない
uuid: c64fe706- bd6e-4746-958e- f94226f4e2cb
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: importing- and- exporting- data
discoiquuid: 12c874da-435f-44b6- a3c8-873301e177cc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Exporting lists{#exporting-lists}

Adobe Campaignでは、後で使用するためにリストをファイル内で直接書き出すことができます。Exporting a list in a file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.

The export list option allows you to export a maximum of 100,000 lines by default and defined by the **Nms_ExportListLimit** option. This option can be managed by the functional administrator, under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]** menu.

Export list is available in all the screens that have a **List** mode view, for users with the **[!UICONTROL EXPORT (export)]** role.

1. Go to your chosen **List** screen. For example, the test profile overview screen ( **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Test profiles]** ).
1. Check that the screen is in **List** mode.

   ![](assets/export_list_mode_switch.png)

1. Organize the columns in the list in the order that you want to export them using the **[!UICONTROL Configure list]** button, in the top right corner. 設定済みの列に加えて、リソースのプライマリキーもエクスポートされます。
1. 必要に応じて、フィルターを適用できます。これを行うには、左上隅のボタンをクリックして検索ペインを表示します。

   異なるリソースを含むリストからエクスポートを実行する場合、リストに1つのリソースしか表示されないようにフィルターを適用する必要があります。

1. 必要に応じて、選択した列を並べ替えます。
1. Select the export button ![](assets/exportlistbutton.png).

   エクスポートを確認するポップアップが表示されます。エクスポートを確認すると、ファイルが自動的にコンピューターにダウンロードされます。

ファイルはCSV形式で生成されますが、iOSではエクスポートが実行されます（この場合、ファイル生成はTXT形式になります）。エクスポートされたリソースとエクスポート日に従って名前が付けられます。次に例を示します。profileBase_20150426_120253. csvという名前は、2015年4月26日26日26日（12:02:53）のプロファイルエクスポートに適用されます。これはUTF-8形式でエンコードされます。

数値および日付は、エクスポートを実行するユーザーのローカル時間（ロケール）を考慮します。次に例を示します。DD- MM- YYYYまたはMM- DD- YYYY。

これより大きいエクスポートを実行するには、専用ワークフローを作成する必要があります。[「ファイルの抽出](../../automating/using/extract-file.md) 」セクションを参照してください。

**例**

次に、以下に定義したプロファイルリストからエクスポートする例を示します。

* 表示される列:姓、名、生年月日、電子メールアドレス。
* 名前はアルファベット順に並べ替えられます。

![](assets/export_list_example1.png)

生成されたファイルは、次のように表示されます（最初の10件のレコード）。

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

**関連トピック:**

* [役割](../../administration/using/list-of-roles.md)
* [リストのカスタマイズ](../../start/using/customizing-lists.md)
* [リストのビデオの設定](https://helpx.adobe.com/campaign/kt/acs/using/acs-configuring-a-list-feature-video-setup.html)


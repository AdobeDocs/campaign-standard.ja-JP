---
solution: Campaign Standard
product: campaign
title: リストの書き出し
description: 'Adobe Campaignを使用すると、リストとして表示されたデータを概要画面から直接ファイルに書き出し、将来的に使用できるようにします。 '
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# リストの書き出し{#exporting-lists}

Adobe Campaignを使用すると、リストをファイルに直接書き出して、将来的に使用できるようになります。 ファイル内のリストを書き出すと、**[!UICONTROL Export audits]**&#x200B;メニューにログエントリが生成されます。 エクスポートの監査について詳しくは、[エクスポートの監査](../../administration/using/auditing-export-logs.md)の節を参照してください。

![](assets/do-not-localize/how-to-video.png) [ビデオでのリストの設定方法の確認](#video)

書き出しリストオプションを使用すると、デフォルトで最大100,000行まで書き出すことができ、**Nms_ExportListLimit**&#x200B;オプションで定義されます。 このオプションは、機能管理者が&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**&#x200B;メニューの下で管理できます。

書き出しリストは、**リスト**&#x200B;表示のあるすべての画面で、**[!UICONTROL EXPORT (export)]**&#x200B;ロールを持つユーザーに対して使用できます。

1. 選択した&#x200B;**リスト**&#x200B;画面に移動します。 例えば、テストプロファイルの概要画面( **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]** )。
1. 画面が&#x200B;**リスト**&#x200B;モードになっていることを確認します。

   ![](assets/export_list_mode_switch.png)

1. 右上隅の&#x200B;**[!UICONTROL Configure list]**&#x200B;ボタンを使用して、リスト内の列を書き出す順序に整理します。 設定済みの列に加えて、リソースの主キーもエクスポートされます。
1. 必要に応じて、フィルターを適用できます。 これを行うには、左上隅のボタンをクリックして検索ペインを表示します。

   異なるリソースを含むリストからエクスポートする場合は、1種類のリソースのみがリストに表示されるように、フィルターを適用する必要があります。

1. 必要に応じて、選択した列を並べ替えます。
1. 書き出しボタン![](assets/exportlistbutton.png)を選択します。

   書き出しを確認するポップアップが表示されます。 書き出しを確認すると、ファイルがコンピューターに自動的にダウンロードされます。

ファイルは.TXT拡張子の付いたCSV形式で生成されます。 エクスポートされたリソースとエクスポート日に従って名前が付けられます。 次に例を示します。profileBase_20150426_120253.txtという名前は、2015年4月26日12:02:53に行われたプロファイルエクスポートに適用されます。 UTF-8形式でエンコードされます。

数値および日付では、エクスポートを実行するユーザーのローカル時間（ロケール）が考慮されます。 次に例を示します。DD-MM-YYYYまたはMM-DD-YYYY。

これより大きい書き出しを実行するには、専用のワークフローを作成する必要があります。 [ファイル](../../automating/using/extract-file.md)の抽出の節を参照してください。

**例**

次の例は、以下に定義するプロファイルリストから実行されるエクスポートです。

* 表示される列（順に）:姓、名、生年月日、電子メールアドレス。
* 名前はアルファベット順に並べ替えられます。

![](assets/export_list_example1.png)

生成されるファイルは次のように表示されます（最初の10件のレコードに対して）。

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

このビデオでは、リストの設定方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/25288/?quality=12)

追加のCampaign Standardハウツービデオは[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)で参照できます。

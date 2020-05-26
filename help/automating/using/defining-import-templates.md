---
title: インポートテンプレートの定義
description: インポートテンプレートを使用すると、必要な設定を減らし、データの読み込みを高速化できます。
page-status-flag: never-activated
uuid: 651eb57c-adac-4e3e-b454-b39aea1f0484
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 85d13147-fb31-446a-8476-f112c841fb82
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 1%

---


# インポートテンプレートの定義{#defining-import-templates}

インポートテンプレートを使用すると、管理者は特定の数の技術的なインポート設定を事前に定義できます。 これらのテンプレートは、標準のユーザがファイルの実行やアップロードを行えるようにすることができます。

インポートテンプレートは、機能管理者が定義し、「/」 **[!UICONTROL Resources]** >「 **[!UICONTROL Templates]** /」 **[!UICONTROL Import templates]** メニューで管理できます。

![](assets/import_template_list.png)

3つのデフォルトの読み取り専用テンプレートを使用できます。

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**: このテンプレートは、ダイレクトメール用に強制隔離と配信ログを更新する新しいインポートの基盤として機能します。 テンプレートのワークフローには、次のアクティビティが含まれます。
* **[!UICONTROL Import data]**: このテンプレートは、新しいインポートの基礎として、ファイルからデータベースにデータを挿入できます。 このテンプレートのワークフローには、次のアクティビティが含まれます。

   * **[!UICONTROL Load file]**: このアクティビティを使用すると、Adobe Campaignサーバーにファイルをアップロードできます。
   * **[!UICONTROL Update data]**: このアクティビティを使用すると、ファイルのデータをデータベースに挿入できます。

* **[!UICONTROL Import list]**: このテンプレートは、ファイル内のデータから **リスト** 型オーディエンスを作成する新しいインポートの基本として機能します。 このテンプレートのワークフローには、次のアクティビティが含まれます。

   * **[!UICONTROL Load file]**: このアクティビティを使用すると、Adobe Campaignサーバーにファイルをアップロードできます。
   * **[!UICONTROL Reconciliation]**: このアクティビティを使用すると、ターゲティングディメンションを読み込んだデータにリンクできます。 これにより、 **リストタイプのオーディエンスを作成できます** 。 読み込んだデータのターゲティングディメンションが不明な場合、オーディエンスは **File** typeです。 「 [ターゲティングディメンションとリソース](../../automating/using/query.md#targeting-dimensions-and-resources)」を参照してください。
   * **[!UICONTROL Save audience]**: このアクティビティを使用すると、 **リストタイプのオーディエンスの形式でインポートしたデータを保存できます** 。 保存されたオーディエンスの名前は、ユーザーが読み込んだファイルの名前に対応し、読み込みの日時を指定するサフィックスが追加されます。 次に例を示します。 &#39;プロファイル_20150406_151448&#39;。

これらのデフォルトのテンプレートは読み取り専用で、標準ユーザーには表示されません。 ユーザーが使用できるテンプレートを作成するには、次の手順に従います。

1. デフォルトの重複を作成します。 複製されたテンプレートには3つのタブが含まれています。

   * **[!UICONTROL Properties]**: インポートテンプレートの一般的なパラメーター。 このタブでは、テンプレートを有効にし、サンプルファイルをアップロードできます。
   * **[!UICONTROL Workflow]**: 読み込みワークフローを参照してください。 このタブでは、ワークフローのアクティビティを定義できます。 これらのアクティビティは、ユーザーが簡単にインポートした場合には表示されません。
   * **[!UICONTROL Executed imports]**: このテンプレートを使用して実行されたインポートのリスト。 このテンプレートを使用して実行された各インポートのステータス、詳細、および結果を表示できます。 このリストから直接ワークフローにアクセスできます（ユーザーに対して透過的に実行される）。

1. タブから、テンプレートの名前を変更し、説明を追加し **[!UICONTROL Properties]** ます。 テンプレートが使用可能になると、ユーザーは説明を表示できます。

   ![](assets/simplified_import_model1.png)

1. Go to the **[!UICONTROL Workflow]** tab. 必要に応じて新しいアクティビティを追加することで、デフォルトで提供されるワークフローをここから拡張できます。

   ワークフローアクティビティを設定する方法の詳細については、この節の使用例を参照してください。 [例： ワークフローテンプレートの読み込み](../../automating/using/creating-import-workflow-templates.md)。 この使用例は、Adobe CampaignデータベースのCRMから来たプロファイルをインポートする際に再利用できるワークフローを設定する場合に役立ちます。

1. ワークフローの設定が正しく考慮されるように、テンプレートを保存します。
1. タブからサンプルファイルをアップロードし **[!UICONTROL Properties]** ます。 アップロードされたファイルには、今後のインポートやサンプルデータに必要な列のみを含めることができます。 サンプルファイルのデータを使用すると、ワークフローを定義した後、シンプル化されたインポートをテストできます。

   ![](assets/import_template_sample.png)

   このサンプルファイルは、テンプレートを使用して読み込みを行うユーザーが使用できるようになります。 例えば、読み込むデータを入力するために、自分のコンピューターにダウンロードできます。 サンプルファイルを追加する場合は、この点を考慮してください。

1. テンプレートを保存します。 これで、サンプルファイルが考慮されます。 いつでもコンピュータにダウンロードしてコンテンツを確認したり、 **[!UICONTROL Drop a new sample file]** オプションを確認して変更したりできます。

   ![](assets/simplified_import_model2.png)

1. タブに戻り、 **[!UICONTROL Workflow]****[!UICONTROL Load file]** アクティビティを開いて、前の手順でアップロードしたサンプルファイルの列設定を確認し、調整します。
1. ワークフローを開始して、インポートをテストします。 手順 **5でアップロードしたサンプルファイルには、データを含める必要があり** ます。

   次に、サンプルファイルのデータが正しく読み込まれます。 使用するデータが小さく架空のものであり、データベースに問題が発生しないことを確認してください。

1. アクションバーにあるワークフロー実行ログに移動します。 エラーが発生した場合は、アクティビティが正しく設定されていることを確認してください。

   ![](assets/simplified_import_model3.png)

1. タブで、をに設定 **[!UICONTROL Properties]** し **[!UICONTROL Import template status]****[!UICONTROL Available]**&#x200B;て、テンプレートを保存します。 このテンプレートの使用を停止するには、をに設定 **[!UICONTROL Import template status]** し **[!UICONTROL Archived]**&#x200B;ます。

テンプレートワークフローを変更するには、サンプルファイルを再度アップロードし、設定を確認します。 **[!UICONTROL Load file]**

これで、インポートテンプレートがユーザーに提供され、ファイルのアップロードに使用できるようになります。

**関連トピック：**

* [ワークフロー](../../automating/using/get-started-workflows.md)
* [データのインポートおよびエクスポート](../../automating/using/about-data-import-and-export.md)
* [例： ワークフローテンプレートの読み込み](../../automating/using/creating-import-workflow-templates.md)


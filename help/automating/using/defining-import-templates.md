---
title: インポートテンプレートの定義
description: テンプレートの読み込みを使用すると、必要な設定を減らし、データの読み込みを高速化できます。
page-status-flag: 非活性化の
uuid: 651eb57c-adac-4e3e-b454-b39aea1f0484
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: データのインポート/エクスポート
discoiquuid: 85d13147-fb31-446a-8476-f112c841fb82
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# インポートテンプレートの定義{#defining-import-templates}

インポートテンプレートを使用すると、管理者は特定の数の技術インポート設定を事前に定義できます。 これらのテンプレートは、標準ユーザがファイルの実行とアップロードを行えるようにすることができます。

インポートテンプレートは、機能管理者が定義し、 &gt; &gt;メニューで管 **[!UICONTROL Resources]** 理で **[!UICONTROL Templates]** き **[!UICONTROL Import templates]** ます。

![](assets/import_template_list.png)

3つのデフォルトの読み取り専用テンプレートを使用できます。

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**:このテンプレートは、検疫およびダイレクトメールの配信ログを更新する新しいインポートの基盤として機能します。 テンプレートのワークフローには、次のアクティビティが含まれます。
* **[!UICONTROL Import data]**:このテンプレートは、ファイルからデータベースにデータを挿入する新しいインポートの基盤となります。 このテンプレートのワークフローには、次のアクティビティが含まれます。

   * **[!UICONTROL Load file]**:このアクティビティにより、Adobe Campaignサーバーにファイルをアップロードできます。
   * **[!UICONTROL Update data]**:このアクティビティを使用すると、ファイルからデータベースにデータを挿入できます。

* **[!UICONTROL Import list]**:このテンプレートは、ファイル内のデータから **List** typeオーディエンスを作成する新しいインポートの基盤として機能します。 このテンプレートのワークフローには、次のアクティビティが含まれます。

   * **[!UICONTROL Load file]**:このアクティビティにより、Adobe Campaignサーバーにファイルをアップロードできます。
   * **[!UICONTROL Reconciliation]**:このアクティビティを使用すると、インポートしたデータにターゲットディメンションをリンクできます。 これにより、リストタイプのオーディエンスを **作成でき** ます。 読み込んだデータのターゲットディメンションが不明な場合、オーディエンスは **File** typeです。 ディメンショ [ンとリソースのターゲット設定を参照してくださ](../../automating/using/query.md#targeting-dimensions-and-resources)い。
   * **[!UICONTROL Save audience]**:このアクティビティでは、 **Listタイプのオーディエンスの形式でインポートしたデータを保存で** きます。 保存済みのオーディエンスの名前は、ユーザーが読み込んだファイルの名前に対応し、読み込みの日時を指定するサフィックスが追加されます。 例：'profiles_20150406_151448'.

これらのデフォルトのテンプレートは読み取り専用で、標準ユーザーには表示されません。 ユーザーが使用できるテンプレートを作成するには、次の手順に従います。

1. デフォルトのテンプレートを複製します。 複製されたテンプレートには3つのタブが含まれます。

   * **[!UICONTROL Properties]**:インポートテンプレートの一般パラメータ。 このタブでは、テンプレートを有効にし、サンプルファイルをアップロードできます。
   * **[!UICONTROL Workflow]**:インポートワークフローを参照してください。 このタブでは、ワークフローアクティビティを定義できます。 これらのアクティビティは、ユーザーが実行したシンプルなインポートでは表示されません。
   * **[!UICONTROL Executed imports]**:このテンプレートを使用して実行されたインポートのリストです。 このテンプレートを使用して実行された各インポートのステータス、詳細および結果を表示できます。 このリストから直接ワークフローにアクセスできます（ユーザーに対して透過的に実行されます）。

1. タブから、テ **[!UICONTROL Properties]** ンプレートの名前を変更し、説明を追加します。 テンプレートが使用可能になると、ユーザーは説明を表示できます。

   ![](assets/simplified_import_model1.png)

1. Go to the **[!UICONTROL Workflow]** tab. ここから、ニーズに応じて新しいアクティビティを追加することで、デフォルトで提供されるワークフローを強化できます。

   ワークフローアクティビティの設定方法について詳しくは、この節で説明する使用例を参照してください。 [例：ワークフローテンプレートの読み込み](../../automating/using/importing-data.md#example--import-workflow-template)。 この使用例は、Adobe CampaignデータベースのCRMからのプロファイルのインポートで再利用できるワークフローの設定に役立ちます。

1. ワークフローの設定が正しく考慮されるように、テンプレートを保存します。
1. タブからサンプルファイルをアップロード **[!UICONTROL Properties]** します。 アップロードされたファイルには、今後のインポートやサンプルデータに必要な列のみを含めることができます。 ワークフローを定義すると、サンプルファイル内のデータを使用して、シンプル化されたインポートをテストできます。

   ![](assets/import_template_sample.png)

   このサンプルファイルは、テンプレートを使用してインポートを実行するユーザーが使用できるようになります。 例えば、読み込むデータを入力するために、コンピューターにダウンロードできます。 サンプルファイルを追加する際は、この点を考慮してください。

1. テンプレートを保存します。 これでサンプルファイルが考慮されました。 コンピューターにダウンロードしてコンテンツを確認したり、オプションを選択して変更したりでき **[!UICONTROL Drop a new sample file]** ます。

   ![](assets/simplified_import_model2.png)

1. タブに戻り、ア **[!UICONTROL Workflow]** クティビティを開 **[!UICONTROL Load file]** いて、前の手順でアップロードされたサンプルファイルの列設定を確認し、調整します。
1. ワークフローを開始して、インポートをテストします。 手順 **5でアップロードしたサンプルファイルには** 、データが含まれている必要があります。

   次に、サンプルファイルのデータが正しく読み込まれます。 使用するデータが小さく、架空のものであることを確認して、データベースに問題がないようにしてください。

1. アクションバーにあるワークフロー実行ログに移動します。 エラーが発生した場合は、アクティビティが正しく設定されていることを確認します。

   ![](assets/simplified_import_model3.png)

1. タブで、 **[!UICONTROL Properties]** をに設定し、テ **[!UICONTROL Import template status]** ンプ **[!UICONTROL Available]**&#x200B;レートを保存します。 このテンプレートの使用を停止するには、をに設定 **[!UICONTROL Import template status]** しま **[!UICONTROL Archived]**&#x200B;す。

テンプレートワークフローは、サンプルファイルを再度アップロードし、設定を確認することで変更で **[!UICONTROL Load file]** きます。

これで、読み込みテンプレートがユーザに提供され、ファイルのアップロードに使用できるようになりました。

**関連トピック：**

* [ワークフロー](../../automating/using/discovering-workflows.md)
* [データのインポート](../../automating/using/importing-data.md)
* [例：ワークフローテンプレートの読み込み](../../automating/using/importing-data.md#example--import-workflow-template)


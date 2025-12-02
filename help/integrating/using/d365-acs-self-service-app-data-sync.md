---
title: Campaign とMicrosoft Dynamics間のデータ同期
description: Campaign と Dynamics 間のデータ同期
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 66623c76-96aa-45cd-9637-19d8a9732c04
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '1839'
ht-degree: 0%

---

# データの同期

Microsoft Dynamics 365 のテーブルを Campaign と Campaign のマーケティング指標に同期して、Microsoft Dynamics 365 に同期させることができます。 同期は、**[!UICONTROL Microsoft Dynamics 365 to Campaign]**、**[!UICONTROL Campaign to Microsoft Dynamics 365]**、**[!UICONTROL Opt-In/Out]** の 3 つの専用のテクニカルワークフローを通じて実行されます。 詳しくは、この節を参照してください [ 詳細情報 ](../../integrating/using/d365-acs-self-service-app-workflows.md)。

>[!IMPORTANT]
>変更を反映させるには、**[!UICONTROL Microsoft Dynamics 365 to Campaign]** ワークフローを停止または開始する必要があります。 [詳細情報](../../integrating/using/d365-acs-self-service-app-workflows.md)
>

## Microsoft Dynamics 365 から Campaign へのテーブルのマッピング

**[!UICONTROL Microsoft Dynamics 365 to Campaign]** のページには、Microsoft Dynamics 365 内のエンティティのリストと、エンティティが同期されるAdobe Campaign内のカスタムリソースが表示されます。 新しいマッピングを追加したり、既存のマッピングを編集または削除したりできます。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

この表の各列の説明を次に示します。

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**：この列は、マッピングのデータのソースとなるMicrosoft Dynamics 365 のエンティティを示します。

* **[!UICONTROL CAMPAIGN TABLE]**：この列は、マッピングのデータ先となるAdobe Campaignのリソースを示します。

* **[!UICONTROL ACTIONS]**：可能なアクションを以下に示します。

   * **[!UICONTROL Edit]** アイコンをクリックして、このマッピングを編集します。

   * テーブルマッピングを削除するには、「**[!UICONTROL Delete]**」アイコンを使用します。

   * **[!UICONTROL Replay Data]** アイコンをクリックして、Microsoft Dynamics 365 テーブルのすべてのデータを再同期します。 通常、統合アプリケーションは、最近変更されたMicrosoft Dynamics 365 のデータのみを同期します。  ただし、場合によっては（変更を加えた、間違いをした、など）、すべてのデータを再同期する必要が生じることがあります。  この場合、このボタンをクリックすると、次に **[!UICONTROL Microsoft Dynamics 365 to Campaign]** ワークフローを停止または開始したときに、データの同期が開始されます。

     「**[!UICONTROL Replay Data]**」ボタンをクリックしてチェックに成功すると、アイコンが無効になります。これは、**[!UICONTROL Microsoft Dynamics 365 to Campaign]** ワークフローの次回の実行で、このテーブルマッピングペアのデータが再同期されることを示しています。

     次の条件に当てはまる場合は、データの再生を選択できません。

      * **[!UICONTROL Microsoft Dynamics 365 to Campaign]** ワークフロー（**[!UICONTROL Workflows]** ページに表示）に関連付けられたバックログ指標に 2,000,000 （またはそれ以上）の項目がある場合
      * Microsoft Dynamics 365 テーブルに 200 万件以上のレコードがある場合

     再同期が必要なレコードの数は異なります。 レコード数が多い場合は、同期プロセスが完了するまでに時間がかかることがあります。 統合アプリケーションが同期プロセスを完了するように動作するので、**[!UICONTROL Backlog]** ページの **[!UICONTROL Workflows]** の指標を参照してください。

     >[!IMPORTANT]
     >
     > Adobe Campaign StandardまたはMicrosoft Dynamics 365 に変更内容を公開する際は、統合ワークフローを停止することを強くお勧めします。 適用可能な変更：リソース/エンティティ（およびその関連フィールド）の更新、リンク、識別子の列など。 は、現在、統合で使用されています。
     >

## 新しいマッピングを作成 {#add-a-new-mapping}

新しいマッピングを作成するには、次の手順に従います。

1. **[!UICONTROL Microsoft Dynamics 365 to Campaign]** ページで、「**[!UICONTROL Add New Mapping]**」ボタンをクリックします。

1. ドロップダウンリストを使用して、Microsoft Dynamics 365 とマッピングする Campaign テーブルを選択します。
ページ上のその他の入力のほとんどは、選択したテーブルによって異なります。

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >各テーブルを複数回マッピングすることはできません。 そのため、ドロップダウン選択には、既にマッピングされているテーブルが含まれないことに注意してください。

1. **[!UICONTROL OK]** をクリックして確認します。選択したテーブルに関連付けられているフィールド情報を読み込むには、アプリケーションにしばらく時間がかかります。

その後、マッピング設定を続行できます。 [詳細情報](#new-mapping-settings)

>[!IMPORTANT]
>
>このページで選択できるのは、マッピングを最初に追加する際のみです。 「**[!UICONTROL Save]**」ボタンをクリックする前に、正しいテーブルを選択していることを確認します。保存すると、テーブル選択フィールドは **読み取り専用** になります。

### 既存のマッピングを編集

既存のマッピングを編集すると、テーブルの選択が編集できないことがわかります。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

これは意図的なもので、ページの下部にある入力は、これらのテーブルに関連付けられたフィールドに基づくからです。 テーブルを変更すると、これらのテーブルに関連付けられているすべてのフィールドが無効になります。  マッピング先のテーブルを変更する場合は、前のページに戻り、変更するマッピングを削除して、新しいマッピングを追加する必要があります。

### 個々のテーブルマッピングの設定 {#new-mapping-settings}

この節では、1 つのMicrosoft Dynamics 365 テーブルから 1 つのAdobe Campaign テーブルへの **シングル** マッピングを設定する方法について説明します。

次の設定を定義できます。

* **[!UICONTROL Tables]**：このセクションには、Microsoft Dynamics 365 テーブルの名前と、そのテーブルのマッピング先となる Campaign テーブルが一覧表示されます。
* **[!UICONTROL Field Mappings]**：詳しくは、[ この節 ](#field-mappings) を参照してください
* **[!UICONTROL Field Replacements]**：詳しくは、[ この節 ](#field-replacements) を参照してください
* **[!UICONTROL Filters]**：詳しくは、[ この節 ](#filters) を参照してください
* **[!UICONTROL Advanced Settings]**：詳しくは、[ この節 ](#advanced-settings) を参照してください

### フィールドマッピング {#field-mappings}

#### プライマリキー

新しいMicrosoft Dynamics 365 を Campaign テーブルマッピングに追加する場合、ID フィールドを特定する必要があります。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

Microsoft Dynamics 365 のプライマリキーは、アプリケーションで検出されるので、読み取り専用です。

Campaign の場合は、一意のキーにするフィールドを選択する必要があります。 [CRM ID カスタムリソース ](../../developing/using/uc-calling-resource-id-key.md) として設定する必要があり、重複がないようにする必要があります。

>[!NOTE]
>
>テーブルの ID フィールドは、**[!UICONTROL Add New Mapping]** を選択した場合にのみ選択できます。 「編集」ボタンをクリックして既存のテーブルマッピングを編集すると、「ID」フィールドは読み取り専用になります。

プライマリキーは、常に「**[!UICONTROL Field Mappings]**」セクションにリストされる最初のフィールド名になります。 次のアイコンが右側に表示され、これがプライマリキーであることを示しています。

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### 他のフィールドマッピングの追加

**[!UICONTROL Field Mappings]** セクションでは、プライマリキー以外のフィールドマッピングを追加できます。 Microsoft Dynamics 365 からAdobe Campaignにフィールドの新しいマッピングを追加するには、「**[!UICONTROL Add new field mapping]**」ボタンをクリックします。

Microsoft Dynamics 365 および Campaign のフィールドをリストから選択します。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

これらのリストには、ページ上部で選択したMicrosoft Dynamics 365 および Campaign テーブルに関連付けられているフィールド名が含まれています。

**[!UICONTROL Apply updates]** スイッチャーを使用すると、このフィールドに対する更新をMicrosoft Dynamics 365 から Campaign に反映するかどうかを制御できます。
* ![](assets/do-not-localize/d365-to-acs-icon-switch-on.png) にオンになっている場合、Microsoft Dynamics 365 の値に対する更新は、更新がおこなわれるたびにAdobe Campaignに反映されます。

* ![](assets/do-not-localize/d365-to-acs-icon-switch-off.png) をオフにした場合、データが最初に読み込まれる（または再生される）ときに値が反映されますが、Microsoft Dynamics 365 のフィールドに対する増分更新は反映されません。

>[!NOTE]
>
>**[!UICONTROL Apply updates]** 列の見出しをクリックして、スイッチの **すべて** をオンまたはオフに更新します。
>

フィールド値を選択すると、ドロップダウンメニューの下にデータタイプが表示されます。   これは、あるフィールドから別のフィールドに値をマッピングする際に留意すべきことです。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> 複数のMicrosoft Dynamics 365 フィールドを 1 つの Campaign フィールドにマッピングすることはできません。

### フィールドの置換 {#field-replacements}

「**[!UICONTROL Add New Field Replacement]**」ボタンを使用して、新しいフィールド置換を定義します。

フィールド置換を使用すると、次の項目を識別できます。

* Microsoft Dynamics 365 フィールド名（上記の「フィールドマッピング」セクションで追加されたもの）
* 既存の値（Microsoft Dynamics 365 に存在）、
* Adobe Campaignに書き込む新しい値

選択リスト、列挙およびブール値用のドロップダウンリストが提供されます。 テキストボックスは、他の文字列タイプや数値タイプにも使用されます。

### フィルター {#filters}

「**[!UICONTROL Add New Filter]**」ボタンを使用して、Campaign に生成するMicrosoft Dynamics 365 レコードを選択します。 フィルターに追加するレコードに関連付けられた任意のフィールドを選択できます（フィールド名をフィールドマッピングに追加する必要はありません）。

フィルターを指定するには、次の情報を入力します。

* Microsoft Dynamics 365 フィールド名
* 比較値、および
* 値（Microsoft Dynamics 365 から）
特定のレコードに対してフィールド名、比較および値が true と評価された場合、レコードはAdobe Campaignに反映されます。

**[!UICONTROL Choose the filter comparison operator]** というラベルの付いた入力を設定することで、これらのフィルターの評価方法を選択できます。  **And** を選択した場合、レコードが Campaign に反映されるためには、すべてのフィルターが true である必要があります。 **Or** を選択すると、いずれかの値が true と評価された場合にレコードが反映されます。

**[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]** のオプションは、除外されたレコードを Campaign から削除するかどうかを制御します。 「**いいえ** を選択した場合、レコードはAdobe Campaignに残ります。 「**はい**」を選択して、統合ロジックで削除されるようにします。

>[!NOTE]
>
> フィルターを追加しない場合、変更されたすべてのレコードがAdobe Campaignに反映されます。
>

### 詳細設定 {#advanced-settings}

マッピングを設定する際には、次の追加オプションを設定できます。

* Microsoft Dynamics 365 で発生した削除を（フィールド名のマッピングに基づいて **[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]** Adobe Campaignの対応するフィールドに反映する場合は、「**」オプションを「** はい」に設定します。 Microsoft Dynamics 365 で削除を無視する場合は、「**いいえ**」を選択します。

* Microsoft Dynamics 365 選択リストに関連付けられた表示値を Campaign に反映する場合は、「**[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]**」オプションを「**いいえ**」に設定します。 **はい** を選択して、テクニカル値を反映させます。

## Campaign マーケティングイベントのMicrosoft Dynamics 365 への同期

**[!UICONTROL Campaign to Microsoft Dynamics 365]** のページでは、Adobe CampaignからMicrosoft Dynamics 365 にマッピングするメールマーケティングイベントを指定できます。

制御できる 4 つの指標は、**送信数**、**クリック数**、**開封数**、**バウンス数** です。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

**はい** を選択して、そのタイプのイベントをMicrosoft Dynamics 365 にフローすることを確認します。

これらのメールイベントフローについて詳しくは、[ ここ ](../../integrating/using/d365-acs-self-service-app-workflows.md) をクリックしてください。

## オプトイン/オプトアウトワークフロー {#opt-in-out-wf}

**オプトイン/オプトアウト** ワークフローを使用すると、Microsoft Dynamics 365 とAdobe Campaignの間のオプトイン/オプトアウト情報のフローを特定できます。 これは、データがMicrosoft Dynamics 365 エンティティ「連絡先」およびAdobe Campaign リソース「プロファイル」に関連付けられていることを前提としています。

オプトアウト管理の詳細については、[ この節 ](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out) を参照してください。

選択内容を保存するには、「保存」をクリックする必要があります。 また、**Microsoft Dynamics 365 に対するキャンペーン** ワークフローを停止し、「再生」をクリックして統合の変更内容を組み込む必要があります。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### オプトイン/オプトアウトの同期方向

データの同期に使用できるオプションのリストを以下に示します。

* **[!UICONTROL Disabled]**：このオプションを選択すると、Adobe CampaignとMicrosoft Dynamics 365 の間でオプトイン/オプトアウト情報が移動しません。

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**：このオプションは、Microsoft Dynamics 365 からAdobe Campaignへのオプトイン/オプトアウトにのみ使用されます。 統合アプリケーションでは、この画面でフローを設定することはできません。代わりに、**[!UICONTROL Save button]** をクリックして、**[!UICONTROL Microsoft Dynamics 365 to Campaign]** ワークフローに移動します。 このワークフローでは、連絡先/プロファイルテーブルのマッピングを編集して、オプトイン/オプトアウトフィールドのマッピング方法を特定できます。

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**：このオプションを選択すると、「**マッピング** セクションが表示されます。 これらの入力を使用すると、Microsoft Dynamics 365 のどのフィールドにデータをマッピングするかをAdobe Campaign フィールドで定義できます。 つまり、Microsoft Dynamics 365 で値を手動で更新すると、変更があった場合に、その値がAdobe Campaignの値で上書きされます。

* **[!UICONTROL Bidirectional]**：このオプションを選択すると、「**マッピング** セクションが表示されます。 これらのペアは、Microsoft Dynamics 365 とAdobe Campaignのどのフィールドを相互にマッピングするかを識別します。 [詳細情報](../../integrating/using/d365-acs-notices-and-recommendations.md)。

### マッピング

この節は、「オプトイン/オプトアウト同期方向」フィールドが「**[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**」または「**[!UICONTROL Bidirectional]**」に設定されている場合にのみ適用されます。 Microsoft Dynamics 365 のどのフィールドをAdobe Campaignのどの入力にマッピングするかを定義できます。

Microsoft Dynamics 365 のフィールド名には、型 **boolean** のすべてのフィールド名が含まれています。

Adobe Campaign フィールド名は、オプトイン/オプトアウトに固有の固定の値セットです。 Adobe Campaign フィールド名は、オプトイン/オプトアウトに固有の固定の値セットです。 **このリストの値セットは変更できません**。

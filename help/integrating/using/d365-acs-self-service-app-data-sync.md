---
title: Campaign とMicrosoft Dynamics 間のデータの同期
description: Campaign と Dynamics の間でのデータの同期
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 66623c76-96aa-45cd-9637-19d8a9732c04
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1795'
ht-degree: 0%

---

# データの同期

Microsoft Dynamics 365 のテーブルを Campaign および Campaign のマーケティング指標とMicrosoft Dynamics 365 に同期できます。 同期は、次の 3 つの専用テクニカルワークフローを通じて実行されます。 **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, **[!UICONTROL Campaign to Microsoft Dynamics 365]**, **[!UICONTROL Opt-In/Out]**. この節を参照して、 [詳細情報](../../integrating/using/d365-acs-self-service-app-workflows.md).

>[!IMPORTANT]
>を停止/開始する必要があります **[!UICONTROL Microsoft Dynamics 365 to Campaign]** ワークフローを使用して、変更を反映させることができます。 [詳細情報](../../integrating/using/d365-acs-self-service-app-workflows.md)

## Microsoft Dynamics 365 から Campaign へのテーブルのマッピング

この **[!UICONTROL Microsoft Dynamics 365 to Campaign]** ページには、Microsoft Dynamics 365 のエンティティのリストと、それらが同期されるAdobe Campaignのカスタムリソースが表示されます。 新しいマッピングの追加、既存のマッピングの編集または削除をおこなうことができます。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

この表の各列の説明を次に示します。

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**:この列は、マッピングのデータソースとなるMicrosoft Dynamics 365 のエンティティを識別します。

* **[!UICONTROL CAMPAIGN TABLE]**:この列は、マッピングのデータの宛先となるAdobe Campaignのリソースを識別します。

* **[!UICONTROL ACTIONS]**:実行可能なアクションを次に示します。

   * 次をクリック： **[!UICONTROL Edit]** アイコンをクリックして、このマッピングを編集します。

   * 以下を使用：  **[!UICONTROL Delete]** アイコンをクリックし、テーブルマッピングを削除します。

   * 次をクリック： **[!UICONTROL Replay Data]** アイコンをクリックして、Microsoft Dynamics 365 テーブル内のすべてのデータを再同期します。 通常、統合アプリケーションは最近変更されたMicrosoft Dynamics 365 のデータのみを同期します。  ただし、場合によっては（変更を加えた場合や誤った場合など）、すべてのデータを再同期させたい場合があります。  この場合、次回、を停止または開始する際に、このボタンをクリックし、 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** ワークフローで、データの同期が開始されます。

      次の項目をクリックした場合、 **[!UICONTROL Replay Data]** ボタンがクリックされ、チェックが正常に完了すると、アイコンが無効になります。これは、このテーブルマッピングペアのデータが、次の **[!UICONTROL Microsoft Dynamics 365 to Campaign]** ワークフロー。

      次の条件に当てはまる場合は、データの再生を選択できません。

      * バックログ指標に 2,000,000 個以上の項目がある場合、 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** ワークフロー ( **[!UICONTROL Workflows]** ページ )
      * Microsoft Dynamics 365 テーブルに 2,000,000 以上のレコードがある場合

      再同期が必要なレコードの数は、それぞれ異なります。 レコード数が多い場合は、同期プロセスの完了に時間がかかる場合があります。 詳しくは、 **[!UICONTROL Backlog]** 指標 **[!UICONTROL Workflows]** ページを開きます。

      >[!IMPORTANT]
      >
      > Adobe Campaign StandardまたはMicrosoft Dynamics 365 に変更を公開する際に、統合ワークフローを停止することを強くお勧めします。 適用される変更は次のとおりです。リソース/エンティティ（および関連するフィールド）、リンク、識別子列などの更新 現在統合で使用中の


## 新しいマッピングを作成 {#add-a-new-mapping}

新しいマッピングを作成するには、次の手順に従います。

1. 内 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** ページで、 **[!UICONTROL Add New Mapping]** 」ボタンをクリックします。

1. ドロップダウンリストを使用して、マッピングするMicrosoft Dynamics 365 および Campaign テーブルを選択します。
ページ上のその他の入力のほとんどは、選択したテーブルによって異なります。

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >各テーブルを複数回マッピングすることはできません。 そのため、ドロップダウンで選択した項目には、既にマッピングされているテーブルは含まれません。

1. クリック **[!UICONTROL OK]** 確認するには：選択したテーブルに関連付けられたフィールド情報を読み込むには、少しの時間が必要です。

その後、マッピング設定を続行できます。 [詳細情報](#new-mapping-settings)

>[!IMPORTANT]
>
>最初にマッピングを追加するときにのみ、このページでテーブルを選択できます。 正しいテーブルが選択されていることを確認してから、 **[!UICONTROL Save]** ボタン：保存すると、テーブル選択フィールドは **読み取り専用**.

### 既存のマッピングの編集

既存のマッピングを編集すると、テーブルの選択は編集できないことがわかります。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

ページの下の方の入力は、これらのテーブルに関連付けられたフィールドに基づいているので、これは設計によるものです。 テーブルを変更すると、これらのテーブルに関連付けられているすべてのフィールドが無効になります。  マッピング先のテーブルを変更する場合は、前のページに戻り、変更するマッピングを削除し、新しいマッピングを追加する必要があります。

### 個々のテーブルマッピングの設定 {#new-mapping-settings}

この節では、 **シングル** 1 つのMicrosoft Dynamics 365 テーブルの 1 つのAdobe Campaignテーブルへのマッピング。

次の設定を定義できます。

* **[!UICONTROL Tables]**:このセクションには、Microsoft Dynamics 365 テーブルの名前と、マッピング先の Campaign テーブルが一覧表示されます。
* **[!UICONTROL Field Mappings]**:詳しくは、 [この節](#field-mappings)
* **[!UICONTROL Field Replacements]**:詳しくは、 [この節](#field-replacements)
* **[!UICONTROL Filters]**:詳しくは、 [この節](#filters)
* **[!UICONTROL Advanced Settings]**:詳しくは、 [この節](#advanced-settings)

### フィールドマッピング {#field-mappings}

#### プライマリキー

新しいMicrosoft Dynamics 365 を Campaign テーブルマッピングに追加する場合は、ID フィールドを識別する必要があります。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

Microsoft Dynamics 365 プライマリキーは、アプリケーションが検出するので、読み取り専用です。

Campaign の場合、一意のキーとなるフィールドを選択する必要があります。 これは、 [CRM ID カスタムリソース](../../developing/using/uc-calling-resource-id-key.md) とは重複していない必要があります。

>[!NOTE]
>
>テーブルで ID フィールドを選択できるのは、 **[!UICONTROL Add New Mapping]**. 編集ボタンをクリックして既存のテーブルマッピングを編集した場合、ID フィールドは読み取り専用になります。

プライマリキーは、常に **[!UICONTROL Field Mappings]** 」セクションに入力します。 右側に次のアイコンが表示され、これらが主キーであることを示します。

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### 他のフィールドマッピングを追加

この **[!UICONTROL Field Mappings]** 「 」セクションでは、「キーのプライマリ」以外のフィールドマッピングを追加できます。 フィールドの新しいマッピングをMicrosoft Dynamics 365 からAdobe Campaignに追加するには、 **[!UICONTROL Add new field mapping]** 」ボタンをクリックします。

リストの「 Microsoft Dynamics 365 」フィールドと「 Campaign 」フィールドを選択します。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

これらのリストには、ページ上部で選択したMicrosoft Dynamics 365 および Campaign テーブルに関連付けられたフィールド名が含まれます。

この **[!UICONTROL Apply updates]** switcher を使用すると、このフィールドに対する更新をMicrosoft Dynamics 365 から Campaign に反映するかどうかを制御できます。
* 電源が入っている場合 ![](assets/do-not-localize/d365-to-acs-icon-switch-on.png)の場合、Microsoft Dynamics 365 の値の更新は、更新がおこなわれるとAdobe Campaignに反映されます。

* 電源を切った場合 ![](assets/do-not-localize/d365-to-acs-icon-switch-off.png)の値は、データが最初に読み込まれたとき（または再生されたとき）に反映されますが、Microsoft Dynamics 365 のフィールドに対する増分更新は反映されません。

>[!NOTE]
>
>をクリックします。 **[!UICONTROL Apply updates]** 更新する列見出し **すべて** をオンまたはオフにします。

フィールド値を選択すると、ドロップダウンメニューの下にデータタイプが表示されます。   これは、あるフィールドから別のフィールドに値をマッピングする際に注意すべきことです。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> 複数のMicrosoft Dynamics 365 フィールドを 1 つの Campaign フィールドにマッピングすることはできません。

### フィールド置換 {#field-replacements}

以下を使用： **[!UICONTROL Add New Field Replacement]** ボタンをクリックして、新しいフィールド置換を定義します。

フィールド置き換えでは、次の項目を識別できます。

* Microsoft Dynamics 365 フィールド名（上記のフィールドマッピングセクションで追加された名前）
* (Microsoft Dynamics 365 に存在する ) 既存の値
* Adobe Campaignに書き込む新しい値

選択リスト、列挙、ブール値のドロップダウンリストが表示されます。 テキストボックスは、他の文字列タイプや数値タイプに使用されます。

### フィルター {#filters}

以下を使用： **[!UICONTROL Add New Filter]** ボタンをクリックして、Campaign に反映するMicrosoft Dynamics 365 レコードを選択します。 フィルターに追加するレコードに関連付けられている任意のフィールドを選択できます（フィールド名をフィールドマッピングに追加する必要はありません）。

次の情報を入力して、フィルターを指定します。

* Microsoft Dynamics 365 フィールド名
* 比較値
* 値 (Microsoft Dynamics 365 の値 ) フィールド名、比較および値が特定のレコードに対して true と評価される場合、レコードはAdobe Campaignに反映されます。

これらのフィルターの評価方法は、「 **[!UICONTROL Choose the filter comparison operator]**.  次を選択した場合： **および**&#x200B;レコードを Campaign に反映させるには、すべてのフィルターが true である必要があります。 次を選択した場合： **または**&#x200B;を指定した場合、いずれかのレコードが true と評価された場合は、レコードが伝播されます。

オプション **[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]** は、除外したレコードを Campaign から削除するかどうかを制御します。 次を選択した場合、 **いいえ** その後、レコードはAdobe Campaignに残ります。 選択 **はい** を追加して、統合ロジックで削除する必要があります。

>[!NOTE]
>
> フィルターを追加しない場合、変更されたすべてのレコードがAdobe Campaignに反映されます。

### 詳細設定 {#advanced-settings}

マッピングを設定する際に、次の追加オプションを設定できます。

* を **[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]** 選択肢 **はい** Microsoft Dynamics 365 で発生した削除をAdobe Campaignの対応するフィールド（フィールド名のマッピングに基づく）に反映する場合は、を選択します。 選択 **いいえ** をクリックして、Microsoft Dynamics 365 の削除を無視します。

* を **[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]** 選択肢 **いいえ** キャンペーンに反映する場合は、Microsoft Dynamics 365 ピックリストに関連付けられた表示値。 選択 **はい** 技術的な値を反映します。

## Campaign マーケティングイベントをMicrosoft Dynamics 365 に同期

この **[!UICONTROL Campaign to Microsoft Dynamics 365]** ページでは、Adobe CampaignからMicrosoft Dynamics 365 にマッピングされる電子メールマーケティングイベントを識別できます。

制御できる 4 つの指標は次のとおりです。 **送信数**, **クリック数**, **開封数**、および **バウンス**.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

選択 **はい** をクリックして、そのタイプのイベントをMicrosoft Dynamics 365 に送信することを確認します。

クリック [ここ](../../integrating/using/d365-acs-self-service-app-workflows.md) を参照してください。

## オプトイン/オプトアウトワークフロー {#opt-in-out-wf}

この **オプトイン/オプトアウト** ワークフローを使用すると、Microsoft Dynamics 365 とAdobe Campaignの間のオプトイン/オプトアウト情報のフローを識別できます。 ここでは、データがMicrosoft Dynamics 365 エンティティの「連絡先」とAdobe Campaignリソースの「プロファイル」に関連付けられていることを前提としています。

でのオプトアウト管理の詳細を説明します。 [この節](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

「保存」をクリックして選択内容を保存する必要があることに注意してください。 また、 **Campaign からMicrosoft Dynamics 365** ワークフローを開き、「再生」をクリックして、変更を組み込みます。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### オプトイン/オプトアウトの同期方向

次に、データを同期するために使用可能なオプションのリストを示します。

* **[!UICONTROL Disabled]**:このオプションを選択した場合、Adobe CampaignとMicrosoft Dynamics 365 の間でオプトイン/オプトアウト情報は移動されません。

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**:このオプションは、Microsoft Dynamics 365 からAdobe Campaignにのみオプトイン/オプトアウトを送るために使用します。 統合アプリケーションでは、この画面でフローを設定できません。代わりに、 **[!UICONTROL Save button]**&#x200B;をクリックし、 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** ワークフロー。 このワークフローでは、連絡先/プロファイルテーブルのマッピングを編集して、オプトイン/オプトアウトフィールドのマッピング方法を指定できます。

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**:このオプションを選択すると、 **マッピング** 」セクションに入力します。 これらの入力により、Microsoft Dynamics 365 のどのフィールドにデータをマッピングするかを定義できます。 つまり、Microsoft Dynamics 365 の値を手動で更新した場合、変更された場合にその値がAdobe Campaign値で上書きされます。

* **[!UICONTROL Bidirectional]**:このオプションを選択すると、 **マッピング** 」セクションに入力します。 これらのペアは、Microsoft Dynamics 365 とAdobe Campaignのどのフィールドが互いにマッピングされるかを識別します。 [詳細情報](../../integrating/using/d365-acs-notices-and-recommendations.md)。

### マッピング

この節は、「オプトイン/オプトアウト同期の方向」フィールドが **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** または **[!UICONTROL Bidirectional]**. Microsoft Dynamics 365 で、どのフィールドをAdobe Campaignの入力にマッピングするかを定義できます。

Microsoft Dynamics 365 のフィールド名には、タイプのすべてのフィールド名が含まれます **ブール型**.

Adobe Campaignのフィールド名は、オプトイン/オプトアウトに固有の一連の値です。 Adobe Campaignのフィールド名は、オプトイン/オプトアウトに固有の一連の値です。 **このリストの値のセットは変更できません**.

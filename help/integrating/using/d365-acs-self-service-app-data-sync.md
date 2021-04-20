---
title: キャンペーンとMicrosoft Dynamics間のデータの同期
description: キャンペーンとダイナミクス間のデータの同期
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1801'
ht-degree: 0%

---


# データの同期

Microsoft Dynamics 365のテーブルをMicrosoft Dynamics 365とキャンペーンおよびキャンペーンのマーケティング指標に同期できます。 同期は、次の3つの専用テクニカルワークフローを通して実行されます。**[!UICONTROL Microsoft Dynamics 365 to Campaign]**、**[!UICONTROL Campaign to Microsoft Dynamics 365]**、**[!UICONTROL Opt-In/Out]**。 [詳細](../../integrating/using/d365-acs-self-service-app-workflows.md)を参照してください。

>[!IMPORTANT]
>変更を考慮するには、**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;ワークフローを停止/開始する必要があります。 [詳細情報](../../integrating/using/d365-acs-self-service-app-workflows.md)


## Microsoft Dynamics 365のテーブルをキャンペーンにマップ

**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;ページには、Microsoft Dynamics 365のエンティティのリストと、それらが同期されるAdobe Campaignのカスタムリソースが表示されます。 新しいマッピングの追加、既存のマッピングの編集または削除が可能です。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

次の表に、各列の説明を示します。

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**:この列は、Microsoft Dynamics 365のどのエンティティがマッピングのデータソースになるかを示します。

* **[!UICONTROL CAMPAIGN TABLE]**:この列は、マッピングのAdobe Campaign先となるリソースを示します。

* **[!UICONTROL ACTIONS]**:可能なアクションを次に示します。

   * **[!UICONTROL Edit]**&#x200B;アイコンをクリックして、このマッピングを編集します。

   * **[!UICONTROL Delete]**&#x200B;アイコンを使用して、テーブルマッピングを削除します。

   * **[!UICONTROL Replay Data]**&#x200B;アイコンをクリックして、Microsoft Dynamics 365テーブル内のすべてのデータを再同期します。 通常、統合アプリケーションは、最近変更されたMicrosoft Dynamics 365のデータのみを同期します。  ただし、場合によっては（変更を加えたか、間違えたなど）、すべてのデータを再同期させたい場合があります。  この場合、このボタンをクリックし、次に&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;ワークフローを停止/開始すると、データは開始して同期します。

      「**[!UICONTROL Replay Data]**」ボタンをクリックしてチェックが正常に完了すると、アイコンは無効になります。これは、このテーブルマッピングペアのデータが&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;ワークフローの次の実行と再同期されることを示します。

      次の条件を満たす場合は、データの再生を選択できません。

      * **[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;ワークフローに関連付けられたバックログ指標に2,000,000個以上の品目がある場合（**[!UICONTROL Workflows]**&#x200B;ページに表示）
      * Microsoft Dynamics 365テーブルに2,000,000以上のレコードがある場合

      再同期する必要があるレコードの数は異なります。 大量のレコードがある場合、同期処理の完了に時間がかかる場合があります。 統合アプリケーションが同期プロセスを完了する際に動作するので、**[!UICONTROL Workflows]**&#x200B;ページの&#x200B;**[!UICONTROL Backlog]**&#x200B;指標を参照してください。

      >[!IMPORTANT]
      >
      > 変更をAdobe Campaign StandardまたはMicrosoft Dynamics 365に発行する場合は、統合ワークフローを停止することを強くお勧めします。 該当する変更は次のとおりです。リソース/エンティティ（およびそれらに関連付けられたフィールド）、リンク、識別子列などに対する更新 」は、現在統合で使用されています。




## 新しいマッピングを作成{#add-a-new-mapping}

新しいマッピングを作成するには、次の手順に従います。

1. **[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;ページで、「**[!UICONTROL Add New Mapping]**」ボタンをクリックします。

1. ドロップダウンリストを使用して、マッピングするMicrosoft Dynamics 365およびキャンペーンテーブルを選択します。
ページ上のその他の入力のほとんどは、選択したテーブルに依存します。

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >各テーブルを2回以上マップすることはできません。 したがって、ドロップダウンの選択には、既にマッピングされているテーブルは含まれません。

1. **[!UICONTROL OK]**&#x200B;をクリックして確認します。選択したテーブルに関連付けられたフィールド情報を読み込むには、少しの時間が必要です。

その後、マッピング設定を続行できます。 [詳細情報](#new-mapping-settings)

>[!IMPORTANT]
>
>マッピングを最初に追加する場合は、このページでのみテーブルを選択できます。 「**[!UICONTROL Save]**」ボタンをクリックする前に、正しいテーブルが選択されていることを確認してください。テーブルを保存すると、テーブル選択フィールドは&#x200B;**読み取り専用**&#x200B;になります。

### 既存のマッピングの編集

既存のマッピングを編集すると、テーブルの選択を編集できないことがわかります。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

これは、ページの下の方に行く入力は、これらのテーブルに関連付けられたフィールドに基づいているので、設計によるものです。 テーブルを変更すると、これらのテーブルに関連付けられているすべてのフィールドが無効になります。  マッピング先のテーブルを変更する場合は、前のページに戻り、変更するマッピングを削除し、新しいマッピングを追加する必要があります。

### 個々のテーブルマッピングを設定{#new-mapping-settings}

このセクションでは、1つのMicrosoft Dynamics 365テーブルを1つのAdobe Campaignテーブルに&#x200B;**単一の**&#x200B;マッピングする方法を構成します。

次の設定を定義できます。

* **[!UICONTROL Tables]**:このセクションには、Microsoft Dynamics 365テーブルの名前と、マッピング先のキャンペーンテーブルがリストされます。
* **[!UICONTROL Field Mappings]**:この節で詳し [く説明する](#field-mappings)
* **[!UICONTROL Field Replacements]**:この節で詳し [く説明する](#field-replacements)
* **[!UICONTROL Filters]**:この節で詳し [く説明する](#filters)
* **[!UICONTROL Advanced Settings]**:この節で詳し [く説明する](#advanced-settings)

### フィールドマッピング{#field-mappings}

#### プライマリキー

新しいMicrosoft Dynamics 365をキャンペーンテーブルマッピングに追加する場合は、IDフィールドを識別する必要があります。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

Microsoft Dynamics 365の主キーは読み取り専用です。アプリケーションによって検出されます。

キャンペーンの場合は、どのフィールドを一意のキーにするかを選択する必要があります。 [CRM IDカスタムリソース](../../developing/using/uc-calling-resource-id-key.md)として設定する必要があり、重複を持つ必要はありません。

>[!NOTE]
>
>テーブルのIDフィールドは、**[!UICONTROL Add New Mapping]**&#x200B;を選択した場合にのみ選択できます。 「編集」ボタンをクリックして既存のテーブルマッピングを編集すると、IDフィールドは読み取り専用になります。

主キーは、常に&#x200B;**[!UICONTROL Field Mappings]**&#x200B;セクションに一覧表示される最初のフィールド名になります。 注意：右側には、主キーであることを通知する次のアイコンが表示されます。

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### 追加その他のフィールドマッピング

**[!UICONTROL Field Mappings]**&#x200B;セクションでは、プライマリキー以外のフィールドマッピングを追加できます。 Microsoft Dynamics 365からAdobe Campaignにフィールドの新しいマッピングを追加するには、[**[!UICONTROL Add new field mapping]**]ボタンをクリックします。

リストのMicrosoft Dynamics 365とキャンペーンフィールドを選択します。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

これらのリストには、ページの上部で選択したMicrosoft Dynamics 365およびキャンペーンテーブルに関連付けられたフィールド名が含まれます。

**[!UICONTROL Apply updates]**&#x200B;切り替えボタンを使用すると、このフィールドに対する更新をMicrosoft Dynamics 365からキャンペーンに反映するかどうかを制御できます。
* ![](assets/do-not-localize/d365-to-acs-icon-switch-on.png)に切り替えると、Microsoft Dynamics 365の値に対する更新は、更新の発生時にAdobe Campaignに反映されます。

* ![](assets/do-not-localize/d365-to-acs-icon-switch-off.png)をオフにした場合、データが最初に読み込まれる（または再生される）ときに値が反映されますが、Microsoft Dynamics 365のフィールドに対する増分更新は反映されません。

>[!NOTE]
>
>**[!UICONTROL Apply updates]**&#x200B;列見出しをクリックして、スイッチの&#x200B;**すべての**&#x200B;をオンまたはオフに更新します。


フィールドの値を選択すると、ドロップダウンメニューの下にデータタイプが表示されます。   値を1つのフィールドから別のフィールドにマッピングする場合は、この点に注意してください。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> 複数のMicrosoft Dynamics 365フィールドを1つのキャンペーンフィールドにマップすることはできません。

### フィールド置換{#field-replacements}

**[!UICONTROL Add New Field Replacement]**&#x200B;ボタンを使用して、新しいフィールドの置き換えを定義します。

フィールド置き換えでは、次の項目を識別できます。

* Microsoft Dynamics 365のフィールド名（上記の「フィールドマッピング」セクションに追加）、
* 既存の値（Microsoft Dynamics 365に存在する）、および
* Adobe Campaignに書き込む新しい値

選択リスト、定義済みリスト、およびブール値のドロップダウンリストが表示されます。 テキストボックスは、他の文字列や数値の種類に使用されます。

### フィルター {#filters}

**[!UICONTROL Add New Filter]**&#x200B;ボタンを使用して、キャンペーンに反映するMicrosoft Dynamics 365レコードを選択します。 レコードに関連付けられた任意のフィールドを選択して、フィルターに追加できます（フィールド名をフィールドのマッピングに追加する必要はありません）。

次の情報を入力して、フィルターを指定します。

* Microsoft Dynamics 365フィールド名
* 比較値、および
* 値（Microsoft Dynamics 365から）
フィールド名、比較および値が、特定のレコードに対してtrueに評価される場合、レコードはAdobe Campaignに渡されます。

**[!UICONTROL Choose the filter comparison operator]**&#x200B;というラベルの付いた入力を設定すると、これらのフィルターの評価方法を選択できます。  「**And**」を選択した場合、レコードをキャンペーンに伝播するには、すべてのフィルターがtrueである必要があります。 「**または**」を選択した場合、いずれかのレコードがtrueに評価された場合、レコードは伝播されます。

**[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]**&#x200B;オプションは、除外されたレコードをキャンペーンから削除するかどうかを制御します。 「**いいえ**」を選択すると、レコードはAdobe Campaignに残ります。 **はい**&#x200B;を選択して、統合ロジックで削除します。

>[!NOTE]
>
> フィルターを追加しない場合、変更されたすべてのレコードがAdobe Campaignに反映されます。


### 詳細設定{#advanced-settings}

マッピングの設定時に、次の追加オプションを設定できます。

* Microsoft Dynamics 365で発生した削除をAdobe Campaignの対応するフィールドに（フィールド名のマッピングに基づいて）反映する場合は、**[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]**&#x200B;オプションを&#x200B;**はい**&#x200B;に設定します。 Microsoft Dynamics 365の削除を無視するには、[**いいえ**]を選択します。

* Microsoft Dynamics 365の選択リストに関連付けられた表示値をキャンペーンに反映する場合は、**[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]**&#x200B;オプションを&#x200B;**いいえ**&#x200B;に設定します。 「**はい**」を選択して、技術的な値を反映します。

## キャンペーンマーケティングイベントをMicrosoft Dynamics 365と同期する

**[!UICONTROL Campaign to Microsoft Dynamics 365]**&#x200B;ページでは、Adobe CampaignからMicrosoft Dynamics 365にマップする電子メールマーケティングイベントを指定できます。

制御できる4つの指標は次のとおりです。****、**クリック数**、**開く**、**バウンス**&#x200B;を送信します。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

**はい**&#x200B;を選択して、その種類のイベントをMicrosoft Dynamics 365にフローすることを確認します。

これらの電子メールイベントフローの詳細については、[ここ](../../integrating/using/d365-acs-self-service-app-workflows.md)をクリックしてください。

## オプトイン/アウトワークフロー{#opt-in-out-wf}

**オプトイン/オプトアウト**&#x200B;ワークフローを使用すると、Microsoft Dynamics 365とAdobe Campaignの間のオプトイン情報のフローを特定できます。 これは、データがMicrosoft Dynamics 365エンティティの「連絡先」とAdobe Campaignリソースの「プロファイル」に関連付けられていることを前提としています。

オプトアウト管理の詳細については、[このセクション](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out)を参照してください。

「保存」をクリックして選択内容を保存する必要があることに注意してください。 また、Microsoft Dynamics 365 **ワークフローへの**&#x200B;キャンペーンを停止してから、[再生]をクリックして変更を組み込む必要があります。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### オプトイン同期方向外

次に、データを同期するために使用できるオプションのリストを示します。

* **[!UICONTROL Disabled]**:このオプションを選択すると、Adobe CampaignとMicrosoft Dynamics 365の間でオプトイン情報が一切移動しません。

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**:このオプションは、Microsoft Dynamics 365からAdobe Campaignに対してのみオプトイン/オプトアウトを行う場合に使用します。統合アプリケーションでは、この画面でのフローを設定できません。代わりに、**[!UICONTROL Save button]**&#x200B;をクリックし、**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;ワークフローに移動します。 このワークフローでは、連絡先/プロファイルテーブルのマッピングを編集して、オプトイン/オプトアウトフィールドのマッピング方法を指定できます。

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**:このオプションを選択すると、 **** Mappingsセクションが表示されます。これらの入力を使用して、どのAdobe CampaignフィールドがMicrosoft Dynamics 365のどのフィールドにデータをマップするかを定義できます。 つまり、Microsoft Dynamics 365で手動で値を更新した場合、変更が発生すると、その値がAdobe Campaign値によって上書きされます。

* **[!UICONTROL Bidirectional]**:このオプションを選択すると、 **** Mappingsセクションが表示されます。これらのペアは、Microsoft Dynamics 365のどのフィールドとAdobe Campaignが相互にマップするかを識別します。 [詳細情報](../../integrating/using/d365-acs-notices-and-recommendations.md)。

### マッピング

この節は、「オプトイン/オプトアウト同期方向」フィールドが&#x200B;**[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**&#x200B;または&#x200B;**[!UICONTROL Bidirectional]**&#x200B;に設定されている場合にのみ適用されます。 Microsoft Dynamics 365のどのフィールドをAdobe Campaignのどの入力にマップするかを定義できます。

Microsoft Dynamics 365のフィールド名には、**boolean**&#x200B;型のすべてのフィールド名が含まれます。

Adobe Campaignフィールド名は、オプトイン/オプトアウトに固有の固定値セットです。 Adobe Campaignフィールド名は、オプトイン/オプトアウトに固有の固定値セットです。 **このリストの値のセットは変更できません**。

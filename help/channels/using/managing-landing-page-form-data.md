---
solution: Campaign Standard
product: campaign
title: ランディングページフォームデータの管理
description: ランディングページフォームデータを管理する方法について説明します。
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: ランディングページ
role: User
level: Intermediate
exl-id: 7083447c-4cac-41cb-8453-369819e0c7c1
source-git-commit: c56d0e0ab4496ae769dc504107f677ef6ea74068
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 15%

---

# ランディングページフォームデータの管理{#managing-landing-page-form-data}

ランディングページのコンテンツでは、入力フィールドを使用してCampaignデータベースのデータを保存または更新します。

これをおこなうには、これらのフィールドをデータベースフィールドにマッピングする必要があります。

マッピングの定義と管理は、左側のパレットの&#x200B;**[!UICONTROL Form data]**&#x200B;セクションでおこなえます。

![](assets/lp_form-data.png)

## フォームフィールドのマッピング {#mapping-form-fields}

必要に応じてCampaignデータベースを更新するには、ランディングページの入力ゾーン、ラジオボタンまたはチェックボックスタイプのブロックに、関連するデータベースフィールドをリンクします。

これは、次の手順に従って行います。

1. ランディングページコンテンツのブロックを選択します。

   >[!NOTE]
   >
   >組み込みランディングページのデフォルトのフィールドは事前に設定されています。必要に応じて変更できます。

1. 左側のパレットの&#x200B;**[!UICONTROL Form data]**&#x200B;セクションにアクセスします。

1. フィールドタイプを変更するには、**[!UICONTROL HTML type of the field]**&#x200B;ドロップダウンリストから値を選択します。

   ![](assets/lp_html-field-type.png)

   >[!NOTE]
   >
   >ランディングページでのチェックボックスタイプの使用について詳しくは、「[複数のサービス購読](#multiple-subscriptions)および[契約チェックボックス](#agreement-checkbox)の更新」の節を参照してください。

1. **[!UICONTROL Field]**&#x200B;ゾーンで現在選択されているデータベースフィールドと互換性のないフィールドタイプを選択すると、警告メッセージが表示されます。 最適なマッピングを行うには、適切な値を選択します。

   ![](assets/lp_field-type-warning.png)

1. **[!UICONTROL Field]**&#x200B;ゾーンを使用して、フォームフィールドにリンクするデータベースフィールドを選択します。

   ![](assets/lp_select-database-field.png)

   >[!NOTE]
   >
   >ランディングページは、**[!UICONTROL Profiles]**&#x200B;または&#x200B;**[!UICONTROL Service]**&#x200B;リソースとのみマッピングできます。

   この例では、ランディングページの&#x200B;**名前**&#x200B;フィールドを&#x200B;**[!UICONTROL Profiles]**&#x200B;リソースの&#x200B;**[!UICONTROL Last name]**&#x200B;フィールドにマッピングします。

   ![](assets/lp_database-field-example.png)

1. 必要に応じて、「**[!UICONTROL Mandatory]**」オプションを選択します。その場合、ランディングページは、ユーザーがこのフィールドに入力した場合にのみ送信できます。

   ![](assets/lp_mandatory-option.png)

   必須フィールドに値が入力されていない場合は、ユーザーがページを送信したときにエラーメッセージが表示されます。

1. **[!UICONTROL Confirm]**&#x200B;をクリックして変更を保存します。

<!--If you choose a mandatory **[!UICONTROL Checkbox]**, make sure that it is of **[!UICONTROL Field]** type.-->

## データのストレージと紐付け{#data-storage-and-reconciliation}

データ紐付けパラメーターを使用すると、ランディングページに入力されたデータが送信された後の管理方法を定義できます。

手順は次のとおりです。

1. ランディングページダッシュボードの ![](assets/edit_darkgrey-24px.png) アイコンを使用してアクセスするランディングページのプロパティを編集し、「**[!UICONTROL Job]**」パラメーターを表示します。

   ![](assets/lp_parameters_job.png)

1. **[!UICONTROL Reconciliation key]**&#x200B;を選択します。このデータベースフィールドは、Adobe Campaignデータベース内に訪問者のプロファイルが既に存在するかどうかを判断するために使用されます。 例えば、Eメール、名、姓を指定できます。 紐付けキーを使用すると、以下に定義する&#x200B;**[!UICONTROL Update strategy]**&#x200B;パラメーターに従って、プロファイルを更新または作成できます。

1. **[!UICONTROL Form parameter mapping]** を定義：このセクションでは、ランディングページフィールドのパラメーターと、紐付けキーで使用するパラメーターをマップできます。

1. **[!UICONTROL Update strategy]**&#x200B;を選択します。紐付けキーが既存のデータベースプロファイルを回復した場合、フォームに入力されたデータを使用してこのプロファイルを更新するか、この更新を実行しないかを選択できます。

   ![](assets/lp_parameters_update-strategy.png)

## 複数のサービスサブスクリプション {#multiple-subscriptions}

単一のランディングページで複数のチェックボックスを使用して、ユーザーが複数のサービスを購読または購読解除できるようにします。

これは、次の手順に従って行います。

1. ランディングページをデザインする場合：

   * ブロックを選択し、**[!UICONTROL Form data]**&#x200B;セクションからフィールドタイプとして&#x200B;**[!UICONTROL Checkbox]**&#x200B;を選択します。

      ![](assets/lp_field-type-checkbox.png)

   * HTMLに詳しい方は、**[!UICONTROL Show source]**&#x200B;ボタンを使用して手動でチェックボックスを挿入することもできます。

      ![](assets/lp_show_source.png)

      これにより、ページ上の任意の場所にチェックボックスを挿入できます。

      ![](assets/lp_manual-checkbox.png)

1. コンテンツでチェックボックスが選択されていることを確認します。 **[!UICONTROL Type]**&#x200B;ドロップダウンリストが左側のパレットの&#x200B;**[!UICONTROL Form data]**&#x200B;セクションに表示されます。 リストから&#x200B;**[!UICONTROL Service and subscription]**&#x200B;を選択します。

   ![](assets/lp_service-and-subscription.png)

1. **[!UICONTROL Behavior]**&#x200B;ドロップダウンリストからオプションを選択します。

   ![](assets/lp_checkbox-behavior.png)

1. 対応するリストから[サービス](../../audiences/using/creating-a-service.md)を選択します。

   ![](assets/lp_checkbox-service.png)

1. **[!UICONTROL Mandatory]**&#x200B;オプションがオフになっていることを確認します。 そうしないと、ユーザーは選択肢を持ちません。

   ![](assets/lp_uncheck-mandatory.png)

1. 他のサービスの購読を有効にするチェックボックスをさらに追加するには、上記の手順を必要な回数だけ繰り返します。

   ![](assets/lp_multiple-checkboxes.png)

ランディングページが公開されると、ユーザーは複数のチェックボックスをオンにして、同じページから複数のニュースレターを購読できます。

## 契約チェックボックス {#agreement-checkbox}

ランディングページを送信する前にプロファイルが確認する必要があるチェックボックスを追加できます。

例えば、ユーザーがフォームを送信する前に、プライバシーポリシーに対する同意を要求したり、ユーザーが利用条件を承諾するように設定したりできます。

>[!IMPORTANT]
>
>このチェックボックスの選択は、ユーザーに必須です。 選択しないと、ランディングページを送信できなくなります。

このチェックボックスを挿入して設定するには、次の操作を行います。

1. ランディングページをデザインする場合：

   * ブロックを選択し、**[!UICONTROL Form data]**&#x200B;セクションからフィールドタイプとして&#x200B;**[!UICONTROL Checkbox]**&#x200B;を選択します。

      ![](assets/lp_field-type-checkbox.png)

   * HTMLに詳しい方は、**[!UICONTROL Show source]**&#x200B;ボタンを使用して手動でチェックボックスを挿入することもできます。

      ![](assets/lp_show_source.png)

      <!--Manually insert a checkbox, such as in the example below:

      <!--Click **[!UICONTROL Hide source]**.-->

1. チェックボックスが選択されていることを確認します。

   ![](assets/lp_select_checkbox.png)

1. **[!UICONTROL Type]**&#x200B;ドロップダウンリストが左側のパレットの&#x200B;**[!UICONTROL Form data]**&#x200B;セクションに表示されます。 リストから&#x200B;**[!UICONTROL Agreement]**&#x200B;を選択します。

   ![](assets/lp_form_data_drop-down.png)

   >[!NOTE]
   >
   >**[!UICONTROL Agreement]**&#x200B;要素がCampaignデータベースのフィールドにマッピングされていません。

1. **[!UICONTROL Form data]**&#x200B;の横にある![](assets/lp-properties-icon.png)アイコンをクリックして、チェックボックスの詳細設定プロパティにアクセスします。

1. 必要に応じて、メッセージを編集できます。

   ![](assets/lp_agreement_message.png)

   このテキストは、ユーザーがフォームを送信する前にチェックボックスを選択していない場合に、警告として表示されます。

   >[!NOTE]
   >
   >このアクションはデフォルトで必須で、変更できません。

1. 「**[!UICONTROL Confirm]**」をクリックします。

これで、ランディングページが表示されるたびに、フォームを送信する前に、このチェックボックスをオンにする必要があります。 そうでない場合、警告が表示され、チェックボックスが有効になるまでフォームを送信できません。
---
title: ランディングページフォームデータの管理
description: ランディングページフォームデータを管理する方法について説明します。
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 7083447c-4cac-41cb-8453-369819e0c7c1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 15%

---

# ランディングページフォームデータの管理{#managing-landing-page-form-data}

ランディングページのコンテンツでは、入力フィールドを使用して Campaign データベースのデータを保存または更新します。

これをおこなうには、これらのフィールドをデータベースフィールドにマッピングする必要があります。

マッピングは、 **[!UICONTROL Form data]** セクションを左側のパレットに追加します。

![](assets/lp_form-data.png)

## フォームフィールドのマッピング {#mapping-form-fields}

必要に応じて Campaign データベースを更新するには、関連するデータベースフィールドをランディングページの入力ゾーン、ラジオボタンまたはチェックボックスタイプのブロックにリンクします。

これは、次の手順に従って行います。

1. ランディングページコンテンツのブロックを選択します。

   >[!NOTE]
   >
   >組み込みランディングページのデフォルトのフィールドは事前に設定されています。必要に応じて変更できます。

1. 次にアクセス： **[!UICONTROL Form data]** セクションを左側のパレットに追加します。

1. フィールドタイプを変更するには、 **[!UICONTROL HTML type of the field]** 」ドロップダウンリストから選択できます。

   ![](assets/lp_html-field-type.png)

   >[!NOTE]
   >
   >ランディングページでのチェックボックスタイプの使用について詳しくは、 [複数のサービス購読を更新](#multiple-subscriptions) および [契約チェックボックス](#agreement-checkbox) セクション。

1. 現在 **[!UICONTROL Field]** ゾーン（警告メッセージが表示されます） 最適なマッピングを行うには、適切な値を選択します。

   ![](assets/lp_field-type-warning.png)

1. 以下を使用： **[!UICONTROL Field]** ゾーン：フォームフィールドにリンクするデータベースフィールドを選択します。

   ![](assets/lp_select-database-field.png)

   >[!NOTE]
   >
   >ランディングページは、 **[!UICONTROL Profiles]** または **[!UICONTROL Service]** リソース。

   この例では、 **名前** ランディングページのフィールドから **[!UICONTROL Last name]** フィールド **[!UICONTROL Profiles]** リソース。

   ![](assets/lp_database-field-example.png)

1. 必要に応じて、「**[!UICONTROL Mandatory]**」オプションを選択します。その場合、ランディングページは、ユーザーがこのフィールドに入力した場合にのみ送信できます。

   ![](assets/lp_mandatory-option.png)

   必須フィールドに値が入力されていない場合は、ユーザーがページを送信する際にエラーメッセージが表示されます。

1. クリック **[!UICONTROL Confirm]** 変更を保存します。

<!--If you choose a mandatory **[!UICONTROL Checkbox]**, make sure that it is of **[!UICONTROL Field]** type.-->

## データのストレージと紐付け{#data-storage-and-reconciliation}

データ紐付けパラメーターを使用すると、ランディングページに入力されたデータが送信された後の管理方法を定義できます。

手順は次のとおりです。

1. ランディングページダッシュボードの ![](assets/edit_darkgrey-24px.png) アイコンを使用してアクセスするランディングページのプロパティを編集し、「**[!UICONTROL Job]**」パラメーターを表示します。

   ![](assets/lp_parameters_job.png)

1. を選択します。 **[!UICONTROL Reconciliation key]**:このデータベースフィールドは、Adobe Campaignデータベース内に訪問者のプロファイルが既に存在するかどうかを判断するために使用されます。 例えば、E メール、名、姓を指定できます。 紐付けキーを使用すると、 **[!UICONTROL Update strategy]** 以下に定義するパラメータ。

1. **[!UICONTROL Form parameter mapping]** を定義：このセクションでは、ランディングページフィールドのパラメーターと、紐付けキーで使用するパラメーターをマップできます。

1. を選択します。 **[!UICONTROL Update strategy]**:紐付けキーが既存のデータベースプロファイルを回復した場合、フォームに入力されたデータでこのプロファイルを更新するか、この更新を実行しないかを選択できます。

   ![](assets/lp_parameters_update-strategy.png)

## 複数のサービス購読 {#multiple-subscriptions}

1 つのランディングページで複数のチェックボックスを使用して、ユーザーが複数のサービスを購読または購読解除できるようにします。

これは、次の手順に従って行います。

1. ランディングページをデザインする場合：

   * ブロックを選択し、 **[!UICONTROL Form data]** セクションで、 **[!UICONTROL Checkbox]** をフィールドタイプとして使用します。

      ![](assets/lp_field-type-checkbox.png)

   * HTMLに詳しい場合は、 **[!UICONTROL Show source]** 」ボタンをクリックします。

      ![](assets/lp_show_source.png)

      これにより、ページ上の任意の場所にチェックボックスを挿入できます。

      ![](assets/lp_manual-checkbox.png)

1. コンテンツでチェックボックスが選択されていることを確認します。 この **[!UICONTROL Type]** ドロップダウンリストが **[!UICONTROL Form data]** 」セクションに表示されます。 選択 **[!UICONTROL Service and subscription]** を選択します。

   ![](assets/lp_service-and-subscription.png)

1. 次の中からオプションを選択します。 **[!UICONTROL Behavior]** 」ドロップダウンリストから選択できます。

   ![](assets/lp_checkbox-behavior.png)

1. を選択します。 [サービス](../../audiences/using/creating-a-service.md) を選択します。

   ![](assets/lp_checkbox-service.png)

1. 次を確認します。 **[!UICONTROL Mandatory]** オプションがオフになっている。 そうしないと、ユーザーは選択できなくなります。

   ![](assets/lp_uncheck-mandatory.png)

1. 他のサービスを購読できるチェックボックスをさらに追加するには、上記の手順を必要な回数だけ繰り返します。

   ![](assets/lp_multiple-checkboxes.png)

ランディングページが公開されると、ユーザーは複数のチェックボックスをオンにして、同じページから複数のニュースレターを購読できます。

## 契約チェックボックス {#agreement-checkbox}

ランディングページを送信する前にプロファイルが確認する必要があるチェックボックスを追加できます。

例えば、ユーザーがフォームを送信する前に、プライバシーポリシーに対する同意を要求したり、ユーザーが利用条件に同意するように設定したりできます。

>[!IMPORTANT]
>
>このチェックボックスを選択すると、ユーザーに必須です。 選択しない場合、ランディングページを送信できません。

このチェックボックスを挿入して設定するには、次の手順を実行します。

1. ランディングページをデザインする場合：

   * ブロックを選択し、 **[!UICONTROL Form data]** セクションで、 **[!UICONTROL Checkbox]** をフィールドタイプとして使用します。

      ![](assets/lp_field-type-checkbox.png)

   * HTMLに詳しい場合は、 **[!UICONTROL Show source]** 」ボタンをクリックします。

      ![](assets/lp_show_source.png)

      <!--Manually insert a checkbox, such as in the example below:

      <!--Click **[!UICONTROL Hide source]**.-->

1. チェックボックスが選択されていることを確認します。

   ![](assets/lp_select_checkbox.png)

1. この **[!UICONTROL Type]** ドロップダウンリストが **[!UICONTROL Form data]** 」セクションに表示されます。 選択 **[!UICONTROL Agreement]** を選択します。

   ![](assets/lp_form_data_drop-down.png)

   >[!NOTE]
   >
   >この **[!UICONTROL Agreement]** 要素が Campaign データベースのフィールドにマッピングされていません。

1. 次をクリック： ![](assets/lp-properties-icon.png) 隣のアイコン **[!UICONTROL Form data]** ：チェックボックスの詳細プロパティにアクセスします。

1. 必要に応じて、メッセージを編集できます。

   ![](assets/lp_agreement_message.png)

   このテキストは、ユーザーがフォームを送信する前にチェックボックスを選択しなかった場合に警告として表示されます。

   >[!NOTE]
   >
   >このアクションはデフォルトで必須で、変更できません。

1. 「**[!UICONTROL Confirm]**」をクリックします。

これで、ランディングページが表示されるたびに、フォームを送信する前にこのチェックボックスをオンにする必要があります。 そうでない場合は、警告が表示され、チェックボックスが有効になるまでユーザーはフォームを送信できません。
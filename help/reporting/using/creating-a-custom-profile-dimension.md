---
title: カスタムプロファイルディメンションの作成
seo-title: カスタムプロファイルディメンションの作成
description: カスタムプロファイルディメンションの作成
seo-description: カスタムプロファイルデータに基づいてカスタムプロファイルディメンションを作成する方法を説明します。
page-status-flag: 未活性化の
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 報告
content-type: 参照
topic-tags: レポートのカスタマイズ
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 4ad558fce83006879455a791127594157456f0c4

---


# カスタムプロファイルディメンションの作成{#creating-a-custom-profile-dimension}

また、プロファイルのカスタムリソース拡張時に作成されたカスタムプロファイルデータに基づいて、レポートを作成および管理することもできます。

この例では、次の3つのレベルに分割されるカスタム·プロファイル·フィ **ールド** Loyaltyプログラムを作成します。金、銀、青銅。 このカスタム·プロファイルは、動的レポートでカスタム·プロファイル次元として使用できるように拡張されます。

* [ステップ1:新しいプロファイルフィールドを作成する](../../reporting/using/creating-a-custom-profile-dimension.md#step-1--create-a-new-profile-field)
* [手順2:プロファイルフィールドで送信ログを拡張する](../../reporting/using/creating-a-custom-profile-dimension.md#step-2--extend-the-sending-logs-with-the-profile-field)
* [ステップ3:ロイヤルティプログラムに登録された配送ターゲット受信者を作成します](../../reporting/using/creating-a-custom-profile-dimension.md#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [手順4:カスタム·プロファイル次元で受信者をフィルタ処理する動的レポートを作成します。](../../reporting/using/creating-a-custom-profile-dimension.md#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## ステップ1:新しいプロファイルフィールドを作成する {#step-1--create-a-new-profile-field}

まず、受信者にロイヤルティレベルを割り当てる新しいプロファイル **フィールド** Loyaltyプログラムを作成する必要があります。金、銀、青銅。

>[!NOTE]
>
>カスタムリソースは、管理者のみが管理できます。

次の手順に従います。

1. 詳細メニューから、 &gt; &gt; **[!UICONTROL Administration]** &gt;カスタムリソ **[!UICONTROL Development]** ースを **[!UICONTROL Custom resources]** 選択 **[!UICONTROL Profile (profile)]** します。

   ![](assets/custom_profile_1.png)

1. タブのカテ **[!UICONTROL Data structure]** ゴリで、ボ **[!UICONTROL Fields]** タンをクリックし **[!UICONTROL Add field]** ます。

   ![](assets/custom_profile_2.png)

1. を入力し、 **[!UICONTROL Label]**&#x200B;カス **[!UICONTROL ID]** タムリソースを選択しま **[!UICONTROL Type]**&#x200B;す。 ここでは、金、銀 **[!UICONTROL Text]** 、青銅のどちらかを選ぶので選びました。

   ![](assets/custom_profile_3.png)

1. アイコンをクリ ![](assets/custom_profile_22.png) ックして、フィールドを定義します。

   ![](assets/custom_profile_12.png)

1. ここでは、をクリックして各値をチェックし、 **[!UICONTROL Specify a list of authorized valued]** 承認値を指定する必要がありま **[!UICONTROL Create element]**&#x200B;す。

   ![](assets/custom_profile_13.png)

1. を入力し、を **[!UICONTROL Label]** クリック **[!UICONTROL Value]** してくださ **[!UICONTROL Add]**&#x200B;い。 この例では、金、銀、青銅の値を作成する必要があります。 完了したら、 **[!UICONTROL Confirm]** をクリックします。

   ![](assets/custom_profile_14.png)

1. タブを選択 **[!UICONTROL Screen definition]** します。 ドロップダウ **[!UICONTROL Detail screen configuration]** ンで、断面をチェックし **[!UICONTROL Add personalized fields]** て、プロファイルに新しい断面を作成します。

   ![](assets/custom_profile_4.png)

1. ボタンをクリック **[!UICONTROL Add an element]** して、新しい断面を作成します。 次の項目を選択しま **[!UICONTROL Type]**&#x200B;す。、また **[!UICONTROL Input field]**&#x200B;は、 **[!UICONTROL Value]****[!UICONTROL List]**&#x200B;この新しいセクションに追加するフィールド。

   ![](assets/custom_profile_5.png)

1. フィールドのセクションにタイトルを追加することもできま **[!UICONTROL Customize the title of the section where the fields will be displayed]**&#x200B;す。

   構成が完 **[!UICONTROL Save]** 了したら、をクリックします。

   ![](assets/custom_profile_6.png)

1. 詳細メニューから、 &gt; &gt;を選択して、カス **[!UICONTROL Administration]** タム **[!UICONTROL Development]****[!UICONTROL Publication]** リソースの発行を開始します。
1. 準備が完 **[!UICONTROL Prepare publication]** 了したら、をクリックし、ボタンをクリック **[!UICONTROL Publish]** します。

   ![](assets/custom_profile_7.png)

これで、新しいプロファイルフィールドを使用して、受信者が選択できるようになりました。

![](assets/custom_profile_8.png)

## 手順2:プロファイルフィールドで送信ログを拡張する {#step-2--extend-the-sending-logs-with-the-profile-field}

プロファイルフィールドが作成されたら、送信ログをプロファイルフィールドと共に拡張して、動的レポートに関連付けられたカスタムプロファイルディメンションを作成する必要があります。

プロファイルフィールドを使用してログを拡張する前に、PIIウィンドウがタブへのアクセス権を受け入れられたことを確認して **[!UICONTROL Sending logs extension]** ください。 詳細は、このページを参照してく [ださい](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

>[!NOTE]
>
>ログは、管理者がプロファイルフィールドを使用してのみ拡張できます。

1. 詳細メニューから、 &gt; &gt; **[!UICONTROL Administration]** &gt;カスタムリソ **[!UICONTROL Development]** ースを **[!UICONTROL Custom resources]** 選択 **[!UICONTROL Profile (profile)]** します。
1. ドロップダウ **[!UICONTROL Sending logs extension]** ンを開きます。
1. ボタンをクリック **[!UICONTROL Create element]** します。

   ![](assets/custom_profile_9.png)

1. 以前に作成したフィールドを選択し、をクリックしま **[!UICONTROL Confirm]**&#x200B;す。
1. カスタム·プ **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** ロファイル次元を作成する場合は、チェックします。

   ![](assets/custom_profile_10.png)

   このオプションは、PIIウィンドウが受け入れられた場合にのみ使用できます。 詳細は、このページを参照してく [ださい](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

1. をクリック **[!UICONTROL Add]** し、カスタムリソースを保存します。
1. カスタムリソースが変更されたため、新しい変更を実装するために発行する必要があります。

   詳細メニューから、 &gt; &gt;を選択して、カス **[!UICONTROL Administration]** タム **[!UICONTROL Development]****[!UICONTROL Publication]** リソースの発行を開始します。

1. 準備が完 **[!UICONTROL Prepare publication]** 了したら、をクリックし、ボタンをクリック **[!UICONTROL Publish]** します。

   ![](assets/custom_profile_7.png)

カスタム·プロファイルが、レポート内のカスタム·プロファイル次元として使用できるようになりました。

フィールドが作成され、このプロファイルフィールドで送信ログが拡張されたので、配信先の受信者をターゲットにすることができます。

## ステップ3:ロイヤルティプログラムに登録された配送ターゲット受信者を作成します {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

プロファイルフィールドが公開されたら、配信を開始できます。 この例では、ロイヤルティプログラムに登録されているすべての受信者を対象にします。

1. タブでをク **[!UICONTROL Marketing activities]** リックし、を **[!UICONTROL Create]** 選択しま **[!UICONTROL Email]**&#x200B;す。
1. 次に、電子メ **[!UICONTROL Email type]** ールのプロパティを選択します。
1. ロイヤルティプログラムに登録された受信者をターゲットにするには、活動をドラッグアンドドロップ **[!UICONTROL Profiles (attributes)]** します。
1. 前に作成したフィールドをドロッ **[!UICONTROL Field]** プダウンから選択します。

   ![](assets/custom_profile_16.png)

1. を選択しま **[!UICONTROL Filter conditions]**&#x200B;す。 ここでは、3つのロイヤルティプログラムのレベルの1つに含まれる受信者を対象にします。

   ![](assets/custom_profile_17.png)

1. をクリック **[!UICONTROL Confirm]** し、フィルタ処理が完了したらをクリックしま **[!UICONTROL Next]**&#x200B;す。
1. メッセージの内容、送信者名、件名を定義し、カスタマイズします。 電子メール作成の詳細については、このページを参照して [ください](../../designing/using/overview.md)。

   次に、をクリックしま **[!UICONTROL Create]**&#x200B;す。

1. 準備が整ったら、メッセージをプレビューして送信できます。 メッセージの準備と送信の詳細については、このページを参照してく [ださい](../../sending/using/preparing-the-send.md)。

選択した受信者に電子メールが正しく送信されたら、データのフィルタリングを開始し、レポートを使用して配信の成功を追跡できます。

## 手順4:カスタム·プロファイル次元で受信者をフィルタ処理する動的レポートを作成します。 {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

搬送を送信した後、表のカスタム·プロファイル分析コードを使用してブレークダウン·レポートを作成で **[!UICONTROL Profile]** きます。

1. タブから **[!UICONTROL Reports]** 、最新のレポートを選択するか、ボタンをクリックして、最 **[!UICONTROL Create]** 初から開始します。

   ![](assets/custom_profile_18.png)

1. カテゴリで、をク **[!UICONTROL Dimensions]** リックし、カス **[!UICONTROL Profile]** タムロイヤルティプログラムプロファイルディメンションをフリーフォーム **** ·テーブルにドラッグ·アンド·ドロップします。

   ![](assets/custom_profile_19.png)

1. データのフィルタを開始するには、 **[!UICONTROL Processed/Sent]** およびメ **[!UICONTROL Open]** トリックをドラッグ·アンド·ドロップします。

   ![](assets/custom_profile_20.png)

1. 必要に応じて、ワークスペース内でビジュアル化をドラッグ&amp;ドロップします。

   ![](assets/custom_profile_21.png)

**関連トピック：**

* [カスタム·プロファイル·データを使用した洞察に富んだレポートの作成](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)

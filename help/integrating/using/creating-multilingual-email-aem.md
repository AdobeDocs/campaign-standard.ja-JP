---
title: Adobe Experience Manager との統合による多言語 E メールの作成.
description: Adobe Experience Manager統合を使用すると、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用することができます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 0f66fe2b-22b1-49d7-a080-29b00941a2cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 15%

---

# Adobe Experience Manager との統合による多言語 E メールの作成 {#creating-multilingual-email-aem}

このドキュメントを使用して、Adobe Experience Managerのコンテンツと言語コピーを使用して多言語の E メールを作成する方法を学びます。

前提は次のとおりです。

* 統合用に設定されたAEMインスタンスへのアクセス。
* 統合用に設定されたAdobe Campaignインスタンスへのアクセス。
* AEMコンテンツを受け取るように設定されたAdobe Campaignの多言語 E メールテンプレート。

## Adobe Experience Manager での新しい E メールコンテンツの作成 {#creating-email-content-aem}

1. Adobe Experience Managerのホームページで、「 」を選択します。 **[!UICONTROL Site]**.

   ![](assets/aem_acs_1.png)

1. ページを作成するフォルダーを選択し、「 **[!UICONTROL Create]** その後 **[!UICONTROL Page]**. ここでは、デフォルト言語となる en_us フォルダーにページを作成します。

   ![](assets/aem_acs_2.png)

1. を選択します。 **[!UICONTROL Adobe Campaign Email (ACS)]** テンプレート。

1. E メールのプロパティを入力し、「 **[!UICONTROL Create]**.

   ![](assets/aem_acs_3.png)

1. 新しい E メールコンテンツを開き、必要に応じてパーソナライズします。 詳しくは、この[ページ](../../integrating/using/creating-email-experience-manager.md#editing-email-aem)を参照してください。

   ![](assets/aem_acs_4.png)

1. 次から： **[!UICONTROL Workflow]** タブで、 **[!UICONTROL Approve for Adobe Campaign]** 検証ワークフロー。 E メールに未承認のコンテンツを使用している場合、その E メールを Adobe Campaign で送信することはできません。

   ![](assets/aem_acs_7.png)

1. クリック **[!UICONTROL Complete]** その後 **[!UICONTROL Newsletter review]** から **[!UICONTROL Complete work item]** ウィンドウ

1. 「**[!UICONTROL Complete]**」、「**[!UICONTROL Newsletter approval]**」の順にクリックします。コンテンツと送信パラメーターを定義したら、Adobe Campaign Standardで E メールの承認、準備および送信に進むことができます。

   ![](assets/aem_acs_8.png)

## 言語コピーの作成 {#creating-language-copies}

E メールコンテンツをデザインした後、バリエーションとしてAdobe Campaign Standardと同期する言語コピーを作成する必要があります。

1. 以前に作成したページを選択し、「 **[!UICONTROL Create]** その後 **[!UICONTROL Language Copy]**.

   ![](assets/aem_acs_5.png)

1. 選択した言語で翻訳される、以前に作成した E メールコンテンツを選択し、「 **[!UICONTROL Next]**.

   ![](assets/aem_acs_6.png)

1. Adobe Analytics の **[!UICONTROL Target language(s)]** ドロップダウンで、コンテンツを翻訳する言語を選択し、「 **[!UICONTROL Next]**.

   ![](assets/aem_acs_9.png)

1. 「**[!UICONTROL Create]**」をクリックします。

言語コピーが作成され、選択した言語に応じてコンテンツを編集できるようになりました。

>[!CAUTION]
>
>すべての言語コピーは、 **[!UICONTROL Approve for Adobe Campaign]** 検証ワークフロー。 E メールに未承認のコンテンツを使用している場合、その E メールを Adobe Campaign で送信することはできません。

![](assets/aem_acs_11.png)

## Adobe Campaign Standardでの多言語コンテンツの作成 {#multilingual-acs}

1. Adobe Campaign Standardのホームページで、 **[!UICONTROL Create an email]**.

   ![](assets/aem_acs_12.png)

1. Adobe Experience Managerコンテンツを受け取るように設定したAdobe Campaign多言語 E メールテンプレートを選択します。 Adobe Experience Managerインスタンスにリンクするテンプレートの作成方法について詳しくは、こちらを参照してください。 [ページ](../../integrating/using/configure-experience-manager.md#config-acs).

   >[!NOTE]
   >
   >その場合は、組み込みテンプレートを複製する必要があります **[!UICONTROL Multilingual email (mailMultiLang)]** 多言語の e メールを送信できるようにする。

   ![](assets/aem_acs_13.png)

1. 次の項目に入力： **[!UICONTROL Properties]** および **[!UICONTROL Audience]** 」と入力します。 **[!UICONTROL Create]**.

1. Adobe Analytics の **[!UICONTROL Edit properties]**&#x200B;を設定する場合、Adobe Experience Managerアカウントが **[!UICONTROL Content]** 」ドロップダウンリストから選択できます。

   ![](assets/aem_acs_20.png)

1. 「**[!UICONTROL Language copy creation]**」をクリックします。

   ![](assets/aem_acs_16.png)

1. 以前に作成したAdobe Experience Managerコンテンツを選択し、 **[!UICONTROL Confirm]**. ここに表示されるAdobe Experience Managerのコンテンツは、検証されたコンテンツのみで、それらのコンテンツに対してフィルタリングできます **[!UICONTROL Label]** および **[!UICONTROL Path]**.

   >[!NOTE]
   >
   >選択した言語コピーがデフォルトとして設定され、後で **[!UICONTROL Content variant]** ブロック。

   ![](assets/aem_acs_17.png)

1. クリック **[!UICONTROL Create variants]** 多言語コンテンツをリンクする その後、Adobe Campaign Standardは、他の言語コピーをこのコンテンツに自動的にリンクします。 作成されたバリエーションには、Adobe Experience Managerで選択されたものと同じラベルおよびコード言語が付きます。

   ![](assets/aem_acs_18.png)

1. 次をクリック： **[!UICONTROL Content variant]** ブロックして、必要に応じてデフォルトのバリアントを変更し、 **[!UICONTROL Confirm]**.

   ![](assets/aem_acs_19.png)

1. コンテンツやバリアントがAdobe Experience Managerで更新された場合、Adobe Campaign Standardで直接 **[!UICONTROL Refresh AEM contents]** 」ボタンをクリックします。

1. これで、E メールを送信する準備が整いました。 これについて詳しくは、この[ページ](../../sending/using/get-started-sending-messages.md)を参照してください。

   >[!NOTE]
   >
   >未承認のAEMコンテンツを使用している場合、Adobe Campaignで E メールを送信することはできません。

オーディエンスは、 **[!UICONTROL Preferred languages]** 彼らの **[!UICONTROL Profiles]**. プロファイルと優先言語の編集方法について詳しくは、こちらを参照してください。 [ページ](../../audiences/using/editing-profiles.md).

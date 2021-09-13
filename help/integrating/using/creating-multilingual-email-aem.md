---
title: Adobe Experience Manager との統合による多言語 E メールの作成.
description: Adobe Experience Manager統合を使用すると、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用できます。
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

このドキュメントでは、Adobe Experience Managerのコンテンツと言語コピーを使用して多言語のEメールを作成する方法を説明します。

前提は次のとおりです。

* 統合用に設定されたAEMインスタンスへのアクセス。
* 統合用に設定されたAdobe Campaignインスタンスへのアクセス。
* AEMコンテンツを受け取るように設定されたAdobe Campaignの多言語Eメールテンプレート。

## Adobe Experience Manager での新しい E メールコンテンツの作成 {#creating-email-content-aem}

1. Adobe Experience Managerのホームページで、「**[!UICONTROL Site]**」を選択します。

   ![](assets/aem_acs_1.png)

1. ページを作成するフォルダーを選択し、「**[!UICONTROL Create]**」、「**[!UICONTROL Page]**」の順にクリックします。 ここでは、デフォルト言語のen_usフォルダーにページを作成します。

   ![](assets/aem_acs_2.png)

1. **[!UICONTROL Adobe Campaign Email (ACS)]**&#x200B;テンプレートを選択します。

1. Eメールのプロパティを入力し、「**[!UICONTROL Create]**」をクリックします。

   ![](assets/aem_acs_3.png)

1. 新しいEメールコンテンツを開き、必要に応じてパーソナライズします。 詳しくは、この[ページ](../../integrating/using/creating-email-experience-manager.md#editing-email-aem)を参照してください。

   ![](assets/aem_acs_4.png)

1. 「**[!UICONTROL Workflow]**」タブで、**[!UICONTROL Approve for Adobe Campaign]**&#x200B;検証ワークフローを選択します。 E メールに未承認のコンテンツを使用している場合、その E メールを Adobe Campaign で送信することはできません。

   ![](assets/aem_acs_7.png)

1. **[!UICONTROL Complete]**&#x200B;をクリックし、**[!UICONTROL Complete work item]**&#x200B;ウィンドウから&#x200B;**[!UICONTROL Newsletter review]**&#x200B;をクリックします。

1. 「**[!UICONTROL Complete]**」、「**[!UICONTROL Newsletter approval]**」の順にクリックします。コンテンツと送信パラメーターを定義したら、Adobe Campaign StandardでEメールの承認、準備、送信に進むことができます。

   ![](assets/aem_acs_8.png)

## 言語コピーの作成 {#creating-language-copies}

Eメールコンテンツをデザインした後、バリエーションとしてAdobe Campaign Standardと同期する言語コピーを作成する必要があります。

1. 以前に作成したページを選択し、「**[!UICONTROL Create]**」、「**[!UICONTROL Language Copy]**」の順にクリックします。

   ![](assets/aem_acs_5.png)

1. 以前に作成したEメールコンテンツを選択し、選択した言語で翻訳する場合は&#x200B;**[!UICONTROL Next]**&#x200B;をクリックします。

   ![](assets/aem_acs_6.png)

1. 「**[!UICONTROL Target language(s)]**」ドロップダウンで、コンテンツの翻訳言語を選択し、「**[!UICONTROL Next]**」をクリックします。

   ![](assets/aem_acs_9.png)

1. 「**[!UICONTROL Create]**」をクリックします。

これで、言語コピーが作成され、選択した言語に応じてコンテンツを編集できます。

>[!CAUTION]
>
>すべての言語コピーは、**[!UICONTROL Approve for Adobe Campaign]**&#x200B;検証ワークフローを通じて承認する必要があります。 E メールに未承認のコンテンツを使用している場合、その E メールを Adobe Campaign で送信することはできません。

![](assets/aem_acs_11.png)

## Adobe Campaign Standardでの多言語コンテンツの作成 {#multilingual-acs}

1. Adobe Campaign Standardのホームページで、「**[!UICONTROL Create an email]**」をクリックします。

   ![](assets/aem_acs_12.png)

1. Adobe Experience Managerコンテンツを受け取るように設定されたAdobe Campaign多言語Eメールテンプレートを選択します。 Adobe Experience Managerインスタンスにリンクされたテンプレートの作成方法について詳しくは、この[ページ](../../integrating/using/configure-experience-manager.md#config-acs)を参照してください。

   >[!NOTE]
   >
   >この場合、多言語のEメールを送信するには、組み込みテンプレート&#x200B;**[!UICONTROL Multilingual email (mailMultiLang)]**&#x200B;を複製する必要があります。

   ![](assets/aem_acs_13.png)

1. Eメールの&#x200B;**[!UICONTROL Properties]**&#x200B;と&#x200B;**[!UICONTROL Audience]**&#x200B;に入力し、「**[!UICONTROL Create]**」をクリックします。

1. **[!UICONTROL Edit properties]**&#x200B;で、**[!UICONTROL Content]**&#x200B;ドロップダウンにAdobe Experience Managerアカウントが正しく設定されていることを確認します。

   ![](assets/aem_acs_20.png)

1. 「**[!UICONTROL Language copy creation]**」をクリックします。

   ![](assets/aem_acs_16.png)

1. 以前に作成したAdobe Experience Managerコンテンツを選択し、「**[!UICONTROL Confirm]**」をクリックします。 ここに表示されるAdobe Experience Managerのコンテンツは、検証されたコンテンツのみで、 **[!UICONTROL Label]**&#x200B;と&#x200B;**[!UICONTROL Path]**&#x200B;でフィルタリングできます。

   >[!NOTE]
   >
   >選択した言語コピーはデフォルトとして設定され、後で&#x200B;**[!UICONTROL Content variant]**&#x200B;ブロックで変更できます。

   ![](assets/aem_acs_17.png)

1. **[!UICONTROL Create variants]**&#x200B;をクリックして、多言語コンテンツをリンクします。 Adobe Campaign Standardは、他の言語コピーをこのコンテンツに自動的にリンクします。 作成されたバリエーションには、Adobe Experience Managerで選択されたものと同じラベルおよびコード言語が付きます。

   ![](assets/aem_acs_18.png)

1. 必要に応じて、**[!UICONTROL Content variant]**&#x200B;ブロックをクリックしてデフォルトのバリアントを変更し、**[!UICONTROL Confirm]**&#x200B;をクリックします。

   ![](assets/aem_acs_19.png)

1. コンテンツやバリエーションがAdobe Experience Managerで更新された場合は、Adobe Campaign Standardで&#x200B;**[!UICONTROL Refresh AEM contents]**&#x200B;ボタンを使用して直接同期できます。

1. これで、Eメールを送信する準備が整いました。 これについて詳しくは、この[ページ](../../sending/using/get-started-sending-messages.md)を参照してください。

   >[!NOTE]
   >
   >Adobe Campaignで未承認のAEMコンテンツを使用している場合、Eメールを送信できません。

オーディエンスは、**[!UICONTROL Profiles]**&#x200B;に設定された&#x200B;**[!UICONTROL Preferred languages]**&#x200B;に応じて電子メールを受け取ります。 プロファイルと優先言語の編集方法について詳しくは、[ページ](../../audiences/using/editing-profiles.md)を参照してください。

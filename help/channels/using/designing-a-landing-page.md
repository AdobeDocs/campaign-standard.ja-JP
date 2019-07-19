---
title: ランディングページのデザイン
seo-title: ランディングページのデザイン
description: ランディングページのデザイン
seo-description: ランディングページのコンテンツをデザインしてサービスにリンクするには、次の手順に従います。
page-status-flag: 常にアクティブ化されていない
uuid: de6fe190-835c-40fd-8101- a809b430b423
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: ランディングページ
discoiquuid: bd77d6f0-3143-4030- a91b-988a2bebc534
context-tags: landingPage， main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Designing a landing page{#designing-a-landing-page}

## About content design {#about-content-design}

Landing pages are created as any [marketing activity](../../start/using/marketing-activities.md#about-marketing-activities).

ランディングページをデザインするときは、次のコンテンツを定義する必要があります。

* ページ自体、
* 確認ページ、
* エラーページが表示されます。

アクションバーの切り替えボタンを使用して、これらの各ページを表示および設定します。

これらのページのコンテンツは、キャンペーンコンテンツエディターを使用してデザインされます。Refer to [Design content](../../designing/using/about-landing-page-content-design.md).

## Mapping form fields {#mapping-form-fields}

入力フィールドは、Campaignデータベースにデータを保存または更新するために使用します。このためには、データベースのフィールドを入力ゾーン、ラジオボタンまたはチェックボックスタイプブロックにリンクする必要があります。これを行うには、次の手順に従います。

1. ランディングページ内のブロックを選択します。
1. Complete the **[!UICONTROL Form data]** part in the palette.

   ![](assets/editing_lp_content_4.png)

1. **[!UICONTROL Field]** 選択ゾーンのフォームフィールドにリンクするデータベースフィールドを選択します。

   **[!UICONTROL Mandatory]** このオプションを選択すると、ユーザーがこのフィールドを完了した場合にのみページを送信できます。必須フィールドが完了していない場合、ユーザーがページを検証するとエラーメッセージが表示されます。

   >[!NOTE]
   >
   >Landing pages can only be mapped with **Profiles**.

1. Define the field type by choosing, for example **[!UICONTROL Text]**, **[!UICONTROL Number]**,or **[!UICONTROL Date]** in the **[!UICONTROL HTML type of the field]** selection area.

>[!NOTE]
>
>組み込みランディングページのデフォルトフィールドは事前に設定されています。必要に応じて変更できます。

## Submitting the form {#submitting-the-form}

訪問者が送信ボタンをクリックしたときに実行するアクションを選択できます。これを行うには、次の手順に従います。

1. ランディングページの送信ボタンを選択します。
1. 左側のパネルのドロップダウンリストでアクションを選択します。Possible actions are: **[!UICONTROL Refresh]** (to refresh the page) and **[!UICONTROL Next page]** (to display the confirmation page).

   ![](assets/editing_lp_content_5.png)

また、ボタンのラベルを変更したり、特定のリンクを設定したりできます。これを行うには、次の手順に従います。

1. 送信ボタンを選択します。
1. Click on the ![](assets/lp_link_properties.png) button in the left panel.
1. ボタンのラベルを入力し、リンクの種類、そのプロパティおよびターゲットを選択します。

   ![](assets/lp_link_custom.png)

## Linking a form to a service {#linking-a-form-to-a-service}

フォームをサービスにリンクして、ランディングページの検証時にプロファイルが特定のサービスを購読できるようにすることができます。

ランディングページをリンクするパラメーターにより、実行されたアクションタイプと、ランディングページが単一のサービスにリンクされているか、汎用かどうかを指定できます。

リンクするサービスを選択するには、以下を行う必要があります。

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Job]** parameters.

   ![](assets/lp_edit_properties_button.png)

1. Choose **[!UICONTROL Subscription]** in the **[!UICONTROL Specific actions]** drop-down list.

   ![](assets/lp_parameters_5.png)

1. Select **[!UICONTROL Specific service]** to link the landing page to a single service. ランディングページで複数のサービスを使用する場合は、このオプションを選択しないでください。

   **[!UICONTROL Specified service in the URL]** このオプションを使用して、ランディングページを複数のサービスに使用できるようにします。したがって、サービスの設定時にランディングページを参照する必要があります。

### Confirm a landing page submission {#confirm-a-landing-page-submission}

ランディングページが訪問者によって送信された場合、トリガーアクションを設定できます。これを行うには、次の手順に従います。

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Job]** parameters.

   ![](assets/lp_edit_properties_button.png)

1. Under the **[!UICONTROL Specific actions]** section, select **[!UICONTROL Start sending message]** to determine the sending of an automatic message, for example to confirm subscription to a service. 電子メール配信テンプレートを選択する必要があります。

   サービスレベルで確認メッセージが既に設定されている場合、複数の確認メッセージを送信しないようにこの画面で1つ選択しないでください。Refer to [Configure a service](../../audiences/using/creating-a-service.md).

1. Create **[!UICONTROL Additional data]** to enable storing additional data when the landing page is being submitted. このデータは、ページを訪問した人には表示されません。考慮されるのは一定の値のみです。

   ![](assets/lp_parameters_6.png)

## Setting permissions and pre-loading data {#setting-permissions-and-pre-loading-data}

ランディングページへのアクセスは、例えばキャンペーンによって送信されたメッセージのリンクから来た訪問者に制限できます。この場合、ランディングページでデータをプリロードできます。これを行うには、次の手順に従います。

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Access & loading]** parameters.

   ![](assets/lp_edit_properties_button.png)

1. Select **[!UICONTROL Preload visitor data]**.

   ページへの訪問者がデータベース内のプロファイルに対応する場合、そのデータはデータベースデータとともにマッピングされるフォームのフィールドに表示され、ランディングページのパーソナライゼーションエレメントが考慮されます。

   ![](assets/lp_parameters_3.png)

また、次のこともできます。

* **[!UICONTROL Authorize visitor identification via URL parameters]** 次のオプションを使用して、URLパラメーターを使用して訪問者を識別します。次に、ロードするキーを選択し、対応するURLのパラメーターを使用してフィルターパラメーターをマッピングする必要があります。
* Authorize any visitor to access the landing page, using the **[!UICONTROL Authorize unidentified visitors]** option.

## Setting Google reCAPTCHA {#setting-google-recaptcha}

ランディングページを使用してGoogle reCAPTCHA V3を設定し、ボットによるスパムや違反から保護することができます。ランディングページで使用できるようにするには、まず外部アカウントを作成する必要があります。For more information on how to configure it, refer to this [section](../../administration/using/external-accounts.md#google-recaptcha-external-account).

Google reCaptCHA V3外部アカウントが設定されたら、ランディングページに追加できます。

1. Before publishing your landing page, access the page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon from you landing page dashboard.

   ![](assets/lp_parameters_google3.png)

1. Unfold the **[!UICONTROL Access & loading]** menu.
1. **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]** このオプションを選択します。
1. 以前に作成したGoogle reCaptCHA外部アカウントを選択します。

   ![](assets/lp_parameters_google.png)

1. **[!UICONTROL Confirm]**&#x200B;をクリックします。

ランディングページがGoogle reCaptchAで設定され、ページの下部に表示できるようになりました。

![](assets/lp_parameters_google2.png)

Google reCaptchAは、ユーザーのページとのインタラクションに基づいてスコアを返します。To check your score, connect to your [Google admin console](https://g.co/recaptcha/admin).

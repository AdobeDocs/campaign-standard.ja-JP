---
title: ランディングページの設定
description: ランディングページのプロパティを設定する方法を説明します。
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# ランディングページの設定 {#configuring-landing-page}

## ランディングページの送信の確認 {#confirm-a-landing-page-submission}

訪問者がランディングページを送信した場合、トリガーされるアクションを設定できます。 手順は次のとおりです。

1. ランディングページのダッシュボードのアイコンを使用し ![](assets/edit_darkgrey-24px.png) てアクセスしたランディングページのプロパティを編集し、パラメータを表示 **[!UICONTROL Job]** します。

   ![](assets/lp_edit_properties_button.png)

1. 「」セクシ **[!UICONTROL Specific actions]** ョンで、自動メ **[!UICONTROL Start sending message]** ッセージの送信を決定する場合に選択します。例えば、サービスの購読を確認します。 その後、電子メール配信テンプレートを選択する必要があります。

   確認メッセージが既にサービスレベルで設定されている場合は、この画面で確認メッセージを1つ選択しないでください。 「サービス [の設定」を参照](../../audiences/using/creating-a-service.md)。

1. ランディング **[!UICONTROL Additional data]** ページの送信時に追加のデータを保存できるように作成します。 このデータは、ページを訪問した人には表示されません。 定数値のみが考慮されます。

   ![](assets/lp_parameters_6.png)

## ランディングページのサービスへのリンク {#linking-a-landing-page-to-a-service}

フォームをサービスにリンクして、ランディングページを検証する際にプロファイルが特定のサービスに登録できるようにすることができます。

ランディングページをリンクするパラメーターを使用すると、実行するアクションのタイプと、ランディングページが単一のサービスに具体的にリンクされているか、汎用であるかを指定できます。

リンクするサービスを選択するには、次の操作を行う必要があります。

1. ランディングページのダッシュボードのアイコンを使用し ![](assets/edit_darkgrey-24px.png) てアクセスしたランディングページのプロパティを編集し、パラメータを表示 **[!UICONTROL Job]** します。

   ![](assets/lp_edit_properties_button.png)

1. ドロッ **[!UICONTROL Subscription]** プダウンリスト **[!UICONTROL Specific actions]** からを選択します。

   ![](assets/lp_parameters_5.png)

1. ランディング **[!UICONTROL Specific service]** ページを単一のサービスにリンクする場合に選択します。 ランディングページで複数のサービスを使用する場合は、このオプションを選択しないでください。

   このオプション **[!UICONTROL Specified service in the URL]** を使用して、ランディングページを複数のサービスで使用できるようにします。 したがって、サービスを設定する際は、ランディングページを参照する必要があります。

## 権限の設定とデータのプリロード {#setting-permissions-and-pre-loading-data}

ランディングページへのアクセスは、例えばキャンペーンから送信されるメッセージ内のリンクから来た、特定の組織単位に対して、識別された訪問者に制限できます。
識別された訪問者の場合は、ランディングページでそのデータを事前に読み込むことができます。 手順は次のとおりです。

1. ランディングページのダッシュボードのアイコンを使用し ![](assets/edit_darkgrey-24px.png) てアクセスしたランディングページのプロパティを編集し、パラメータを表示 **[!UICONTROL Access & loading]** します。

   ![](assets/lp_edit_properties_button.png)

1. Select **[!UICONTROL Preload visitor data]**.

   ページの訪問者がデータベース内のプロファイルに対応する場合、そのデータはデータベースデータにマップされたフォームのフィールドに表示され、ランディングページのパーソナライゼーション要素が考慮されます。

   ![](assets/lp_parameters_3.png)

また、次のこともできます。

* 次のオプションを使用して、URLパラメーターを使用して訪問者を識別 **[!UICONTROL Authorize visitor identification via URL parameters]** します。次に、読み込みキーを選択し、対応するURLのパラメーターを使用してフィルターパラメーターをマッピングする必要があります。
* このオプションを使用して、すべての訪問者がランディングページにアクセスすることを許 **[!UICONTROL Authorize unidentified visitors]** 可します。

ランディングページは、組織単位にリンクすることもできます。 これにより、様々なランディングページへのユーザーのアクセスが定義されます。 組織単位を割り当てるには：

1. アイコンを使用してランディングページのプロパティにアク **[!UICONTROL Edit properties]** セスします。

   ![](assets/lp_parameters_google3.png)

1. を展開しま **[!UICONTROL Access authorization]**&#x200B;す。

1. ドロップダウンメニューをクリックし、組織単位を選択します。 組織単位の作成方法の詳細については、このページを参照してく [ださい](../../administration/using/organizational-units.md)。

   ![](assets/lp_org_unit_2.png)

1. 、およ **[!UICONTROL Created by]**&#x200B;び各フ **[!UICONTROL Created]**&#x200B;ィー **[!UICONTROL Access authorization]** ルドが自 **[!UICONTROL Last modified]** 動的に入力されます。

1. 「&gt;」をク **[!UICONTROL Confirm]** リックしま **[!UICONTROL Save]**&#x200B;す。

これで、選択した組織単位内のユーザーのみがランディングページにアクセスし、管理できるようになります。

![](assets/lp_org_unit_3.png)

## Google reCAPTCHAの設定 {#setting-google-recaptcha}

ランディングページにGoogle reCAPTCHA V3を設定して、ボットによるスパムや悪用からGoogle ReCAPTCHA V3を保護できます。 ランディングページでこのページを使用するには、まず外部アカウントを作成する必要があります。 設定方法の詳細については、この節を参照してく [ださい](../../administration/using/external-accounts.md#google-recaptcha-external-account)。

Google reCAPTCHA V3外部アカウントが設定されたら、それをランディングページに追加できます。

1. ランディングページを公開する前に、ランディングページのダッシュボードからアイコンを使用してアク ![](assets/edit_darkgrey-24px.png) セスしたページのプロパティにアクセスします。

   ![](assets/lp_parameters_google3.png)

1. メニューを展開 **[!UICONTROL Access & loading]** します。
1. Check the **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]** option.
1. 以前に作成したGoogle reCAPTCHA外部アカウントを選択します。

   ![](assets/lp_parameters_google.png)

1. Click **[!UICONTROL Confirm]**.

これで、ランディングページがGoogle reCAPTCHAで設定され、ページの下部に表示されます。

![](assets/lp_parameters_google2.png)

その後、Google reCAPTCHAは、ユーザーのページでのインタラクションに基づいてスコアを返します。 スコアを確認するには、 [Google管理コンソールに接続します](https://g.co/recaptcha/admin)。

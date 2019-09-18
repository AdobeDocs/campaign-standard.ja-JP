---
title: ランディング·ページの設計
seo-title: ランディング·ページの設計
description: ランディング·ページの設計
seo-description: 次の手順に従って、ランディング·ページの内容を設計し、サービスにリンクします。
page-status-flag: 未活性化の
uuid: de6fe190-835c-40fd-8101-a809b430b423
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: チャンネル
content-type: 参照
topic-tags: ランディング·ページ
discoiquuid: bd77d6f0-3143-4030-a91b-988a2bebc534
context-tags: ランディングページ，メイン
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: aa52fcca887c9423476a1bc0160d340f255b9ac8

---


# ランディング·ページの設計{#designing-a-landing-page}

## コンテンツデザインについて {#about-content-design}

ランディング·ページは、任意のマーケティング·アクティビティ [として作成されま](../../start/using/marketing-activities.md#about-marketing-activities)す。

ランディング·ページを設計する場合は、次の内容を定義する必要があります。

* ページ自体
* 確認ページ
* エラーページ。

アクションバーの下のスイッチャを使用して、各ページを表示および設定します。

これらのページの内容は、キャンペーンコンテンツエディタを使用して設計されています。 「設計の内容」を [参照してください](../../channels/using/about-landing-page-content-design.md)。

## フォームフィールドのマッピング {#mapping-form-fields}

入力フィールドは、キャンペーンデータベースにデータを格納または更新するために使用されます。 このためには、データベースフィールドを入力ゾーン、ラジオボタン、またはチェックボックスタイプブロックとリンクする必要があります。 これを行うには、次の手順に従います。

1. ランディングページでブロックを選択します。
1. パレットのパ **[!UICONTROL Form data]** ーツを完成させます。

   ![](assets/editing_lp_content_4.png)

1. 選択領域のフォームフィールドにリンクするデータベースフィールドを **[!UICONTROL Field]** 選択します。

   このオプション **[!UICONTROL Mandatory]** をオンにした場合、ページは、ユーザーがこのフィールドを入力した場合にのみ送信できます。 必須フィールドが完了していない場合は、ユーザーがページを検証すると、エラーメッセージが表示されます。

   >[!NOTE]
   >
   >ランディング·ページは、プロファイルでのみマップで **きます**。

1. 選択領域で、 、などを選択して、フ **[!UICONTROL Text]**&#x200B;ィールドの **[!UICONTROL Number]**&#x200B;種類を **[!UICONTROL Date]** 定義 **[!UICONTROL HTML type of the field]** します。

>[!NOTE]
>
>組み込みのランディング·ページのデフォルト·フィールドは、事前に構成されています。 必要に応じて修正できます。

## フォームの送信 {#submitting-the-form}

ビジターが「送信」ボタンをクリックしたときに実行するアクションを選択できます。 これを行うには、次の手順に従います。

1. ランディング·ページの送信ボタンを選択します。
1. 左側のパネルのドロップダウンリストからアクションを選択します。 次の操作が可能です。(ペ **[!UICONTROL Refresh]** ージを更新)と **[!UICONTROL Next page]** （確認ページを表示）。

   ![](assets/editing_lp_content_5.png)

また、ボタンのラベルを変更したり、特定のリンクを構成することもできます。 これを行うには、次の手順に従います。

1. 「発行」ボタンを選択します。
1. 左側のパネルのボ ![](assets/lp_link_properties.png) タンをクリックします。
1. ボタンのラベルを入力し、リンクのタイプ、そのプロパティ、およびターゲットを選択します。

   ![](assets/lp_link_custom.png)

## フォームをサービスにリンクする {#linking-a-form-to-a-service}

フォームをサービスにリンクして、プロファイルがランディング·ページを検証する際に特定のサービスを購読できるようにすることができます。

ランディング·ページをリンクするパラメータを使用すると、実行するアクション·タイプ、およびランディング·ページが単一のサービスに特別にリンクされているか、ジェネリックであるかを指定できます。

リンクするサービスを選択するには、次の操作を行う必要があります。

1. ランディング·ページ·ダッシュボードのアイコンを使用してアク ![](assets/edit_darkgrey-24px.png) セスするランディング·ページのプロパティを編集し、パラメータを表 **[!UICONTROL Job]** 示します。

   ![](assets/lp_edit_properties_button.png)

1. ドロップ **[!UICONTROL Subscription]** ダウンリスト **[!UICONTROL Specific actions]** からを選択します。

   ![](assets/lp_parameters_5.png)

1. 選択す **[!UICONTROL Specific service]** ると、ランディング·ページが1つのサービスにリンクされます。 ランディング·ページで複数のサービスを使用する場合は、このオプションを選択しないでください。

   オプションを使 **[!UICONTROL Specified service in the URL]** 用して、ランディング·ページを複数のサービスに使用できるようにします。 したがって、サービスを構成する際にはランディング·ページを参照する必要があります。

### ランディングページの送信の確認 {#confirm-a-landing-page-submission}

ビジターがランディング·ページを送信すると、トリガーされるアクションを構成できます。 これを行うには、次の手順に従います。

1. ランディング·ページ·ダッシュボードのアイコンを使用してアク ![](assets/edit_darkgrey-24px.png) セスするランディング·ページのプロパティを編集し、パラメータを表 **[!UICONTROL Job]** 示します。

   ![](assets/lp_edit_properties_button.png)

1. [ ]セクシ **[!UICONTROL Specific actions]** ョンで、自動メ **[!UICONTROL Start sending message]** ッセージの送信を決定する場合に選択します。たとえば、サービスへの購読を確認します。 次に、電子メール配信テンプレートを選択する必要があります。

   確認メッセージがサービス·レベルですでに構成されている場合は、複数の確認メッセージを送信しないように、この画面で確認メッセージを選択しないでください。 「サービスの [構成」を参照してください](../../audiences/using/creating-a-service.md)。

1. [作成] **[!UICONTROL Additional data]** を選択すると、ランディング·ページの送信時に追加のデータを保存できます。 このデータは、ページにアクセスしたユーザーには表示されません。 定数値のみが考慮されます。

   ![](assets/lp_parameters_6.png)

## 権限の設定とデータの事前読み込み {#setting-permissions-and-pre-loading-data}

ランディング·ページへのアクセスは、たとえばキャンペーンから送信されるメッセージのリンクから来た特定の訪問者に制限できます。 この場合、ランディング·ページでデータをプリロードできます。 これを行うには、次の手順に従います。

1. ランディング·ページ·ダッシュボードのアイコンを使用してアク ![](assets/edit_darkgrey-24px.png) セスするランディング·ページのプロパティを編集し、パラメータを表 **[!UICONTROL Access & loading]** 示します。

   ![](assets/lp_edit_properties_button.png)

1. Select **[!UICONTROL Preload visitor data]**.

   ページのビジターがデータベース内のプロファイルに対応する場合は、データベースデータと共にマップされたフォームのフィールドにそのデータが表示され、ランディング·ページのパーソナライズ要素が考慮されます。

   ![](assets/lp_parameters_3.png)

次の操作も実行できます。

* URLパラメータを使用して、次のオプションを使用してビジターを識別 **[!UICONTROL Authorize visitor identification via URL parameters]** します。次に、読み込みキーを選択し、対応するURLのパラメータを使用してフィルタパラメータをマップする必要があります。
* オプションを使用して、任意のビジターがランディング·ページにアクセスできるように **[!UICONTROL Authorize unidentified visitors]** します。

## Google reCAPTCHAの設定 {#setting-google-recaptcha}

Google reCAPTCHA V3をランディング·ページと共に設定し、ボットによるスパムや悪用から保護できます。 ランディング·ページで使用するには、まず外部アカウントを作成する必要があります。 設定方法の詳細については、このセクションを参照してく [ださい](../../administration/using/external-accounts.md#google-recaptcha-external-account)。

Google reCAPTCHA V3外部アカウントが設定されたら、次のランディングページに追加できます。

1. ランディング·ページを公開する前に、ランディング·ページのダッシュボードからアイコンを使用してアク ![](assets/edit_darkgrey-24px.png) セスするページ·プロパティにアクセスします。

   ![](assets/lp_parameters_google3.png)

1. メニューを展開 **[!UICONTROL Access & loading]** します。
1. オプションを確認 **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]** します。
1. 以前に作成したGoogle reCAPTCHA外部アカウントを選択します。

   ![](assets/lp_parameters_google.png)

1. Click **[!UICONTROL Confirm]**.

これで、ランディング·ページがGoogle reCAPTCHAで設定され、ページの下部に表示されます。

![](assets/lp_parameters_google2.png)

次に、Google reCAPTCHAは、ユーザーのページとのやり取りに基づいてスコアを返します。 スコアを確認するには、 [Google管理コンソールに接続します](https://g.co/recaptcha/admin)。

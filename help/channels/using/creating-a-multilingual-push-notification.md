---
title: 多言語プッシュ通知の作成
seo-title: 多言語プッシュ通知の作成
description: 多言語プッシュ通知の作成
seo-description: 多言語プッシュ通知を作成して、ユーザーを好みの言語や地域にターゲット設定します。
page-status-flag: 常にアクティブ化されていない
uuid: d4aff741- e969-47c6- bae8-787c6c673191
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: プッシュ通知
discoiquuid: f9bb2235- d388-4025-9ace-734beb0c1961
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# 多言語プッシュ通知の作成{#creating-a-multilingual-push-notification}

## 多言語プッシュ通知について {#about-multilingual-push-notification}

ユーザーの好みの言語と地域に基づいてメッセージを送信して、プッシュ通知コンテンツをパーソナライズします。コンテンツエディターで多言語プッシュ通知コンテンツバリアントを直接インポートし、単一の配信で多言語プッシュ通知を送信できます。

この機能は、プッシュ通知に使用する配信テンプレートに応じて、受信者のプロファイルまたはシステム言語の環境設定で指定された優先言語のいずれかを利用します。特定のユーザーに言語の環境設定が入力されていない場合、多言語プッシュ通知の作成時に定義されるデフォルトのバリアントが使用されます。プロファイルおよび購読者の管理方法について詳しくは、本 [ガイドを参照](../../audiences/using/about-profiles-and-audiences.md)してください。

![](assets/multivariant_push_1.png)

プッシュ通知配信に多言語コンテンツバリアントを使用するには、次の手順に従います。

* [手順1:多言語コンテンツバリアントのアップロード](../../channels/using/creating-a-multilingual-push-notification.md#step-1--upload-multilingual-content-variant)
* [手順2:多言語コンテンツバリアントを使用したプッシュ通知のプレビューとファイナライズ](../../channels/using/creating-a-multilingual-push-notification.md#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [手順3:多言語プッシュ通知配信の送信と分析](../../channels/using/creating-a-multilingual-push-notification.md#step-3--send-and-analyze-multilingual-push-notification-delivery)

## 手順1:多言語コンテンツバリアントのアップロード {#step-1--upload-multilingual-content-variant}

多言語プッシュ通知をパーソナライズする前に、まず多言語配信テンプレートにコンテンツバリアントをアップロードし、配信を作成する必要があります。

>[!NOTE]
>
>また、言語バリアントごとに手動でバリアントを作成する場合は、この手順をスキップすることもできます。

1. で **[!UICONTROL Marketing activities]**、ボタンを **[!UICONTROL Create]** クリックして選択 **[!UICONTROL Push notification]**&#x200B;します。
1. モバイルアプリケーション **[!UICONTROL Send multilingual push to Campaign profiles]** から通知を受信するためにオプトインしているすべてのユーザーに、モバイルアプリケーションまたはテンプレート **[!UICONTROL Send multilingual push to app subscriber]** を登録しているAdobe Campaignプロファイルをターゲットにするには、テンプレートを選択します。

   ![](assets/multivariant_push_2.png)

1. プッシュ通知プロパティを入力し、 **[!UICONTROL Associate a Mobile App to a delivery]** フィールド内のモバイルアプリを選択します。

   ドロップダウンには、SDK V4およびAdobe Experience Platform SDKアプリケーションの両方が表示されることに注意してください。

1. **[!UICONTROL Audiences]** ウィンドウで、クエリーをドラッグ&amp;ドロップして、オーディエンスを微調整します。

   追加されるクエリーは、選択したテンプレートによって異なります。 **[!UICONTROL Send multilingual push to Campaign profiles]** テンプレートを選択すると、モバイルアプリケーションの既知の受信者に問い合わせることができます。一方、 **[!UICONTROL Send multilingual push to app subscriber]** テンプレートを選択すると、オプトインしている特定のアプリのすべての購読者に問い合わせることができます。

   ![](assets/push_notif_audience.png)

1. **[!UICONTROL Manage Content Variants]** ウィンドウで、ファイルをドラッグ&amp;ドロップするか、コンピューターからファイルを選択します。

   ファイルはUTF8エンコードされており、特定のレイアウトを持つ必要があります。このレイアウトは **[!UICONTROL Download the sample file]** 、オプションをクリックすることで検出できます。ロケール値に適切な構文も使用する必要があります。ファイル形式とサポートされているロケールについて詳しくは [、こちらのテクニカルノート](http://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html)を参照してください。

   ![](assets/multivariant_push_4.png)

1. ファイルをアップロードすると、言語バリアントが自動的にタブに **[!UICONTROL Variants]** 入力されます。ターゲットユーザーに指定された言語が指定されていない場合は、デフォルトコンテンツバリアントになるファイル **[!UICONTROL Default variant]** を指定できます。

   ![](assets/multivariant_push_5.png)

1. **[!UICONTROL Variant selection]** タブには、配信テンプレートに応じて考慮される言語の優先順位を決定するスクリプトが表示されます。これは、変更を必要としないままのスクリプトです。
1. 読み込んだファイルに存在しないバリエーションを追加する場合は、ボタンを **[!UICONTROL Add an element]** クリックし、必要に応じて新しい言語バリアントを追加します。

   ファイルからアップロードされたもの以外のバリアントを追加すると、この言語にリンクされたコンテンツは一切表示されません。コンテンツを配信ダッシュボードで直接編集する必要があります。

   ![](assets/multivariant_push_6.png)

1. 設定が完了したら、をクリック **[!UICONTROL Create]** します。いつでも **[!UICONTROL Content variant]** ウィンドウに戻って、配信ダッシュボードから変更を加えることができます。

   ![](assets/multivariant_push_8.png)

多言語プッシュ通知をパーソナライズできるようになりました。

## 手順2:多言語コンテンツバリアントを使用したプッシュ通知のプレビューとファイナライズ {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

コンテンツバリアントを含むファイルをアップロードした後、プッシュ通知配信から様々なバリアントをプレビューできるようになりました。

ファイルからアップロードされたものに加えて、より多くのバリアントを作成して編集することもできます。

1. 配信ダッシュボードの **[!UICONTROL Content]** ウィンドウでは、ドロップダウンで選択した言語に応じてプッシュ通知コンテンツをプレビューできます。

   ![](assets/multivariant_push_7.png)

1. 特定の言語に対してコンテンツバリアントが指定されていない場合は、プレビューの下のベルアイコンをクリックして、この言語バリアントにコンテンツを追加します。

   ウィンドウを **[!UICONTROL Content]** クリックすると、ドロップダウンで選択した言語の内容が表示されます。このウィンドウで行った変更は、1言語にのみ影響します。

1. コンテンツバリアントをクリックして、パーソナライゼーションフィールドなどのようにカスタマイズすることもできます。

   プッシュ通知をカスタマイズする方法について詳しくは、この [節](../../channels/using/customizing-a-push-notification.md)を参照してください。

   ![](assets/multivariant_push_9.png)

1. 言語バリアントを追加または削除する **[!UICONTROL Content variant]** 場合は、ウィンドウをクリックします。

   新しい言語を追加することで、追加された言語にリンクされているプッシュ通知にコンテンツを手動で追加する必要があります。

   ![](assets/multivariant_push_10.png)

多言語プッシュ通知配信を送信できるようになりました。

## 手順3:多言語プッシュ通知配信の送信と分析 {#step-3--send-and-analyze-multilingual-push-notification-delivery}

多言語コンテンツバリアントプッシュ通知がユーザーに送信できるようになりました。

1. 送信の準備を開始するには、ボタンを **[!UICONTROL Prepare]** クリックします。
1. 警告がなくても準備が完了したら、ボタンを **[!UICONTROL Confirm]** クリックして多言語プッシュの送信を開始できます。

   ![](assets/multivariant_push_12.png)

1. プッシュ通知を正常に送信したら、アイコンを **[!UICONTROL Reports]** クリック **[!UICONTROL Dynamic reports]** して、配信の成功を分析します。

   ![](assets/multivariant_push_13.png)

1. Select **[!UICONTROL Push notification report]**.
1. ディメンションを **[!UICONTROL Variant]** パネルにドラッグ&amp;ドロップして、データのフィルタリングを開始します。

   ![](assets/multivariant_push_11.png)

受信者に多言語プッシュ通知配信の影響を測定できるようになりました。

**関連トピック:**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)
* [1つのワークフローを使用した多言語オーディエンスのリーチ](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)

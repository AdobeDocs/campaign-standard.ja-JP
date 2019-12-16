---
title: 多言語プッシュ通知の作成
description: 多言語のプッシュ通知を作成して、ユーザーの好みの言語と地域をターゲットにします。
page-status-flag: never-activated
uuid: d4aff741-e969-47c6-bae8-787c6c673191
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: f9bb2235-d388-4025-9ace-734beb0c1961
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fc9c6371732aa0eba9e675d2709cd62c25b27b96

---


# 多言語プッシュ通知の作成{#creating-a-multilingual-push-notification}

## 多言語プッシュ通知について {#about-multilingual-push-notification}

ユーザーの好みの言語と地域に基づいてメッセージを送信し、プッシュ通知コンテンツをパーソナライズします。 多言語のプッシュ通知コンテンツバリアントをコンテンツエディターに直接読み込み、多言語のプッシュ通知を1回の配信で送信できます。

この機能は、プッシュ通知に使用される配信テンプレートに応じて、受信者のプロファイルで指定された優先言語またはモバイルアプリ購読者のシステム言語設定を利用します。 特定のユーザーに対して言語設定が設定されていない場合、システムは、多言語プッシュ通知の作成時に定義されたデフォルトのバリアントを使用します。 プロファイルとサブスクリプションの管理方法について詳しくは、このガイドを参照して [ください](../../audiences/using/about-profiles-and-audiences.md)。

![](assets/multivariant_push_1.png)

プッシュ通知配信で多言語コンテンツバリアントを使用するには、次の手順に従います。

* [手順1:多言語コンテンツバリアントのアップロード](#step-1--upload-multilingual-content-variant)
* [手順2:多言語コンテンツバリアントを使用したプッシュ通知のプレビューと最終処理](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [手順3:多言語プッシュ通知配信の送信と分析](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## 手順1:多言語コンテンツバリアントのアップロード {#step-1--upload-multilingual-content-variant}

多言語プッシュ通知をパーソナライズする前に、まずコンテンツバリアントを多言語配信テンプレートにアップロードし、配信を作成する必要があります。

>[!NOTE]
>
>また、各言語バリアントに対して手動でバリアントを作成する場合は、この手順をスキップすることもできます。

1. で、ボタ **[!UICONTROL Marketing activities]**&#x200B;ンをクリックし **[!UICONTROL Create]** てを選択しま **[!UICONTROL Push notification]**&#x200B;す。
1. モバイルアプリケー **[!UICONTROL Send multilingual push to Campaign profiles]****[!UICONTROL Send multilingual push to app subscriber]** ションに登録しているAdobe Campaignプロファイルまたはテンプレートをターゲットにして、モバイルアプリケーションからの通知の受信を許可しているすべてのユーザーにプッシュ通知を送信する場合は、テンプレートを選択します。

   ![](assets/multivariant_push_2.png)

1. プッシュ通知プロパティを入力し、フィールドでモバイルアプリを選択 **[!UICONTROL Associate a Mobile App to a delivery]** します。

   ドロップダウンにはSDK V4とAdobe Experience Platform SDKの両方のアプリケーションが表示されます。

1. ウィンドウで、ク **[!UICONTROL Audiences]** エリをドラッグ&amp;ドロップしてオーディエンスを微調整します。

   追加されるクエリーは、選択したテンプレートに依存します。テンプレートを選択した場合 **[!UICONTROL Send multilingual push to Campaign profiles]** は、モバイルアプリケーションの既知の受信者に対してクエリを実行できます。 一方、テンプレートを選択した **[!UICONTROL Send multilingual push to app subscriber]** 場合は、オプトインした特定のアプリのすべての購読者に対してクエリを実行できます。
   >[!NOTE]
   >
   >特定の言語を使用するオーディエンスをターゲット設定する場合は、CSVファイルにターゲット設定されたすべての言語を一覧表示する必要があります。

   ![](assets/push_notif_audience.png)

1. ウィンドウで、 **[!UICONTROL Manage Content Variants]** ファイルをドラッグ&amp;ドロップするか、コンピューターからファイルを選択します。

   ファイルはUTF8でエンコードされ、オプションをクリックすると見つかる特定のレイアウトを持つ必要があ **[!UICONTROL Download the sample file]** ります。 また、ロケールの値に対して正しい構文を使用する必要があります。 ファイル形式とサポートされているロケールについて詳しくは、このテクニカルノートを参照して [くださ](https://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html)い。

   ![](assets/multivariant_push_4.png)

1. ファイルをアップロードすると、言語バリアントがタブに自動的に入力さ **[!UICONTROL Variants]** れます。 対象ユーザーに優先言語が指定されていな **[!UICONTROL Default variant]** い場合に、デフォルトのコンテンツバリアントとなるファイルを指定できます。

   ![](assets/multivariant_push_5.png)

1. このタ **[!UICONTROL Variant selection]** ブには、配信テンプレートに応じてどの言語設定を考慮するかを決定するスクリプトが用意されています。 これは、変更を行う必要のない、あらかじめ用意されたスクリプトです。
1. 読み込んだファイルに存在しないバリアントをさらに追加する場合は、ボタンをクリックし、必要な数だけ新しい言語バリア **[!UICONTROL Add an element]** ントを追加することができます。

   ファイルからアップロードされた以外のバリアントを追加すると、コンテンツはこの言語にリンクされません。 配信ダッシュボードでコンテンツを直接編集する必要があります。

   ![](assets/multivariant_push_6.png)

1. 設定が **[!UICONTROL Create]** 完了したら、をクリックします。 いつでもウィンドウに戻って、配信ダッ **[!UICONTROL Content variant]** シュボードから変更を加えることができます。

   ![](assets/multivariant_push_8.png)

これで、多言語プッシュ通知のパーソナライズを開始できます。

## 手順2:多言語コンテンツバリアントを使用したプッシュ通知のプレビューと最終処理 {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

コンテンツバリアントを含むファイルをアップロードした後、プッシュ通知配信から様々なバリアントをプレビューできるようになりました。

また、ファイルからアップロードされたバリアントに加えて、より多くのバリアントを作成して編集することもできます。

1. 配信ダッシ **[!UICONTROL Content]** ュボードのウィンドウで、選択した言語に応じてプッシュ通知のコンテンツをプレビューできます。

   ![](assets/multivariant_push_7.png)

1. 特定の言語に対してコンテンツバリアントが指定されていない場合は、プレビューの下のベルアイコンをクリックして、この言語バリアントへのコンテンツの追加を開始します。

   ウィンドウをクリ **[!UICONTROL Content]** ックすると、プッシュ通知はドロップダウンで選択した言語のコンテンツを表します。 このウィンドウで行った変更は、1つの言語にのみ影響します。

1. また、コンテンツバリアントをクリックして、パーソナライゼーションフィールドなどを使用してさらにカスタマイズすることもできます。

   プッシュ通知のカスタマイズ方法について詳しくは、この節を参照してく [ださい](../../channels/using/customizing-a-push-notification.md)。

   ![](assets/multivariant_push_9.png)

1. 言語バリアント **[!UICONTROL Content variant]** を追加または削除する場合は、このウィンドウをクリックします。

   新しい言語を追加すると、追加した言語にリンクされたプッシュ通知にコンテンツを手動で追加する必要があることに注意してください。

   ![](assets/multivariant_push_10.png)

これで、多言語プッシュ通知配信を送信する準備が整いました。

## 手順3:多言語プッシュ通知配信の送信と分析 {#step-3--send-and-analyze-multilingual-push-notification-delivery}

これで、多言語コンテンツバリアントプッシュ通知をユーザーに送信する準備が整いました。

1. 送信の準備を開始するには、ボタンをクリック **[!UICONTROL Prepare]** します。
1. 警告なしで準備が完了したら、ボタンをクリックして多言語 **[!UICONTROL Confirm]** プッシュの送信を開始できます。

   ![](assets/multivariant_push_12.png)

1. プッシュ通知が正常に送信されたら、アイコンをク **[!UICONTROL Reports]** リックし、 **[!UICONTROL Dynamic reports]** 配信の成功を分析します。

   ![](assets/multivariant_push_13.png)

1. Select **[!UICONTROL Push notification report]**.
1. ディメンションをパネルにドラ **[!UICONTROL Variant]** ッグ&amp;ドロップして、データのフィルタリングを開始します。

   ![](assets/multivariant_push_11.png)

多言語のプッシュ通知配信が受信者に与える影響を測定できるようになりました。

**関連トピック：**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)
* [1つのワークフローを使用した多言語オーディエンスの提供](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)

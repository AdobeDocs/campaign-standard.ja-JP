---
solution: Campaign Standard
product: campaign
title: 多言語プッシュ通知の作成
description: 多言語のプッシュ通知を作成して、ユーザーを優先言語と地域のターゲットに設定します。
audience: channels
content-type: reference
topic-tags: push-notifications
feature: プッシュ
role: User
level: Intermediate
exl-id: 1b81f6e9-cb31-4664-af78-22e70043fbc8
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '921'
ht-degree: 3%

---

# 多言語プッシュ通知の作成{#creating-a-multilingual-push-notification}

## 多言語プッシュ通知について {#about-multilingual-push-notification}

ユーザーの好みの言語と地域に基づいてメッセージを送信することで、プッシュ通知のコンテンツをパーソナライズします。 多言語のプッシュ通知コンテンツバリアントをコンテンツエディターに直接インポートし、多言語のプッシュ通知を単一の配信で送信できます。

この機能は、プッシュ通知に使用する配信テンプレートに応じて、受信者のプロファイルで指定された優先言語またはモバイルアプリ購読者のシステム言語の優先設定を利用します。 特定のユーザーに対して言語の環境設定が設定されていない場合、多言語のプッシュ通知の作成時に定義されたデフォルトのバリアントが使用されます。 プロファイルと購読者の管理方法について詳しくは、この[ガイド](../../audiences/using/get-started-profiles-and-audiences.md)を参照してください。

![](assets/multivariant_push_1.png)

プッシュ通知配信で多言語コンテンツのバリエーションを使用するには、次の手順に従います。

* [手順1:多言語コンテンツバリアントのアップロード](#step-1--upload-multilingual-content-variant)
* [手順2:多言語コンテンツバリアントを使用したプッシュ通知のプレビューと最終決定](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [手順3:多言語プッシュ通知配信の送信と分析](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## 手順1:多言語コンテンツバリアントのアップロード {#step-1--upload-multilingual-content-variant}

多言語のプッシュ通知をパーソナライズする前に、まず多言語の配信テンプレートでコンテンツバリアントをアップロードし、配信を作成する必要があります。

>[!NOTE]
>
>各言語バリアントに対して手動でバリアントを作成する場合は、この手順をスキップすることもできます。

1. **[!UICONTROL Marketing activities]**&#x200B;で&#x200B;**[!UICONTROL Create]**&#x200B;ボタンをクリックし、**[!UICONTROL Push notification]**&#x200B;を選択します。
1. モバイルアプリケーションを購読しているAdobe Campaignプロファイルまたはテンプレート&#x200B;**[!UICONTROL Send multilingual push to app subscriber]**&#x200B;をターゲットにして、モバイルアプリケーションからの通知の受信をオプトインしたすべてのユーザーにプッシュ通知を送信する場合は、テンプレート&#x200B;**[!UICONTROL Send multilingual push to Campaign profiles]**&#x200B;を選択します。

   ![](assets/multivariant_push_2.png)

1. プッシュ通知のプロパティを入力し、「 **[!UICONTROL Associate a Mobile App to a delivery]** 」フィールドでモバイルアプリを選択します。

   ドロップダウンにはSDK V4とAdobe Experience Platform SDKの両方のアプリケーションが表示されることに注意してください。

1. **[!UICONTROL Audiences]**&#x200B;ウィンドウで、クエリをドラッグ&amp;ドロップしてオーディエンスを微調整します。

   追加されるクエリは、選択したテンプレートによって異なります。**[!UICONTROL Send multilingual push to Campaign profiles]**&#x200B;テンプレートを選択した場合は、モバイルアプリケーションの既知の受信者に対してクエリを実行できます。 一方、**[!UICONTROL Send multilingual push to app subscriber]**&#x200B;テンプレートを選択した場合は、オプトインした特定のアプリのすべての購読者に対してクエリを実行できます。
   >[!NOTE]
   >
   >特定の言語でオーディエンスをターゲット設定する場合は、CSVファイルにすべてのターゲット言語をリストする必要があります。

   ![](assets/push_notif_audience.png)

1. **[!UICONTROL Manage Content Variants]**&#x200B;ウィンドウで、ファイルをドラッグ&amp;ドロップするか、コンピューターからファイルを選択します。

   ファイルはUTF8でエンコードする必要があり、**[!UICONTROL Download the sample file]**&#x200B;オプションをクリックすると見つかる特定のレイアウトが必要です。 また、ロケール値に対して正しい構文を使用する必要があります。 ファイル形式とサポートされているロケールについて詳しくは、この[テクニカルノート](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push.html)を参照してください。

   ![](assets/multivariant_push_4.png)

1. ファイルをアップロードすると、言語のバリエーションが自動的に「**[!UICONTROL Variants]**」タブに入力されます。 ターゲットユーザーに優先言語が指定されていない場合は、デフォルトのコンテンツバリアントとなる&#x200B;**[!UICONTROL Default variant]**&#x200B;をファイルに指定できます。

   ![](assets/multivariant_push_5.png)

1. **[!UICONTROL Variant selection]**&#x200B;タブには、配信テンプレートに応じて、考慮する言語設定を決定するスクリプトが表示されます。 これは標準のスクリプトで、変更を加える必要はありません。
1. インポートしたファイルに存在しないバリエーションをさらに追加する場合は、「**[!UICONTROL Add an element]**」ボタンをクリックし、必要な数だけ新しい言語バリエーションを追加します。

   ファイルからアップロードしたバリエーション以外のバリエーションを追加すると、コンテンツはこの言語にリンクされません。 配信ダッシュボードで直接コンテンツを編集する必要があります。

   ![](assets/multivariant_push_6.png)

1. 設定が完了したら、「**[!UICONTROL Create]**」をクリックします。 いつでも&#x200B;**[!UICONTROL Content variant]**&#x200B;ウィンドウに戻って、配信ダッシュボードで変更を加えることができます。

   ![](assets/multivariant_push_8.png)

多言語のプッシュ通知のパーソナライズを開始できるようになりました。

## 手順2:多言語コンテンツバリアントを使用したプッシュ通知のプレビューと最終決定 {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

コンテンツのバリエーションを含むファイルをアップロードした後、プッシュ通知配信から様々なバリエーションをプレビューできるようになりました。

ファイルからアップロードされるバリエーションに加えて、バリエーションを作成および編集することもできます。

1. 配信ダッシュボードの&#x200B;**[!UICONTROL Content]**&#x200B;ウィンドウで、ドロップダウンを使用して、選択した言語に応じてプッシュ通知コンテンツをプレビューできます。

   ![](assets/multivariant_push_7.png)

1. 特定の言語に対してコンテンツバリアントが指定されていない場合は、プレビューの下にあるベルのアイコンをクリックして、この言語バリアントへのコンテンツの追加を開始します。

   **[!UICONTROL Content]**&#x200B;ウィンドウをクリックすると、プッシュ通知は、ドロップダウンで選択した言語のコンテンツを表します。 このウィンドウで行った変更は、1つの言語にのみ影響します。

1. コンテンツバリアントをクリックして、パーソナライゼーションフィールドなど、さらにカスタマイズすることもできます。

   プッシュ通知のカスタマイズ方法について詳しくは、[](../../channels/using/customizing-a-push-notification.md)を参照してください。

   ![](assets/multivariant_push_9.png)

1. 言語バリアントを追加または削除する場合は、**[!UICONTROL Content variant]**&#x200B;ウィンドウをクリックします。

   新しい言語を追加すると、追加した言語にリンクされたプッシュ通知に手動でコンテンツを追加する必要があります。

   ![](assets/multivariant_push_10.png)

これで、多言語のプッシュ通知配信を送信する準備が整いました。

## 手順3:多言語プッシュ通知配信の送信と分析 {#step-3--send-and-analyze-multilingual-push-notification-delivery}

これで、多言語コンテンツバリアントプッシュ通知をユーザーに送信する準備が整いました。

1. 送信の準備を開始するには、「**[!UICONTROL Prepare]**」ボタンをクリックします。
1. 警告なしで準備が完了したら、「**[!UICONTROL Confirm]**」ボタンをクリックして、多言語プッシュの送信を開始できます。

   ![](assets/multivariant_push_12.png)

1. プッシュ通知を正常に送信したら、**[!UICONTROL Reports]**&#x200B;アイコンをクリックし、**[!UICONTROL Dynamic reports]**&#x200B;をクリックして配信の成功を分析します。

   ![](assets/multivariant_push_13.png)

1. 「**[!UICONTROL Push notification report]**」を選択します。
1. **[!UICONTROL Variant]**&#x200B;ディメンションをパネルにドラッグ&amp;ドロップして、データのフィルタリングを開始します。

   ![](assets/multivariant_push_11.png)

受信者に対する多言語のプッシュ通知配信の影響を測定できるようになりました。

**関連トピック：**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)
* [1つのワークフローを使用した多言語オーディエンスへのリーチ](https://helpx.adobe.com/jp/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)

---
title: 多言語プッシュ通知の作成
description: 多言語のプッシュ通知を作成して、ユーザーを優先言語と地域でターゲットに設定します。
audience: channels
content-type: reference
topic-tags: push-notifications
feature: Push
role: User
level: Intermediate
exl-id: 1b81f6e9-cb31-4664-af78-22e70043fbc8
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 2%

---

# 多言語プッシュ通知の作成{#creating-a-multilingual-push-notification}

## 多言語プッシュ通知について {#about-multilingual-push-notification}

ユーザーの設定言語および地域に基づいてメッセージを送信することで、プッシュ通知コンテンツをパーソナライズします。 多言語のプッシュ通知コンテンツバリアントをコンテンツエディターに直接インポートし、単一の配信で多言語のプッシュ通知を送信できます。

この機能は、プッシュ通知に使用する配信テンプレートに応じて、受信者のプロファイルで指定された優先言語またはモバイルアプリ購読者のシステム言語の設定を利用します。 特定のユーザーの言語の環境設定が入力されていない場合、多言語プッシュ通知の作成時に定義されたデフォルトのバリアントが使用されます。 プロファイルおよび購読者の管理方法について詳しくは、 [ガイド](../../audiences/using/get-started-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

プッシュ通知配信で多言語のコンテンツバリアントを使用するには、次の手順に従います。

* [手順 1:多言語コンテンツバリアントのアップロード](#step-1--upload-multilingual-content-variant)
* [手順 2:多言語コンテンツバリアントを使用したプッシュ通知のプレビューと最終決定](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [手順 3:多言語プッシュ通知配信の送信と分析](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## 手順 1:多言語コンテンツバリアントのアップロード {#step-1--upload-multilingual-content-variant}

多言語プッシュ通知をパーソナライズする前に、まず多言語配信テンプレートでコンテンツのバリエーションをアップロードし、配信を作成する必要があります。

>[!NOTE]
>
>また、各言語バリアントに対して手動でバリアントを作成する場合は、この手順をスキップできます。

1. 内 **[!UICONTROL Marketing activities]**、 **[!UICONTROL Create]** ボタンをクリックし、 **[!UICONTROL Push notification]**.
1. テンプレートを選択 **[!UICONTROL Send multilingual push to Campaign profiles]** モバイルアプリケーションまたはテンプレートを購読しているAdobe Campaignプロファイルをターゲットにする場合 **[!UICONTROL Send multilingual push to app subscriber]** ：モバイルアプリケーションからの通知の受信をオプトインしたすべてのユーザーにプッシュ通知を送信します。

   ![](assets/multivariant_push_2.png)

1. プッシュ通知のプロパティを入力し、 **[!UICONTROL Associate a Mobile App to a delivery]** フィールドに入力します。

   ドロップダウンには、SDK V4 とAdobe Experience Platform SDK の両方のアプリケーションが表示されます。

1. 内 **[!UICONTROL Audiences]** ウィンドウを開き、クエリをドラッグ&amp;ドロップしてオーディエンスを微調整します。

   追加されるクエリは、選択したテンプレートによって異なります。もしあなたが **[!UICONTROL Send multilingual push to Campaign profiles]** テンプレートモバイルアプリケーションの既知の受信者に対してクエリを実行できます。 一方、 **[!UICONTROL Send multilingual push to app subscriber]** テンプレートの作成時に、オプトインした特定のアプリのすべての購読者に対してクエリを実行できます。
   >[!NOTE]
   >
   >特定の言語でオーディエンスのターゲットを設定する場合は、CSV ファイルにすべてのターゲット言語を一覧表示する必要があります。

   ![](assets/push_notif_audience.png)

1. 内 **[!UICONTROL Manage Content Variants]** ウィンドウで、ファイルをドラッグ&amp;ドロップするか、コンピューターからファイルを選択します。

   ファイルは UTF8 でエンコードされ、特定のレイアウトを持つ必要があります。レイアウトは、 **[!UICONTROL Download the sample file]** オプション。 また、ロケール値に対しては正しい構文を使用する必要があります。 ファイル形式とサポートされているロケールについて詳しくは、次を参照してください。 [ページ](../../channels/using/generating-csv-multilingual-push.md).

   ![](assets/multivariant_push_4.png)

1. ファイルをアップロードすると、言語のバリエーションが **[!UICONTROL Variants]** タブをクリックします。 なお、 **[!UICONTROL Default variant]** を指定します。

   ![](assets/multivariant_push_5.png)

1. この **[!UICONTROL Variant selection]** 「 」タブには、配信テンプレートに応じて、考慮に入れる言語設定を決定するスクリプトが表示されます。 これは標準のスクリプトで、変更を加える必要はありません。
1. インポートしたファイルに存在しないバリアントをさらに追加する場合は、 **[!UICONTROL Add an element]** ボタンをクリックし、必要な数の新しい言語のバリアントを追加します。

   ファイルからアップロードされたバリエーション以外のバリエーションを追加すると、コンテンツはこの言語にリンクされません。 配信ダッシュボードで直接コンテンツを編集する必要があります。

   ![](assets/multivariant_push_6.png)

1. クリック **[!UICONTROL Create]** 設定が完了したとき。 いつでも **[!UICONTROL Content variant]** ウィンドウが開き、配信ダッシュボードで変更を加えます。

   ![](assets/multivariant_push_8.png)

これで、多言語プッシュ通知のパーソナライズを開始できます。

## 手順 2:多言語コンテンツバリアントを使用したプッシュ通知のプレビューと最終決定 {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

コンテンツバリアントを含むファイルをアップロードした後、プッシュ通知配信とは異なるバリアントをプレビューできるようになりました。

ファイルからアップロードされたバリエーションに加えて、より多くのバリエーションを作成および編集することもできます。

1. 内 **[!UICONTROL Content]** ウィンドウを開くと、ドロップダウンリストで、選択した言語に応じてプッシュ通知コンテンツをプレビューできます。

   ![](assets/multivariant_push_7.png)

1. 特定の言語に対してコンテンツバリアントが指定されていない場合は、プレビューの下にあるベルのアイコンをクリックして、この言語バリアントへのコンテンツの追加を開始します。

   この **[!UICONTROL Content]** ウィンドウに表示されるプッシュ通知は、ドロップダウンで選択した言語のコンテンツを表します。 このウィンドウで行った変更は、1 つの言語にのみ影響します。

1. コンテンツバリアントをクリックして、パーソナライゼーションフィールドなどを使用してさらにカスタマイズすることもできます。

   プッシュ通知のカスタマイズ方法について詳しくは、次を参照してください。 [セクション](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. 次をクリック： **[!UICONTROL Content variant]** ウィンドウを開きます。

   新しい言語を追加すると、追加した言語にリンクされたプッシュ通知にコンテンツを手動で追加する必要があります。

   ![](assets/multivariant_push_10.png)

これで、多言語プッシュ通知配信を送信する準備が整いました。

## 手順 3:多言語プッシュ通知配信の送信と分析 {#step-3--send-and-analyze-multilingual-push-notification-delivery}

これで、多言語コンテンツバリアントプッシュ通知をユーザーに送信する準備が整いました。

1. 送信の準備を開始するには、 **[!UICONTROL Prepare]** 」ボタンをクリックします。
1. 警告を出さずに準備が完了したら、 **[!UICONTROL Confirm]** ボタンをクリックして、多言語プッシュの送信を開始します。

   ![](assets/multivariant_push_12.png)

1. プッシュ通知が正常に送信されたら、 **[!UICONTROL Reports]** アイコンを選択し、 **[!UICONTROL Dynamic reports]** 配信の成功を分析する。

   ![](assets/multivariant_push_13.png)

1. 「**[!UICONTROL Push notification report]**」を選択します。
1. 次をドラッグ&amp;ドロップ： **[!UICONTROL Variant]** ディメンションをパネルに追加して、データのフィルタリングを開始します。

   ![](assets/multivariant_push_11.png)

多言語プッシュ通知配信が受信者に与える影響を測定できるようになりました。

**関連トピック：**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)

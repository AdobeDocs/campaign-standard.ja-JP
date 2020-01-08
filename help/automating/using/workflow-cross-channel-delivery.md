---
title: 「ワークフローの使用例：クロスチャネル配信」
description: 「ワークフローの使用例：クロスチャネル配信」
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,wait,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f959441647d1fea41ecce2fc41e3cad3cb536bac

---


# ワークフローの使用例：クロスチャネル配信の作成{#cross-channel-delivery}

このドキュメントでは、標準的な使用例を基に Adobe Campaign のクロスチャネル配信ワークフロー作成機能を紹介します。

ここでの目的は、データベースの受信者からオーディエンスを選択し、最初のグループに電子メールを送信し、2番目のグループにSMSメッセージを送信することを目的として、2つの異なるグループにセグメント化することです。

![](assets/wkf_segment_overview.png)

Adobe Campaignで使用できるワークフローと様々なチャネルの詳細については、以下のドキュメントを参照してください。

* [ワークフローの検索](../../automating/using/discovering-workflows.md)
* [通信チャネルの検出](../../channels/using/discovering-communication-channels.md)

## ワークフローの作成 {#creating-workflow}

任意のグループに 2 つの異なる配信を送信するには、まずターゲットを定義する必要があります。

そのためには、受信者を特定するクエリを作成しなければならないので、ワークフローを作成する必要があります。

プログラムまたは選択したキャンペーンで新しいワークフローを作成します。

1. で、を **[!UICONTROL Marketing Activities]**クリックし**[!UICONTROL Create]** てを選択しま **[!UICONTROL Workflow]**す。
1. ワークフロー **[!UICONTROL New Workflow]**タイプとして選択し、をクリックしま**[!UICONTROL Next]**&#x200B;す。
1. ワークフローのプロパティを入力し、をクリックしま **[!UICONTROL Create]**す。

ワークフローを作成する詳細な手順は、「ワークフローの構築」セク [ションに記載され](../../automating/using/building-a-workflow.md) ます。

## クエリーアクティビティの作成 {#creating-query-activity}

ワークフローを作成したら、そのインターフェイスにアクセスできます。

ワークフローにQueryアクティビティを挿入し、配信を受け取るプロファイルをターゲットにします。

1. /で、 **[!UICONTROL Activities]**をドラ**[!UICONTROL Targeting]**&#x200B;ッグ&amp;ドロップしま **[!UICONTROL Query activity]**す。
1. アクティビティをダブルクリックします。
1. タブで、シ **[!UICONTROL Target]**ョートカットを参照し、オーディエンスの1つを選択[します](../../audiences/using/about-audiences.md)。
1. ショートカットを編集ゾーンにドラッグ&amp;ドロップします。 選択したショートカットのタイプに応じて、ウィンドウが表示されます。
1. ターゲット要素を設定し、クエリを確認します。

![](assets/wkf_segment_query.png)

1つまたは複数の要素に対してクエリーを作成できます。

このボタンを **[!UICONTROL Count]**使用して、クエリーの対象となるプロファイル数の推定を確認します。

Queryアクティビティを構築する詳細な手順は、「 [Query](../../automating/using/query.md) 」セクションに示します。

## セグメント化アクティビティの作成 {#creating-segmentation-activity}

クエリアクティビティでターゲットを特定したら、ターゲットを 2 つの別々の母集団にセグメント化する条件を選択する必要があります。一方は E メールを受信し、もう一方は SMS を受信します。

クエリーで上流に計算された母集団から1つまたは複数のセグメントを作成するには、セグメント化アクティビティを使用する必要があります。

![](assets/wkf_segment_activity.png)

**E メール**&#x200B;グループでは、E メールアドレスが定義されているが、携帯電話番号がない受信者をターゲットにします。**SMS** グループには、携帯電話番号がプロファイルに保存されている受信者が含まれます。

最初の移行（電子メール）を設定するには：

1. タブには、 **[!UICONTROL Segments]**デフォルトで最初のセグメントが表示されます。 プロパティを編集して、そのセグメントを設定します。

   ![](assets/wkf_segment_properties.png)

1. プロファイルのフィルター条 **[!UICONTROL Email]**件を選択します。

   ![](assets/wkf_segment_email.png)

1. 画面に表示される新しいウィンドウで、演算子を選択し **[!UICONTROL Is not empty]**ます。

   ![](assets/wkf_segment_email_not_empty.png)

1. 2つ目のフィルター条件を追加し **[!UICONTROL Mobile]**、演算子を選択しま**[!UICONTROL Is empty]**&#x200B;す。

   ![](assets/wkf_segment_mobile_empty.png)

   電子メールが定義されているが、携帯電話番号が定義されていないクエリからのプロファイルは、すべてこの移行に含まれます。

1. ワークフローをより明確にするために、移行ラベルを編集できます。 変更を確認します。

   ![](assets/wkf_segment_transition_label.png)

最初の移行が設定されます。 2番目の移行(SMS)を設定するには：

1. 新しいトランジシ **[!UICONTROL Add an element]**ョンを追加するには、ボタンをクリックします。
1. 携帯電話番号が入力されたすべてのプロファイルを取得できる条件を定義します。 これを行うには、論理演算子を使用してフィー **[!UICONTROL Mobile]**ルドにルールを作**[!UICONTROL Is not empty]** 成します。

   ![](assets/wkf_segment_mobile_not_empty.png)

   携帯電話番号が定義されているクエリからのプロファイルは、すべてこの移行に含まれます。

1. トランジションのラベルを編集できます。 変更を確認します。

2つ目の移行も設定されました。

![](assets/wkf_segment_transitions.png)

セグメント化アクティビティを作成する詳細な手順については、「セグメント化 [](../../automating/using/segmentation.md) 」の節を参照してください。

## 配信の作成 {#creating-deliveries}

既に2つのトランジションが作成されているので、セグメント化アクティビティのアウトバウンドトランジションに2種類の配信を追加する必要があります。とと **[!UICONTROL Email delivery]**を指定し**[!UICONTROL SMS delivery]**&#x200B;ます。

Adobe Campaignでは、ワークフローに配信を追加できます。 これを行うには、ワークフローのアクティビティパレ **[!UICONTROL Channels]**ットのカテゴリから配信を選択します。

![](assets/wkf_segment_deliveries1.png)

電子メール配信を作成するには：

1. 最初のセグメントの後ろにドラ **[!UICONTROL Email delivery]**ッグ&amp;ドロップします。
1. アクティビティをダブルクリックして編集します。
1. 選択 **[!UICONTROL Simple email]**.
1. を選択し、 **[!UICONTROL Add an outbound transition with the population]**をクリックしま**[!UICONTROL Next]**&#x200B;す。

   ![](assets/wkf_segment_deliveries2.png)

   アウトバウンド移行では、訪問者と追跡ログを回復できます。 例えば、これを使用して、最初のメールをクリックしなかったユーザーに2番目のメールを送信できます。

1. 電子メールテンプレートを選択し、をクリックしま **[!UICONTROL Next]**す。
1. 電子メールのプロパティを入力し、をクリックしま **[!UICONTROL Next]**す。
1. 電子メールのレイアウトを作成する場合は、を選択しま **[!UICONTROL Use the Email Designer]**す。
1. コンテンツを編集して保存します。
1. メッセージダ **[!UICONTROL Schedule]**ッシュボードのセクションで、[!UICONTROL要求確認]**&#x200B;オプションの選択を解除します&#x200B;**。

電子メールアクティビティを作成する詳細な手順は、「電子メール配信」セクション [に示され](../../automating/using/email-delivery.md) ます。

SMS配信を作成するには：

1. 他のセグメントの後ろにドラッ **[!UICONTROL SMS delivery]**グ&amp;ドロップします。
1. アクティビティをダブルクリックして編集します。
1. を選択し、 **[!UICONTROL SMS]**をクリックしま**[!UICONTROL Next]**&#x200B;す。
1. SMSテンプレートを選択し、をクリックしま **[!UICONTROL Next]**す。
1. SMSプロパティを入力し、をクリックしま **[!UICONTROL Next]**す。
1. コンテンツを編集して保存します。

SMSアクティビティを構築する詳細な手順は、「 [SMS配信](../../automating/using/sms-delivery.md) 」セクションに示します。

配信が作成および編集されると、ワークフローを開始する準備が整います。

![](assets/wkf_segment_deliveries.png)

## ワークフローの実行 {#running-the-workflow}

ワークフローが開始されると、Queryアクティビティの対象となる訪問者がセグメント化され、電子メールまたはSMS配信を受け取ります。

To execute your workflow, click the **[!UICONTROL Start]**button from the action bar.

You can access your deliveries from the **[!UICONTROL Marketing plans]**>**[!UICONTROL Marketing activities]** advanced menu via the Adobe Campaign logo. Click the delivery then the **[!UICONTROL Reports]**button to access the[delivery reports](../../reporting/using/about-dynamic-reports.md#accessing-dynamic-reports), such as the delivery summary, the open rate or the email rendering according to the recipients&#39; message inbox.
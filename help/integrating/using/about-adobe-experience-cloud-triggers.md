---
title: Adobe Experience Cloud トリガーについて
description: Adobe Analytics を使用して特定の顧客行動を追跡することで、Adobe Campaign で顧客にパーソナライズされた E メールを送信できるようになりました。
page-status-flag: never-activated
uuid: 0aa4bd6e-1bb5-4d0b-913b-eca93f050acd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: e526b205-2d01-4a8b-9685-ba1d9a1f459f
context-tags: trigger,overview;trigger,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---


# Adobe Experience Cloud トリガーについて{#about-adobe-experience-cloud-triggers}

Experience Cloud Activation コアサービスである **[!UICONTROL Triggers]** と Adobe Campaign を統合すると、Web サイト上で Adobe Analytics によってトラッキングされている特定の動作に対する反応としてパーソナライズされた E メールを送信できます（15 分以内）。

Adobe Experience Cloud では、様々なトリガー、つまり、監視したい顧客行動（Web サイトで訪問を放棄したすべての顧客、Web サイトで検索をおこなったが購入には至らなかった顧客、セッション期限が切れた顧客など）を定義します。トリガーを作成する場合は、トリガーの条件と、イベントで Adobe Campaign に送信される（アップロードされる）データを定義します。

Adobe Campaign では、以前に作成したトリガーを選択し、データマートのデータを使用してイベントデータのエンリッチメントをおこない、そのトリガーにリンクされたトランザクションメッセージテンプレートを定義します。例えば、ある顧客が Web サイトでの訪問を放棄した場合、イベントが Adobe Campaign に送信され、15 分以内にクライアントに送信されるリマーケティング E メールを介してこのイベントを活用できます。

次の図は、この統合の仕組みについて詳しく説明しています。

![](assets/triggers_diagram.png)

**関連トピック：**

* トリガーの様々なタイプについて詳しくは、[Adobe Experience Cloud ドキュメント](https://docs.adobe.com/content/help/ja-JP/core-services/interface/activation/triggers.html)を参照してください。
* [サイトアクティビティに基づくリマーケティングメッセージのトリガー](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two)に関するビデオを参照してください。
* 2 つの[放棄トリガーの使用例](../../integrating/using/abandonment-triggers-use-cases.md)を参照してください。

## トリガーのユーザープロセス {#triggers-user-process}

>[!CAUTION]
>
>メインユーザー手順を実行する前に、機能を設定する必要があります。詳しくは、[機能のアクティベーション](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)、[ソリューションおよびサービスの設定](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services)、[Campaign でのマッピングされたトリガーの作成](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)を参照してください。

Adobe Campaign でのユーザープロセスの主な手順は次のとおりです。

1. 既存の Adobe Experience Cloud トリガーにリンクしたトリガーイベントを作成します。
1. トリガーイベントを公開します。
1. トランザクションメッセージテンプレートのコンテンツを定義します。
1. テンプレートをテストします（テストプロファイルを作成し、配達確認を送信します）。
1. トランザクションメッセージテンプレートを公開します。

完全な使用例については、[この節](../../integrating/using/abandonment-triggers-use-cases.md)で説明します。

## 重要な注意事項 {#important-notes}

以下に、トリガーと Campaign の統合を使用する前に考慮すべき重要な注意事項を示します。

* トリガーに対するプッシュ通知はサポートされていません。E メールと SMS のみがサポートされます。
* E メール ID、ページ名など、Analytics で取り込んだメタデータを使用してトリガーをエンリッチメントできます。
* トリガーを Campaign Standard に格納されたプロファイルに紐付けし、プロファイルのフィールドを使用してメッセージをパーソナライズできます。
* 受信したトリガーは処理および紐付けされて、送信されます。この処理には、受信するトリガーの量とテンプレートで使用されるパーソナライゼーションフィールドの数に応じて、約 5～15 分かかります。

>[!NOTE]
>
>ベストプラクティスと技術上の制約について詳しくは、[トリガーのベストプラクティスと制約](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations)を参照してください。


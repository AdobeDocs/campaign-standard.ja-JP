---
title: 統合アプリケーションワークフロー
description: Campaign と Dynamics の統合ワークフロー
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 51f07f08-5d57-4c4c-aff2-d03e5956ec6f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 1%

---

# Campaign - Microsoft Dynamics 365 統合ワークフロー

**[!UICONTROL Workflows]** のページには、テクニカルワークフローとそのステータスが一覧表示されます。

統合アプリケーションには、次の 3 つのワークフローがあります。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 から Campaign へ**
* Microsoft Dynamics 365 からAdobe Campaignへの *連絡先* の送信
* *カスタムエンティティ*:Microsoft Dynamics 365 からAdobe Campaignにカスタムテーブルを取り込みます。 [詳細情報](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* これは、**入口** とも呼ばれます（Microsoft Dynamics 365 からAdobe Campaignへのデータの入口を指します）

**Campaign からMicrosoft Dynamics 365 へ**
* Adobe Campaign Standardからのメールマーケティングイベントは Dynamics 365 に送信されます（メール送信、開封、クリック、バウンス）。 [詳細情報](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* これは、**エグレス** とも呼ばれます（Adobe CampaignからMicrosoft Dynamics 365 へのデータのエグレスを指します）

**オプトイン/オプトアウト**

オプトアウトステータス（例：^ブロックリスト）は、Microsoft Dynamics 365 からAdobe Campaignへ、またはAdobe CampaignからMicrosoft Dynamics 365 へ同期させることができます。 データは、双方向に同期することもできます（つまり、双方向のデータフロー）。 [詳細情報](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。

>[!IMPORTANT]
>
>変更内容をAdobe Campaign StandardまたはMicrosoft Dynamics 365 に公開する前に、**Microsoft Dynamics 365 から Campaign** へのワークフローを停止することを強くお勧めします。 これらの変更には、統合で現在使用されているリソース/エンティティ（およびその関連フィールド）、リンク、識別子列などの更新が含まれます。 そうしないと、データが失われたり、ワークフローが予期せず停止したりする可能性があります。

## ワークフローバックログ

この統合アプリケーションは、最初にデータを読み取り、次に宛先にデータを書き込みます。 **[!UICONTROL Backlog]** 列は、キューに入れられ、書き込みを待っているレコードの数を示します。 この値は、処理するデータが大量にある場合（例えば、統合を初めて実行する場合や、データを再生する場合など）に増加することが予想されます。

>[!NOTE]
>Microsoft Dynamics 365 や Campaign レコードが更新されていない場合は、まず、書き込み先に書き込まれるのを待っているレコードが多数あるかどうかを確認する必要があります。
>

## ワークフローステータス {#workflow-status}

**[!UICONTROL Status]** の列は、ワークフローに関連付けられているバックグラウンドプロセスの状態を示します。 次のような値を選択できます。

* **実行中**: プロセスは現在実行中です。データを同期する必要があります。
* **停止**: プロセスは現在実行されていないので、データが同期される必要はありません。
* **開始**：ワークフロープロセスの開始をリクエストしました。 アプリケーションは、このワークフローに関連付けられたデータの同期をまだ開始していませんが、数分後に開始されることが予想されます（その後、**実行中** のステータスが表示されます）
* **失敗**: ワークフロープロセスは実行中ですが、エラーが発生したため、回復できませんでした。

## 使用可能なアクション

可能なアクションを以下に示します。

* **編集**：鉛筆アイコンをクリックすると、ワークフローを更新できる別のページに送信されます。 加えた変更は、ワークフローを停止して再起動するまで有効になりません。

* **開始**：開始ボタンは、停止したワークフローの開始をリクエストします。 このボタンは、ワークフローに関連付けられているプロセスが現在停止されている場合にのみ表示されます。 プロセスは、最初に「開始中」に変わり、次に「実行中」に変わります。 ワークフローに関連付けられているデータは、ワークフローが「実行中」の状態になるまで同期を開始しません。

  「開始」ボタンは切り替えボタンです。 ワークフロープロセスが既に開始されている場合、ボタンは **停止** ボタンに変わります。

* **停止**:**停止** ボタンは、実行中のワークフローの停止をリクエストします。 このボタンは、ワークフローに関連付けられたプロセスが現在実行中の場合にのみ表示されます。

ワークフローを編集する場合、その更新は、ワークフローを停止して「**開始**」ボタンをクリックするまで、実行中のプロセスのルールにすぐには組み込まれません。 その後、更新内容は実行中のプロセスに組み込まれます（プロセスが **実行中** 状態に戻ると）。

**a）ワークフローが更新されたが、（b）このワークフローの停止/開始を行っていない場合に通知する警告の表示が** 停止」ボタンに追加されます。

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)

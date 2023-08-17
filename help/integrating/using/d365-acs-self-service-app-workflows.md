---
title: 統合アプリケーションのワークフロー
description: Campaign と Dynamics の統合ワークフロー
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 51f07f08-5d57-4c4c-aff2-d03e5956ec6f
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---

# Campaign - Microsoft Dynamics 365 統合ワークフロー

The **[!UICONTROL Workflows]** ページには、テクニカルワークフローとそのステータスが一覧表示されます。

統合アプリケーションには、次の 3 つのワークフローが用意されています。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 から Campaign へ**
* 送信 *連絡先* Microsoft Dynamics 365 からAdobe Campaignへ
* *カスタムエンティティ*：カスタムテーブルをMicrosoft Dynamics 365 からAdobe Campaignに取り込みます。 [詳細情報](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* これは、 **入口** (Microsoft Dynamics 365 からAdobe Campaignへのデータの入り込みを参照 )

**Campaign からMicrosoft Dynamics 365**
* Adobe Campaign Standardの電子メールマーケティングイベントが Dynamics 365（電子メール送信、開く、クリック、バウンス）に送信されます。 [詳細情報](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* これは、 **エグレス** (Adobe CampaignからMicrosoft Dynamics 365 へのデータの出力を参照 )

**オプトイン/オプトアウト**

オプトアウトステータス（例：）は、Microsoft ブロックリストに加える Dynamics 365 からAdobe Campaignに、またはAdobe CampaignからMicrosoft Dynamics 365 に同期できます。 データは双方向に同期する（つまり、両方向にデータフローを行う）ことでも可能です。 [詳細情報](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)

>[!IMPORTANT]
>
>を停止することを強くお勧めします。 **Microsoft Dynamics 365 から Campaign へ** ワークフローを使用して、変更をAdobe Campaign StandardまたはMicrosoft Dynamics 365 に公開する必要があります。 これらの変更には、リソース/エンティティ（および関連するフィールド）、リンク、識別子列など、統合で現在使用中の更新が含まれます。 そうしないと、データが失われたり、ワークフローが予期せず停止したりする可能性があります。

## ワークフローのバックログ

この統合アプリケーションは、最初にデータを読み込み、次に宛先にデータを書き込みます。 The **[!UICONTROL Backlog]** 列は、キューに入れられ、書き込みを待機しているレコードの数を示します。 処理するデータ量が多い場合（例えば、初めて統合を実行した場合、データを再生する場合など）、この値は増加すると予想されます。

>[!NOTE]
>Microsoft Dynamics 365 または Campaign のレコードが更新されていない場合は、まず、宛先に書き込まれるのを待っているレコードが多数あるかどうかを確認する必要があります。
>

## ワークフローステータス {#workflow-status}

The **[!UICONTROL Status]** 列は、ワークフローに関連付けられたバックグラウンドプロセスの状態を示します。 次のような値を選択できます。

* **実行中**：プロセスは現在実行中で、データを同期する必要があります。
* **停止済み**：プロセスは現在実行中ではないので、データは同期されないはずです。
* **開始中**：ワークフロープロセスの開始をリクエストしました。 アプリケーションはまだこのワークフローに関連付けられたデータの同期を開始していませんが、数分後に同期が開始されると想定できます ( その後、のステータスが表示される場合は **実行中**)
* **失敗**：ワークフロープロセスは実行中でしたが、エラーが発生し、これらから回復できませんでした。

## 使用可能なアクション

実行可能なアクションを次に示します。

* **編集**：鉛筆アイコンをクリックすると、別のページに送信され、ワークフローを更新できます。 ワークフローを停止してから再起動するまで、加えた変更は有効になりません。

* **開始**:「開始」ボタンは、停止したワークフローを開始するようにリクエストします。 このボタンは、ワークフローに関連付けられたプロセスが現在停止している場合にのみ表示されます。 プロセスは最初に「STARTING」に変わり、次に「RUNNING」に変わります。 ワークフローに関連付けられたデータは、ワークフローが「実行中」の状態になるまで同期を開始しません。

  「開始」ボタンは切り替えです。 ワークフロープロセスが既に開始されている場合、ボタンは **停止** 」ボタンをクリックします。

* **停止**: A **停止** ボタンは、実行中のワークフローを停止するようリクエストします。 このボタンは、ワークフローに関連付けられたプロセスが現在実行中の場合にのみ表示されます。

ワークフローを編集する際、ワークフローを停止し、 **開始** 」ボタンをクリックします。 その後、更新が実行中のプロセスに組み込まれます ( プロセスが **実行中** 州 ) です。

警告メッセージが **停止** ボタンをクリックして、(a) ワークフローを更新したが、(b) このワークフローの停止/開始を実行していないことを通知します。

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)

---
title: トリガーのテスト
description: null
page-status-flag: 非活性化の
uuid: b3a667d-e843-4ad6-817e-d91542b5f2e2
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: キャンペーンとトリガーの連携
discoiquuid: f67e69f2-09fb-4f33-b2c3-c67a060743e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# トリガーのテスト{#testing-your-triggers}

以下のトラブルシューティングのヒントは、Adobe CampaignでTriggersを使用する場合に発生する最も一般的な問題の解決に役立ちます。

**機能は有効になっていますか。**

Triggers - Campaignの統合がアクティブ化されているかどうかを確認するには、左上隅にあるAdobe Campaignロゴをクリックし、/を選択 **[!UICONTROL Marketing plans]** します **[!UICONTROL Transactional messages]**。 アイテムが表示さ **[!UICONTROL Experience Cloud Triggers]** れます。

見えたら、次の手順に進みます。

そうでない場合は、アドビのアカウント担当者またはプロフェッショナルサービスパートナーにお問い合わせください。 機能のア [クティブ化を参照してください](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)。

**トリガーの作成を試みる**

トリガーを作成するには、「Campaignで [のマッピングされたトリガーの作成](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) 」で説明されている手順に従います。

トリガーが作成された場合は、次の手順に進みます。 そうでない場合は、トリガのエンドポイント接続が失敗したことを意味します。 TriggersがExperience Cloud（Activationサービス）でプロビジョニングされているかどうかを確認します。 アドビのアカウント担当者またはプロフェッショナルサービスパートナーに問い合わせてください。 次の情報が必要です。

* Marketing cloud会社名
* IMS ORG ID
* Analyticsログイン会社名（Marketing cloud会社名と同じ名前を使用できます）

**トリガーの公開を試みる**

「Campaignでのマッピングされたトリガ [ーの作成」で説明されている手順に従って](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) 、トリガーを公開します。

パブリケーションが成功した場合は、次のステップに進みます。 インスタンスが存在しない場合は、アドビに連絡してインスタンスを再起動し、もう一度お試しください。

**Webサイトからのトリガーの生成**

トランザクションメッセージテンプ [レートを編集して発行するには](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) 、「トランザクションメッセージテンプレートの編集」で説明されている手順に従います。 次に、Webサイトからのトリガーの生成をテストします。

Analyticsがトリガーを受け取った場合は、次の手順に進みます。 そうでない場合は、次の項目を確認します。

* Analyticsでトリガーが有効になっている
* MCIDおよびAnalyticsを使用するWebサイトがDTMで有効になっている
* トリガーの作成時に正しいAnalyticsレポートスイートが使用される

**トリガーはキャンペーンで受け取られますか。**

トリガーがない場合は、トリガーがパイプラインから受け取られたかどうかを確認します。

そうでない場合は、アドビに連絡して、パイプラインエンドポイントの設定を確認してください。

該当する場合は、次のガイドラインに従います。

* キャンペーンデータソースで調整IDタイプを確認します。
* 顧客IDデータソースは顧客属性を使用して作成されます。
* データソースIDを確認します。
* データソースの設定後にCampaignインスタンスを再起動するようアドビに依頼します。
* トリガーレポートでトリガーの解析の問題を確認します。

**トリガーは保留中の状態ですか？**

そうでない場合は、次の手順に進みます。 該当する場合は、次のガイドラインに従います。

* トランザクションテンプレートが発行されていることを確認します。
* PropensityScoreしきい値がキャンペーンに対して有効になっている場合は、パイプラインからトリガーの傾向スコアを確認します。
* プロファイルがブラックリストに記載されていないことを確認します。
* タイポロジルールの適用を確認します。
* トランザクションメッセージのログを確認します。

**メッセージは有効ですか？**

メッセージが無効な場合は、次の項目を確認します。

* 無効とマークされたトリガーリッチメントパーソナライゼーションフィールドについては、関連するeventCusResourceコレクションからトランザクションテンプレートを検証します。
* メッセージ形式の検証


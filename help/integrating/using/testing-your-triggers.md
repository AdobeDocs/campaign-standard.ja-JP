---
title: トリガーのテスト
seo-title: トリガーのテスト
description: トリガーのテスト
seo-description: null
page-status-flag: 常にアクティブ化されていない
uuid: b3a6667d- e843-4ad6-817e- d91542b5f2e2
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- trigger
discoiquuid: f67e69f2-09fb-4f33- b2c3- c67a060743e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Testing your triggers{#testing-your-triggers}

次のトラブルシューティングのヒントは、Adobe CampaignでTriggersを使用する際に発生する可能性のある最も一般的な問題を解決するのに役立ちます。

**機能がアクティブ化されているか。**

To check if the Triggers - Campaign integration is activated, click the Adobe Campaign logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]**. **[!UICONTROL Experience Cloud Triggers]** 項目が表示されます。

表示されている場合は、次の手順に進みます。

サポートされていない場合は、アドビのアカウント担当者またはプロフェッショナルサービスパートナーにお問い合わせください。See [Activating the functionality](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**トリガーの作成**

Follow the steps described in [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) to create a trigger.

トリガーが作成された場合は、次のステップに移動します。そうでないと、トリガーのエンドポイント接続が失敗します。TriggersがExperience Cloud（Activationサービス）でプロビジョニングされているかどうかを確認します。サポートされていない場合は、アドビのアカウント担当者またはプロフェッショナルサービスパートナーにお問い合わせください。次の情報が必要です。

* Marketing Cloud会社名
* IMS ORG ID
* Analyticsログイン会社名（Marketing Cloud会社名と同じにすることができます）

**トリガーの公開を試みる**

Follow the steps described in [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) to publish the trigger.

パブリケーションが成功した場合は、次のステップに進みます。そうでない場合は、アドビに連絡してインスタンスを再起動し、再試行してください。

**Webサイトからのトリガーの生成**

Follow the steps described in [Editing the transactional message template](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) to edit and publish the transactional template. その後、Webサイトからトリガーの生成をテストします。

トリガーがAnalyticsによって受信された場合は、次の手順に進みます。そうでない場合は、次の項目を確認してください。

* トリガーがAnalyticsで有効になっている
* WebサイトがDTMで使用され、AnalyticsがDTMで有効になる
* トリガーの作成時に、正しいAnalyticsレポートスイートが使用される

**トリガーはキャンペーンによって受信されますか。**

そうでない場合は、トリガーがパイプラインから受信されたかどうかを確認します。

サポートされていない場合は、アドビに連絡してパイプラインエンドポイントの設定を確認してください。

その場合は、次のガイドラインに従います。

* キャンペーンデータソースで紐付けIDタイプを確認します。
* CustomerIDデータソースは、顧客属性を介して作成されます。
* データソースIDを確認します。
* Adobeにデータソース設定の後にCampaignインスタンスを再起動するように依頼します。
* トリガーレポートの解析の問題をトリガーします。

**トリガーは保留状態ですか。**

そうでない場合は、次のステップに進みます。その場合は、次のガイドラインに従います。

* トランザクションテンプレートが発行されていることを確認します。
* CampaignScoreのしきい値がキャンペーンで有効になっている場合、パイプラインからトリガーの傾向スコアを確認します。
* プロファイルがブラックリストに記載されていないことを確認します。
* タイポロジルールの適用を確認します。
* トランザクションメッセージのログを確認します。

**メッセージは有効ですか?**

メッセージが有効でない場合は、次の項目を確認してください。

* 無効とマークされた無効なパーソナライゼーションパーソナライゼーションフィールドの場合、関連付けられたEventCusResourceコレクションからトランザクションテンプレートを検証します。
* メッセージの形式の検証


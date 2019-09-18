---
title: メッセージダッシュボード
seo-title: メッセージダッシュボード
description: メッセージダッシュボード
seo-description: アクションバーやさまざまな機能ブロックなど、メッセージダッシュボードの構成を確認します。
page-status-flag: 未活性化の
uuid: 9bb4ee8-2cf6-43ce-94a4-367f4e469713
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: チャンネル
content-type: 参照
topic-tags: 通信チャネルについて
discoiquuid: 90a78742-697f-46da-8c54-108048e57b67
context-tags: 配送，メイン
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: aa52fcca887c9423476a1bc0160d340f255b9ac8

---


# メッセージダッシュボード{#message-dashboard}

メッセージダッシュボードは、異なるアイコン（アクションバーに再グループ化）と、メッセージのパラメータを設定して送信できるさまざまな機能ブロックで構成されたワークスペースです。 これらの要素を以下に示す。

![](assets/delivery_dashboard_2.png)

## 灰色のバー {#gray-bar}

灰色のバーは、メッセージにリンクされたさまざまなアイコンを再グループ化します。

* **[!UICONTROL Summary]**:メッセージに関する主な情報を表示/非表示にします。
* **[!UICONTROL Edit properties]**:メッセージの詳細パラメータを編 [集できます](../../administration/using/configuring-email-channel.md#list-of-email-properties)。
* **[!UICONTROL Reports]**:メッセージに関するレポートにアクセスできます。

**関連トピック：**

* [チャネルの設定](../../administration/using/about-channel-configuration.md)
* [レポートへのアクセス](../../reporting/using/about-dynamic-reports.md)

## アクションバー {#action-bar}

アクションバーには、メッセージを操作するためのさまざまなアイコンがあります。

![](assets/delivery_dashboard_4.png)

設定済みのパラメータと実行中の進行状況に応じて、特定のアイコンが使用できない場合があります。

* **[!UICONTROL Show proofs]**:送信された校正の一覧が存在する場合は、その一覧を表示/非表示にします。 このボタンは、校正を行った後にのみ有効になります。

   校正の詳細については、「テストプロファ [イルを管理し、校正を送信する」を参照してくださ](../../sending/using/managing-test-profiles-and-sending-proofs.md)い。

* **[!UICONTROL Send a test]**:使用する承認モードを選択できます。メー **[!UICONTROL Email rendering]**&#x200B;ルの **[!UICONTROL Proof]** 場合は、または両方。 テストプロファイルの詳細については、「校正の送信」を [参照してください](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs)。

   このボタンは、テストプロファイルを設定した後にのみ有効になります。

   >[!NOTE]
   >
   >SMSメッセージの場合は、他に選択肢はありません。自動的に **[!UICONTROL Proof]**。

* **[!UICONTROL Prepare send]**:送信の準備を開始します。 ブロック **[!UICONTROL Deployment]** が表示され、準備の結果が表示されます。 このボタンは、ターゲットが入力された後にのみ表示されます。 対応するボタンを使用して、いつでも準備を停止できます。

   メッセージの準備の詳細については、 [送信の準備をします](../../sending/using/preparing-the-send.md)。

* **[!UICONTROL Confirm send]**:メッセージの送信を確認します。 送信統計がブロックに表示さ **[!UICONTROL Deployment]** れます。 このボタンは、送信の準備が完了した後にのみ表示されます。 [送信の停止]ボタンと[送信の停止]ボタンを使用して、いつでも送信を停 **止または一時** 停止で **[!UICONTROL Pause]** きます。

   送信の確認の詳細については、「メッセージの送信」を参 [照してくださ](../../sending/using/confirming-the-send.md)い。

## ブロック {#blocks}

メイン画面は異なるブロックで構成されています。 ブロック内をクリックして、対応するパラメータ画面にアクセスします。

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**:メッセージの準備または送信の進行状況を追跡できます。 このブロックの右下にあるボタンをクリックして、送信ログと分析ログにアクセスします。 このブロックは、送信が準備された後にのみ表示されます。 この件に関する詳細は、こちらをご覧ください。 送信の確 [認を参照](../../sending/using/confirming-the-send.md)。
* **[!UICONTROL Audience]**:メッセージの主なターゲットとテストプロファイルを設定できます。 対象ユーザー [の作成を参照](../../audiences/using/creating-audiences.md)。
* **[!UICONTROL Schedule]**:メッセージの送信日を指定できます。 「スケジュー [リング](../../sending/using/about-scheduling-messages.md)」を参照。
* **[!UICONTROL Content]**:メッセージの内容を定義し、プレビューできます。 メッセージ [を送信するには、「主な手順」を参照してください](../../channels/using/key-steps-to-send-a-message.md)。


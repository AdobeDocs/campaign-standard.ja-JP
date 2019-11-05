---
title: メッセージダッシュボード
description: アクションバーや様々な機能ブロックなど、メッセージダッシュボードの構成要素を確認します。
page-status-flag: 非活性化の
uuid: 9bb44ee8-2cf6-43ce-94a4-367f4e469713
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: 通信路
discoiquuid: 90a78742-697f-46da-8c54-108048e57b67
context-tags: 配信，メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# メッセージダッシュボード{#message-dashboard}

メッセージダッシュボードは、様々なアイコン（アクションバーに再グループ化）で構成されたワークスペースで、メッセージのパラメーターを確立して送信できる様々な機能ブロック)を備えています。 以下、これらの要素を紹介する。

![](assets/delivery_dashboard_2.png)

## グレーバー {#gray-bar}

グレーのバーは、メッセージにリンクされた様々なアイコンを再グループ化します。

* **[!UICONTROL Summary]**:メッセージに関するメイン情報の表示/非表示を切り替えます。
* **[!UICONTROL Edit properties]**:メッセージの詳細パラメータを編 [集できます](../../administration/using/configuring-email-channel.md#list-of-email-properties)。
* **[!UICONTROL Reports]**:メッセージに関連するレポートにアクセスできます。

**関連トピック：**

* [チャネルの設定](../../administration/using/about-channel-configuration.md)
* [レポートへのアクセス](../../reporting/using/about-dynamic-reports.md)

## アクションバー {#action-bar}

アクションバーには、メッセージを操作できる様々なアイコンがあります。

![](assets/delivery_dashboard_4.png)

設定したパラメーターと実行された進行状況に応じて、特定のアイコンが使用できない場合があります。

* **[!UICONTROL Show proofs]**:送信された校正が存在する場合は、その一覧を表示/非表示にします。 このボタンは、校正を送信した後にのみ有効になります。

   校正について詳しくは、「テストプロフ [ァイルの管理と校正の送信」を参照してください](../../sending/using/managing-test-profiles-and-sending-proofs.md)。

* **[!UICONTROL Send a test]**:使用する承認モードを選択できます。電子メ **[!UICONTROL Email rendering]**&#x200B;ールの場 **[!UICONTROL Proof]** 合は、またはその両方を指定します。 テストプロファイルについて詳しくは、「校正の送信」を [参照してくださ](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs)い。

   このボタンは、テストプロファイルを確立した後にのみ有効になります。

   >[!NOTE]
   >
   >SMSメッセージの場合は、他に選択肢はありません。自動的に実行されま **[!UICONTROL Proof]**&#x200B;す。

* **[!UICONTROL Prepare send]**:送信の準備を開始します。 ブロッ **[!UICONTROL Deployment]** クが表示され、準備の結果が表示されます。 このボタンは、ターゲットが入力された後にのみ表示されます。 対応するボタンを使用して、いつでも準備を停止できます。

   メッセージの準備について詳しくは、 [送信の準備を参照](../../sending/using/preparing-the-send.md)。

* **[!UICONTROL Confirm send]**:メッセージの送信を確認します。 送信統計がブロックに表示され **[!UICONTROL Deployment]** ます。 このボタンは、送信の準備が完了した後にのみ表示されます。 送信を停止ボタンと停止ボタンを使用して、いつでも送信を停 **止または一時停止で** き **[!UICONTROL Pause]** ます。

   送信の確認について詳しくは、「メッセージの送信」を [参照してくださ](../../sending/using/confirming-the-send.md)い。

## ブロック {#blocks}

メイン画面は異なるブロックで構成されています。 ブロック内をクリックして、対応するパラメータ画面にアクセスします。

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**:メッセージの準備または送信の進行状況を追跡できます。 このブロックの右下にあるボタンをクリックして、送信および分析ログにアクセスします。 このブロックは、送信の準備が完了した後にのみ表示されます。 詳しくは、 送信の確 [認を参照してください](../../sending/using/confirming-the-send.md)。
* **[!UICONTROL Audience]**:メッセージのメインターゲットとテストプロファイルを確立できます。 オーディエ [ンスの作成を参照してくださ](../../audiences/using/creating-audiences.md)い。
* **[!UICONTROL Schedule]**:メッセージの送信日を指定できます。 スケジュール [を参照](../../sending/using/about-scheduling-messages.md)。
* **[!UICONTROL Content]**:メッセージの内容を定義し、プレビューできます。 See [Key steps to send a message](../../channels/using/key-steps-to-send-a-message.md).


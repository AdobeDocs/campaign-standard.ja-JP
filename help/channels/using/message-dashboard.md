---
title: メッセージダッシュボード
description: アクションバーや様々な機能ブロックなど、メッセージダッシュボードの構成要素を確認します。
page-status-flag: never-activated
uuid: 9bb44ee8-2cf6-43ce-94a4-367f4e469713
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: about-communication-channels
discoiquuid: 90a78742-697f-46da-8c54-108048e57b67
context-tags: delivery,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0fe16001c57d3ccc2e7d42b94bc14e73d8b47ddb

---


# メッセージダッシュボード{#message-dashboard}

メッセージダッシュボードは、様々なアイコン（アクションバーに再グループ化）で構成されたワークスペースで、メッセージのパラメーターを確立して送信できる様々な機能ブロック)を備えています。 以下、これらの要素を紹介する。

![](assets/delivery_dashboard_2.png)

## グレーバー {#gray-bar}

グレーのバーは、メッセージにリンクされた様々なアイコンを再グループ化します。

* **[!UICONTROL Summary]**:メッセージに関するメイン情報の表示/非表示を切り替えます。
* **[!UICONTROL Edit properties]**:メッセージの詳細パラメータを編[集できます](../../administration/using/configuring-email-channel.md#list-of-email-properties)。
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

* **[!UICONTROL Send a test]**:使用する承認モードを選択できます。電子メ**[!UICONTROL Email rendering]**&#x200B;ールの場 **[!UICONTROL Proof]**合は、またはその両方を指定します。 テストプロファイルについて詳しくは、「校正の送信」を[参照してくださ](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs)い。

   このボタンは、テストプロファイルを確立した後にのみ有効になります。

   >[!NOTE]
   >
   >SMSメッセージの場合は、他に選択肢はありません。自動的に実行されま **[!UICONTROL Proof]**す。

* **[!UICONTROL Prepare send]**:送信の準備を開始します。 ブロッ**[!UICONTROL Deployment]** クが表示され、準備の結果が表示されます。 このボタンは、ターゲットが入力された後にのみ表示されます。 対応するボタンを使用して、いつでも準備を停止できます。

   メッセージの準備について詳しくは、 [送信の準備を参照](../../sending/using/preparing-the-send.md)。

* **[!UICONTROL Confirm send]**:メッセージの送信を確認します。 送信統計がブロックに表示され**[!UICONTROL Deployment]** ます。 このボタンは、送信の準備が完了した後にのみ表示されます。 送信を停止ボタンと停止ボタンを使用して、いつでも送信を停 **止または一時停止で** き **[!UICONTROL Pause]**ます。

   送信の確認について詳しくは、「メッセージの送信」を [参照してくださ](../../sending/using/confirming-the-send.md)い。

## ブロック {#blocks}

メイン画面は異なるブロックで構成されています。 ブロック内をクリックして、対応するパラメータ画面にアクセスします。

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**:メッセージの準備または送信の進行状況を追跡できます。 このブロックの右下にあるボタンをクリックして、送信および分析ログにアクセスします。 このブロックは、送信の準備が完了した後にのみ表示されます。 詳しくは、 送信の確[認を参照してください](../../sending/using/confirming-the-send.md)。
* **[!UICONTROL Audience]**:メッセージのメインターゲットとテストプロファイルを確立できます。 オーディエ[ンスの作成を参照してくださ](../../audiences/using/creating-audiences.md)い。
* **[!UICONTROL Schedule]**:メッセージの送信日を指定できます。 スケジュール[を参照](../../sending/using/about-scheduling-messages.md)。
* **[!UICONTROL Content]**:メッセージの内容を定義し、プレビューできます。 See[Key steps to send a message](../../channels/using/key-steps-to-send-a-message.md).

## 警告 {#warnings}

場合によっては、メッセージダッシュボードの上に黄色のバナーで警告が表示されることがあります。

![](assets/delivery_dashboard_warnings.png)

表示できるメッセージの一覧を次に示します。

* *「SMTP test mode option is enabled for this email:メッセージは送信されません。」*

   For more on this, see [this section](../../administration/using/configuring-email-channel.md#smtp-test-mode).

* *&quot;外部アカウントのルーティングが無効になっています。&quot;*

   For more on this, see [External accounts](../../administration/using/external-accounts.md).

* *&quot;現在のIP親和性は送信プロセスで処理されないため、メッセージを送信できません。&quot;*

   このメッセージが表示される場合は、IP親和性の定義レベルまたは送信プロセスレベルで問題が発生しています。 アドビの管理者に問い合わせてください。

* *「このトランザクションメッセージは、標準搭載のトランザクションメッセージテンプレートです。 変更する場合は、複製してコピーを作成する必要があります。」*

   標準搭載のトランザクションメッセージテンプレートの一部は、ランディングページテンプレートが組み込まれています。 For more on this, see [this section](../../channels/using/landing-page-templates.md).

* *「このメッセージは、技術的なトランザクションメッセージテンプレートです。 変更や公開はできません。」*

   この警告は、編集できない空のトランザクションメッセージテンプレートで表示されます。 トランザクションメッセージについて詳しくは、この節を [参照してくださ](../../channels/using/about-transactional-messaging.md)い。

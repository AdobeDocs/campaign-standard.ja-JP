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
source-git-commit: 9c812b0b622b82ba7aa382f04edb7a2a3f717cd4
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 5%

---


# メッセージダッシュボード{#message-dashboard}

メッセージダッシュボードは、様々なアイコン（アクションバーに再グループ化されたアイコン）と、メッセージのパラメーターを確立して送信できる様々な機能ブロックで構成されたワークスペースです。 以下、これらの要素を紹介する。

![](assets/delivery_dashboard_2.png)

## グレーバー {#gray-bar}

グレーのバーは、メッセージにリンクされた様々なアイコンを再グループ化します。

* **[!UICONTROL Summary]**:メッセージに関するメイン情報を表示/非表示にします。
* **[!UICONTROL Edit properties]**:メッセージの [詳細パラメータを編集できます](../../administration/using/configuring-email-channel.md#list-of-email-properties)。
* **[!UICONTROL Reports]**:メッセージに関するレポートにアクセスできます。

**関連トピック：**

* [チャネルの設定](../../administration/using/about-channel-configuration.md)
* [レポートへのアクセス](../../reporting/using/about-dynamic-reports.md)

## アクションバー {#action-bar}

アクションバーには、メッセージを操作できる様々なアイコンがあります。

![](assets/delivery_dashboard_4.png)

設定したパラメーターと実行された進行状況に応じて、特定のアイコンが使用できない場合があります。

* **[!UICONTROL Show proofs]**:送信された配達確認が存在する場合は、そのリストを表示/非表示にします。 このボタンは、配達確認を送信した後にのみ有効になります。

   配達確認について詳しくは、「配達確認の [送信](../../sending/using/sending-proofs.md)」を参照してください。

* **[!UICONTROL Send a test]**:使用する承認モードを選択できます。 **[!UICONTROL Email rendering]** （電子メールのみ） **[!UICONTROL Proof]** またはその両方。 テストプロファイルについて詳しくは、「配達確認の [送信](../../sending/using/sending-proofs.md)」を参照してください。 このボタンは、テストプロファイルを作成した場合にのみ有効になります。

* **[!UICONTROL Prepare send]**:送信を準備する開始。 ブロックが表示され、準備の結果が表示されます。 **[!UICONTROL Deployment]** このボタンは、ターゲットを入力した場合にのみ表示されます。 対応するボタンを使用すると、いつでも準備を停止できます。 For more on message preparation, refer to [Preparing the send](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**:メッセージの送信を確認します。 送信統計が **[!UICONTROL Deployment]** ブロック内に表示されます。 このボタンは、送信の準備が完了した後にのみ表示されます。 「送信を停止 **」ボタンと「送信を停止** 」 **[!UICONTROL Pause]** ボタンを使用すると、いつでも送信を停止または一時停止できます。 送信の確認について詳しくは、「メッセージの [送信](../../sending/using/confirming-the-send.md)」を参照してください。

## ブロック {#blocks}

メイン画面は異なるブロックで構成されています。 ブロック内をクリックして、対応するパラメータ画面にアクセスします。

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**:メッセージの準備または送信の進行状況を追跡できます。 送信ログと分析ログにアクセスするには、このブロックの右下のセクションにあるボタンをクリックします。 このブロックは、送信の準備が完了した後にのみ表示されます。 詳しくは、 See [Confirming send](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**:メッセージのメインターゲットとテストプロファイルを確立できます。 [オーディエンスの作成](../../audiences/using/creating-audiences.md)を参照してください。
* **[!UICONTROL Schedule]**:メッセージの送信日を指定できます。 「 [スケジュール](../../sending/using/about-scheduling-messages.md)」を参照してください。
* **[!UICONTROL Content]**:メッセージの内容とプレビューを定義できます。 See [Key steps to send a message](../../channels/using/key-steps-to-send-a-message.md).

## 警告 {#warnings}

メッセージダッシュボードの上部に黄色のバナーで警告が表示される場合があります。

![](assets/delivery_dashboard_warnings.png)

次に、表示できるメッセージのリストを示します。

* *「SMTP test modeオプションは、次の電子メールに対して有効です：メッセージは送信されません。」*

   詳しくは、[この節](../../administration/using/configuring-email-channel.md#smtp-test-mode)を参照してください。

* *&quot;ルーティング外部アカウントは無効になっています。&quot;*

   For more on this, see [External accounts](../../administration/using/external-accounts.md).

* *&quot;現在のIPアフィニティは送信プロセスで処理されないため、メッセージを送信できません。&quot;*

   このメッセージが表示される場合は、IPアフィニティ定義レベルまたは送信プロセスレベルで問題が発生しています。 Adobe 管理者にお問い合わせください。

* *「これは既製のトランザクションメッセージテンプレートです 変更したい場合は、重複してコピー作業を行う必要があります。」*

   あらかじめ用意されているこれらのトランザクションメッセージテンプレートの一部は、組み込みのランディングページテンプレートです。 詳しくは、[この節](../../channels/using/landing-page-templates.md)を参照してください。

* *同氏は、「このメッセージはテクニカルなトランザクションメッセージテンプレートだ。 変更や公開はできません。」*

   この警告は、編集できない空のトランザクションメッセージテンプレートで表示されます。 For more on transactional messages, see [this section](../../channels/using/getting-started-with-transactional-msg.md).

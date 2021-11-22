---
title: メッセージダッシュボード
description: アクションバーや様々な機能ブロックなど、メッセージダッシュボードの構成内容を確認します。
audience: channels
content-type: reference
topic-tags: about-communication-channels
context-tags: delivery,main
feature: Overview
role: User
level: Beginner
exl-id: 886aae39-2029-471c-b4d1-c6ca57d0e568
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 5%

---

# メッセージダッシュボード{#message-dashboard}

メッセージダッシュボードは、様々なアイコンで構成され、アクションバーに再グループ化されたワークスペースです。メッセージのパラメーターを設定して送信できる様々な機能ブロックが用意されています。 これらの要素は以下に示します。

![](assets/delivery_dashboard_2.png)

## グレーバー {#gray-bar}

灰色のバーは、メッセージにリンクされた様々なアイコンを再グループ化します。

* **[!UICONTROL Summary]**:メッセージに関するメイン情報を表示/非表示にします。
* **[!UICONTROL Edit properties]**:メッセージの [詳細パラメーター](../../administration/using/configuring-email-channel.md#list-of-email-properties).
* **[!UICONTROL Reports]**:を使用すると、メッセージに関するレポートにアクセスできます。

**関連トピック：**

* [チャネルの設定](../../administration/using/about-channel-configuration.md)
* [レポートへのアクセス](../../reporting/using/about-dynamic-reports.md)

## アクションバー {#action-bar}

アクションバーには、メッセージを操作するための様々なアイコンがあります。

![](assets/delivery_dashboard_4.png)

設定されたパラメーターと実行された進行状況によっては、特定のアイコンを使用できない場合があります。

* **[!UICONTROL Show proofs]**:送信済みの配達確認のリストが存在する場合は、そのリストを表示または非表示にします。 このボタンは、配達確認を送信した後にのみ有効になります。

   配達確認について詳しくは、 [配達確認の送信](../../sending/using/sending-proofs.md).

* **[!UICONTROL Send a test]**:使用する承認モードを選択できます。 **[!UICONTROL Email rendering]** （電子メールのみ）、 **[!UICONTROL Proof]** またはその両方。 テストプロファイルについて詳しくは、 [配達確認の送信](../../sending/using/sending-proofs.md). このボタンは、テストプロファイルを作成した場合にのみ有効になります。

* **[!UICONTROL Prepare send]**:送信の準備を開始します。 この **[!UICONTROL Deployment]** ブロックが表示され、準備の結果が表示されます。 このボタンは、ターゲットを入力した場合にのみ表示されます。 対応するボタンを使用して、いつでも準備を停止できます。 メッセージの準備について詳しくは、 [送信の準備](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**:メッセージの送信を確認します。 送信の統計が **[!UICONTROL Deployment]** ブロック このボタンは、送信の準備が完了した後にのみ表示されます。 送信は、いつでも **送信を停止** および **[!UICONTROL Pause]** ボタン 送信の確認について詳しくは、 [メッセージの送信](../../sending/using/confirming-the-send.md).

## ブロック {#blocks}

メイン画面は異なるブロックで構成されています。 ブロック内をクリックして、対応するパラメータ画面にアクセスします。

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**:では、メッセージの準備または送信の進行状況をトラッキングできます。 このブロックの右下にある「 」ボタンをクリックして、送信ログと分析ログにアクセスします。 このブロックは、送信が準備された場合にのみ表示されます。 詳しくは、こちらを参照してください。 詳しくは、 [送信の確認](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**:では、メッセージのメインターゲットとテストプロファイルを確立できます。 [オーディエンスの作成](../../audiences/using/creating-audiences.md)を参照してください。
* **[!UICONTROL Schedule]**:メッセージを送信する日付を指定できます。 詳しくは、 [スケジュール](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**:では、メッセージの内容を定義してプレビューできます。 詳しくは、 [メッセージを送信するための主な手順](../../channels/using/key-steps-to-send-a-message.md).

## 警告 {#warnings}

場合によっては、メッセージダッシュボードの上に黄色いバナーが表示されることがあります。

![](assets/delivery_dashboard_warnings.png)

表示可能なメッセージのリストを次に示します。

* *「このメールに対して SMTP テストモードオプションが有効になっています：メッセージは送信されません。」*

   詳しくは、[この節](../../administration/using/configuring-email-channel.md#smtp-test-mode)を参照してください。

* *&quot;ルーティング外部アカウントが無効になりました。&quot;*

   詳しくは、 [外部アカウント](../../administration/using/external-accounts.md).

* *&quot;現在の IP アフィニティはどの送信プロセスでも処理されないので、メッセージを送信できません。&quot;*

   このメッセージが表示される場合、IP アフィニティの定義レベルまたは送信プロセスレベルに問題があります。 Adobe 管理者にお問い合わせください。

* *「これは、標準のトランザクションメッセージテンプレートです。 変更する場合は、コピーを作成して作業する必要があります。」*

   標準搭載のトランザクションメッセージテンプレートの一部は、組み込みのランディングページテンプレートです。 詳しくは、[この節](../../channels/using/landing-page-templates.md)を参照してください。

* *「このメッセージは、技術トランザクションメッセージテンプレートです。 変更や公開はできません。」*

   この警告は、編集できない空のトランザクションメッセージテンプレートで表示されます。 トランザクションメッセージについて詳しくは、 [この節](../../channels/using/getting-started-with-transactional-msg.md).

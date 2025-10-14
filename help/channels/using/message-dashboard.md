---
title: メッセージダッシュボード
description: アクションバーや様々な機能ブロックなど、メッセージダッシュボードの構成要素を確認します。
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
ht-degree: 4%

---

# メッセージダッシュボード{#message-dashboard}

メッセージダッシュボードは、様々なアイコン（アクションバーに再グループ化）と、メッセージのパラメーターを確立して送信できる様々な機能ブロックで構成されるワークスペースです。 これらの要素については、以降で説明します。

![](assets/delivery_dashboard_2.png)

## 灰色のバー {#gray-bar}

灰色のバーは、メッセージにリンクされた様々なアイコンを再グループ化します。

* **[!UICONTROL Summary]**：メッセージに関する主な情報の表示/非表示を切り替えます。
* **[!UICONTROL Edit properties]**：メッセージの [&#x200B; 詳細設定パラメーター &#x200B;](../../administration/using/configuring-email-channel.md#list-of-email-properties) を編集できます。
* **[!UICONTROL Reports]**：メッセージに関するレポートへのアクセスを許可します。

**関連トピック：**

* [チャネルの設定](../../administration/using/about-channel-configuration.md)
* [レポートへのアクセス](../../reporting/using/about-dynamic-reports.md)

## アクションバー {#action-bar}

アクションバーには、メッセージを操作するための様々なアイコンがあります。

![](assets/delivery_dashboard_4.png)

設定されたパラメーターと実行された進行状況によっては、特定のアイコンを使用できないことがあります。

* **[!UICONTROL Show proofs]**：送信された配達確認が存在する場合、そのリストを表示または非表示にします。 このボタンは、配達確認を送信した場合にのみ有効になります。

  配達確認について詳しくは、[&#x200B; 配達確認の送信 &#x200B;](../../sending/using/sending-proofs.md) を参照してください。

* **[!UICONTROL Send a test]**：使用する承認モード（**[!UICONTROL Email rendering]** （メールのみ）、**[!UICONTROL Proof]** またはその両方）を選択できます。 テストプロファイルについて詳しくは、[&#x200B; 配達確認の送信 &#x200B;](../../sending/using/sending-proofs.md) を参照してください。 このボタンは、テストプロファイルを作成した場合にのみ有効になります。

* **[!UICONTROL Prepare send]**：送信の準備を開始します。 **[!UICONTROL Deployment]** ブロックが表示され、準備の結果が表示されます。 このボタンは、ターゲットが入力された場合にのみ表示されます。 対応するボタンを使用して、いつでも準備を停止できます。 メッセージの準備について詳しくは、[&#x200B; 送信の準備 &#x200B;](../../sending/using/preparing-the-send.md) を参照してください。

* **[!UICONTROL Confirm send]**: メッセージの送信を確認します。 送信統計が **[!UICONTROL Deployment]** ブロックに表示されます。 このボタンは、送信の準備が完了した後にのみ表示されます。 **送信を停止** ボタンと送信ボタンを使用して、送信をいつでも停止または一時停止 **[!UICONTROL Pause]** きます。 送信の確認について詳しくは、[&#x200B; メッセージの送信 &#x200B;](../../sending/using/confirming-the-send.md) を参照してください。

## ブロック {#blocks}

メイン画面は、異なるブロックで構成されています。 ブロック内をクリックして、対応するパラメーター画面にアクセスします。

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**：メッセージの準備または送信の進行状況を追跡できます。 送信ログと分析ログにアクセスするには、このブロックの右下のセクションにあるボタンをクリックします。 このブロックは、送信が準備された場合にのみ表示されます。 詳しくは、こちらを参照してください。 [&#x200B; 送信の確認 &#x200B;](../../sending/using/confirming-the-send.md) を参照してください。
* **[!UICONTROL Audience]**：メッセージのメインターゲットとテストプロファイルを確立できます。 [オーディエンスの作成](../../audiences/using/creating-audiences.md)を参照してください。
* **[!UICONTROL Schedule]**: メッセージを送信する日付を指定できます。 [&#x200B; スケジュール設定 &#x200B;](../../sending/using/about-scheduling-messages.md) を参照してください。
* **[!UICONTROL Content]**: メッセージのコンテンツを定義し、プレビューできます。 [&#x200B; メッセージを送信するための主な手順 &#x200B;](../../channels/using/key-steps-to-send-a-message.md) を参照してください。

## 警告 {#warnings}

場合によっては、警告がメッセージダッシュボードの上の黄色のバナーに表示されることがあります。

![](assets/delivery_dashboard_warnings.png)

表示できるメッセージのリストを以下に示します。

* *「この電子メールに対して SMTP テストモード オプションが有効になっています。メッセージは送信されません。」*

  詳しくは、[この節](../../administration/using/configuring-email-channel.md#smtp-test-mode)を参照してください。

* *「ルーティング外部アカウントが無効になりました。」*

  詳しくは、[&#x200B; 外部アカウント &#x200B;](../../administration/using/external-accounts.md) を参照してください。

* *「現在の IP アフィニティがどの送信プロセスでも処理されないので、メッセージを送信できません。」*

  このメッセージが表示された場合は、IP アフィニティ定義レベルまたは送信プロセスレベルで問題があります。 Adobe管理者にお問い合わせください。

* *「これは、標準のトランザクションメッセージテンプレートです。 変更する場合は、複製してコピーに対して作業を行う必要があります。*

  これらの標準提供のトランザクションメッセージテンプレートの一部は、ビルトインのランディングページテンプレートです。 詳しくは、[この節](../../channels/using/landing-page-templates.md)を参照してください。

* *「このメッセージは、テクニカルトランザクションメッセージテンプレートです。 変更や公開はできません。」*

  この警告は、編集できない空のトランザクションメッセージテンプレートに表示されます。 トランザクションメッセージについて詳しくは、[&#x200B; この節 &#x200B;](../../channels/using/getting-started-with-transactional-msg.md) を参照してください。

---
solution: Campaign Standard
product: campaign
title: メッセージダッシュボード
description: アクションバーや様々な機能ブロックなど、メッセージダッシュボードの構成要素を確認します。
audience: channels
content-type: reference
topic-tags: about-communication-channels
context-tags: delivery,main
feature: Overview
role: Business Practitioner
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 6%

---


# メッセージダッシュボード{#message-dashboard}

メッセージダッシュボードは、様々なアイコン（アクションバーに再グループ化されたアイコン）と、メッセージのパラメーターを確立して送信できる様々な機能ブロックで構成されたワークスペースです。 以下、これらの要素を紹介する。

![](assets/delivery_dashboard_2.png)

## グレーバー{#gray-bar}

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

* **[!UICONTROL Show proofs]**:送信された配達確認が存在する場合は、そのリストを表示/非表示にします。このボタンは、配達確認を送信した後にのみ有効になります。

   配達確認について詳しくは、[配達確認の送信](../../sending/using/sending-proofs.md)を参照してください。

* **[!UICONTROL Send a test]**:使用する承認モードを選択できます。 **[!UICONTROL Email rendering]** （電子メールのみ）またはその両方 **[!UICONTROL Proof]** を送信します。テストプロファイルについて詳しくは、[配達確認の送信](../../sending/using/sending-proofs.md)を参照してください。 このボタンは、テストプロファイルを作成した場合にのみ有効になります。

* **[!UICONTROL Prepare send]**:送信を準備する開始。**[!UICONTROL Deployment]**&#x200B;ブロックが表示され、準備の結果が表示されます。 このボタンは、ターゲットを入力した場合にのみ表示されます。 対応するボタンを使用すると、いつでも準備を停止できます。 メッセージの準備について詳しくは、[送信の準備](../../sending/using/preparing-the-send.md)を参照してください。

* **[!UICONTROL Confirm send]**:メッセージの送信を確認します。送信統計は&#x200B;**[!UICONTROL Deployment]**&#x200B;ブロックに表示されます。 このボタンは、送信の準備が完了した後にのみ表示されます。 「**送信を停止**」ボタンと「**[!UICONTROL Pause]**」ボタンを使用すると、いつでも送信を停止または一時停止できます。 送信の確認について詳しくは、[メッセージの送信](../../sending/using/confirming-the-send.md)を参照してください。

## ブロック {#blocks}

メイン画面は異なるブロックで構成されています。 ブロック内をクリックして、対応するパラメータ画面にアクセスします。

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**:メッセージの準備または送信の進行状況を追跡できます。送信ログと分析ログにアクセスするには、このブロックの右下のセクションにあるボタンをクリックします。 このブロックは、送信の準備が完了した後にのみ表示されます。 詳しくは、 「[送信の確認](../../sending/using/confirming-the-send.md)」を参照してください。
* **[!UICONTROL Audience]**:メッセージのメインターゲットとテストプロファイルを確立できます。[オーディエンスの作成](../../audiences/using/creating-audiences.md)を参照してください。
* **[!UICONTROL Schedule]**:メッセージの送信日を指定できます。[スケジュール](../../sending/using/about-scheduling-messages.md)を参照してください。
* **[!UICONTROL Content]**:メッセージの内容とプレビューを定義できます。[メッセージを送信するための主な手順](../../channels/using/key-steps-to-send-a-message.md)を参照してください。

## 警告 {#warnings}

メッセージダッシュボードの上部に黄色のバナーで警告が表示される場合があります。

![](assets/delivery_dashboard_warnings.png)

次に、表示できるメッセージのリストを示します。

* *「SMTP test modeオプションは、次の電子メールに対して有効です：メッセージは送信されません。」*

   詳しくは、[この節](../../administration/using/configuring-email-channel.md#smtp-test-mode)を参照してください。

* *&quot;ルーティング外部アカウントは無効になっています。&quot;*

   詳しくは、[外部アカウント](../../administration/using/external-accounts.md)を参照してください。

* *&quot;現在のIPアフィニティは送信プロセスで処理されないため、メッセージを送信できません。&quot;*

   このメッセージが表示される場合は、IPアフィニティ定義レベルまたは送信プロセスレベルで問題が発生しています。 Adobe 管理者にお問い合わせください。

* *「これは既製のトランザクションメッセージテンプレートです変更したい場合は、重複してコピーに取り組む必要があります。&quot;*

   あらかじめ用意されているこれらのトランザクションメッセージテンプレートの一部は、組み込みのランディングページテンプレートです。 詳しくは、[この節](../../channels/using/landing-page-templates.md)を参照してください。

* *同氏は、「このメッセージはテクニカルなトランザクションメッセージテンプレートだ。変更や発行はできません。&quot;*

   この警告は、編集できない空のトランザクションメッセージテンプレートで表示されます。 トランザクションメッセージの詳細については、[このセクション](../../channels/using/getting-started-with-transactional-msg.md)を参照してください。

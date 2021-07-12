---
solution: Campaign Standard
product: campaign
title: メッセージダッシュボード
description: アクションバーや様々な機能ブロックなど、メッセージダッシュボードの構成要素を確認します。
audience: channels
content-type: reference
topic-tags: about-communication-channels
context-tags: delivery,main
feature: 概要
role: User
level: Beginner
exl-id: 886aae39-2029-471c-b4d1-c6ca57d0e568
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 6%

---

# メッセージダッシュボード{#message-dashboard}

メッセージダッシュボードは、様々なアイコンで構成され、アクションバーに再グループ化されたワークスペースです。メッセージのパラメーターを設定して送信できる様々な機能ブロックが用意されています。 これらの要素は、以下に示します。

![](assets/delivery_dashboard_2.png)

## グレーのバー {#gray-bar}

灰色のバーは、メッセージにリンクされた様々なアイコンを再グループ化します。

* **[!UICONTROL Summary]**:メッセージに関するメイン情報の表示/非表示を切り替えます。
* **[!UICONTROL Edit properties]**:メッセージの詳細設定パラメーターを編 [集できます](../../administration/using/configuring-email-channel.md#list-of-email-properties)。
* **[!UICONTROL Reports]**:は、メッセージに関するレポートにアクセスできます。

**関連トピック：**

* [チャネルの設定](../../administration/using/about-channel-configuration.md)
* [レポートへのアクセス](../../reporting/using/about-dynamic-reports.md)

## アクションバー {#action-bar}

アクションバーには、メッセージを操作するための様々なアイコンがあります。

![](assets/delivery_dashboard_4.png)

設定済みのパラメーターと実行された進行状況によっては、特定のアイコンを使用できない場合があります。

* **[!UICONTROL Show proofs]**:送信済みの配達確認のリストが存在する場合は、そのリストを表示または非表示にします。このボタンは、配達確認を送信した後でのみ有効になります。

   配達確認について詳しくは、[配達確認の送信](../../sending/using/sending-proofs.md)を参照してください。

* **[!UICONTROL Send a test]**:使用する承認モードを選択できます。 **[!UICONTROL Email rendering]** （電子メールのみ）またはその **[!UICONTROL Proof]** 両方。テストプロファイルについて詳しくは、[配達確認の送信](../../sending/using/sending-proofs.md)を参照してください。 このボタンは、テストプロファイルを作成した場合にのみ有効になります。

* **[!UICONTROL Prepare send]**:送信の準備を開始します。**[!UICONTROL Deployment]**&#x200B;ブロックが表示され、準備の結果が表示されます。 このボタンは、ターゲットを入力した場合にのみ表示されます。 対応するボタンを使用して、いつでも準備を停止できます。 メッセージの準備について詳しくは、[送信の準備](../../sending/using/preparing-the-send.md)を参照してください。

* **[!UICONTROL Confirm send]**:メッセージの送信を確認します。送信統計が&#x200B;**[!UICONTROL Deployment]**&#x200B;ブロックに表示されます。 このボタンは、送信の準備が完了した後にのみ表示されます。 **「**&#x200B;を送信を停止」ボタンと&#x200B;**[!UICONTROL Pause]**&#x200B;ボタンを使用して、いつでも送信を停止または一時停止できます。 送信の確認について詳しくは、[メッセージの送信](../../sending/using/confirming-the-send.md)を参照してください。

## ブロック {#blocks}

メイン画面は異なるブロックで構成されています。 ブロック内をクリックして、対応するパラメータ画面にアクセスします。

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**:では、メッセージの準備または送信の進行状況をトラッキングできます。このブロックの右下にある「 」ボタンをクリックして、送信ログと分析ログにアクセスします。 このブロックは、送信が準備された場合にのみ表示されます。 詳しくは、こちらを参照してください。 [送信の確認](../../sending/using/confirming-the-send.md)を参照してください。
* **[!UICONTROL Audience]**:では、メッセージのメインターゲットとテストプロファイルを確立できます。[オーディエンスの作成](../../audiences/using/creating-audiences.md)を参照してください。
* **[!UICONTROL Schedule]**:メッセージの送信日を指定できます。[スケジュール](../../sending/using/about-scheduling-messages.md)を参照してください。
* **[!UICONTROL Content]**:では、メッセージのコンテンツを定義し、プレビューできます。[メッセージを送信するための主な手順](../../channels/using/key-steps-to-send-a-message.md)を参照してください。

## 警告 {#warnings}

場合によっては、メッセージダッシュボードの上に黄色いバナーで警告が表示されることがあります。

![](assets/delivery_dashboard_warnings.png)

表示可能なメッセージのリストを次に示します。

* *「SMTPテストモードオプションは、この電子メールに対して有効です。メッセージは送信されません。」*

   詳しくは、[この節](../../administration/using/configuring-email-channel.md#smtp-test-mode)を参照してください。

* *&quot;ルーティング外部アカウントが無効になりました。&quot;*

   詳しくは、[外部アカウント](../../administration/using/external-accounts.md)を参照してください。

* *&quot;現在のIPアフィニティがどの送信プロセスでも処理されていないため、メッセージを送信できません。&quot;*

   このメッセージが表示された場合は、IPアフィニティの定義レベルまたは送信プロセスレベルで問題が発生しています。 Adobe 管理者にお問い合わせください。

* *「これは、標準のトランザクションメッセージテンプレートです。変更する場合は、コピーを作成して作業する必要があります。&quot;*

   標準搭載のトランザクションメッセージテンプレートの一部は、組み込みのランディングページテンプレートです。 詳しくは、[この節](../../channels/using/landing-page-templates.md)を参照してください。

* *「このメッセージは、テクニカルトランザクションメッセージテンプレートです。変更やパブリッシュはできません。&quot;*

   この警告は、編集できない空のトランザクションメッセージテンプレートで表示されます。 トランザクションメッセージについて詳しくは、[この節](../../channels/using/getting-started-with-transactional-msg.md)を参照してください。

---
title: Campaign Standardモバイルガイド
description: モバイルアプリの設定方法やプッシュ通知およびアプリ内メッセージの作成方法など、Adobe Campaign Standardのモバイル配信に関する一般的なガイドラインについて詳しく説明します。
audience: channels
content-type: reference
topic-tags: mobile-guide
feature: Overview
role: User
level: Beginner
exl-id: d4e1b935-b21f-4a24-99ba-f455db0f7cfc
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 22%

---

# モバイルチャネルの概要 {#mobile-guide}

<table style="table-layout:fixed">
<tr>
<td><img src="assets/do-not-localize/config_push.png" width="60px"><p>プッシュ通知用にモバイルアプリケーションを設定する方法を説明します </br><a href="#configuration-push">ここをクリック</a></p></td>
<td><img src="assets/do-not-localize/config_inapp.png" width="60px"><p>アプリ内メッセージ用にモバイルアプリを設定する方法を説明します </br><a href="#configuring-mobile-app">ここをクリック</a></p></td>
</tr>
<tr>
<td><img src="assets/do-not-localize/push2.png" width="60px"><p>プッシュ通知の作成方法の詳細を説明します </br><a href="#create-push">ここをクリック</a></p></td>
<td><img src="assets/do-not-localize/inapp.png" width="60px"><p>アプリ内メッセージの作成方法を説明します</br><a href="#create-inapp">ここをクリック</a></p></td></tr>
</table>

## モバイル配信について {#about-mobile}

Adobe Campaignでは、各種チャネルでパーソナライズされたメッセージを作成して送信し、専用レポートを通じてその効果を測定できます。

Adobe Campaign Standardでは、次の 3 つのチャネルを使用してモバイル配信を送信できます。

* SMS（ SMS メッセージについての節で説明）
* プッシュ通知（プッシュ通知についての節で説明）。
* アプリ内メッセージ（アプリ内メッセージについての節で説明）。

## プッシュ通知用のモバイルアプリケーションの設定 {#configuration-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Adobe Experience Platform SDK を使用したモバイルアプリケーションの設定</strong></p>
    </div>
    <p>アプリ内メッセージとプッシュ通知を送信するには、Adobe Experience Platform SDK を利用して、モバイルアプリケーションをAdobe Campaignで設定する必要があります。詳しくは、</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Campaign Standardプッシュ通知のペイロード構造について</strong></p>
    </div>
    <p>プッシュ通知がAdobe Campaign Standardからアプリに正常に送信されたときにモバイルアプリで受け取るペイロードの構造について詳しく説明します。詳しくは、</br><a href="../../administration/using/push-payload.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>ローカル通知トラッキングの実装</strong></p>
    </div>
    <p>ローカル通知トラッキングが正しく実装されていることを確認する方法を説明します。 詳しくは、</br><a href="../../administration/using/local-tracking.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>プッシュトラッキングの実装</strong></p>
    </div>
    <p>iOSおよび Android で、プッシュ通知トラッキングが正しく実装されていることを確認する方法について説明します。詳しくは、</br><a href="../../administration/using/push-tracking.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
</table>

## アプリ内メッセージ用のモバイルアプリの設定 {#configuring-mobile-app}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Adobe Experience Platform SDK を使用したモバイルアプリケーションの設定</strong></p>
    </div>
    <p>アプリ内メッセージとプッシュ通知を送信するには、Adobe Experience Platform SDK を利用して、モバイルアプリケーションをAdobe Campaignで設定する必要があります。詳しくは、</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Adobe Experience Platform SDK の使用をサポートするモバイルの使用例</strong></p>
    </div>
    <p>Adobe Experience Platform SDK を使用してAdobe Campaign Standardでサポートされるモバイルの使用例について詳しく説明します。詳しくは、</br><a href="../../administration/using/supported-mobile-use-cases.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Adobe Campaign Standard のユースケースをサポートするタグルールの設定</strong></p>
    </div>
    <p><a href="../../administration/using/configuring-rules-launch.md"><strong>ここをクリック</strong></a> ：データ収集 UI でデータ要素とルールの作成を開始し、モバイルアプリケーションからAdobe Campaign Standardに PII やその他のデータを送信します。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>ローカル通知トラッキングの実装</strong></p>
    </div>
    <p>ローカル通知トラッキングが正しく実装されていることを確認する方法を説明します。 詳しくは、</br><a href="../../administration/using/local-tracking.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
</table>

## プッシュ通知の作成 {#create-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>プッシュ通知の準備と送信</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-a-push-notification.md"><strong>こちらを参照</strong></a> プッシュ通知を準備し、ターゲットオーディエンスに送信する方法を説明します。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>プッシュ通知のカスタマイズ</strong></p>
    </div>
    <p>Adobe Campaignでは、配信を微調整するために、プッシュ通知のデザイン中に一連のオプションにアクセスできます。詳しくは、</br><a href="../../channels/using/customizing-a-push-notification.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>多言語プッシュ通知の作成</strong></p>
    </div>
    <p>ユーザーの設定言語および地域に基づいてメッセージを送信することで、プッシュ通知コンテンツをパーソナライズします。詳しくは、</br><a href="../../channels/using/creating-a-multilingual-push-notification.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Adobe Campaign Standardのプッシュ通知からの画像の表示</strong></p>
    </div>
    <p><a href="../../administration/using/image-push-notification.md"><strong>こちらを参照</strong></a> Adobe Campaignのプッシュ通知からの画像をiOSデバイスに表示する方法です。</p>
    <br>
  </td>
</tr>
</table>

## アプリ内メッセージの作成 {#create-inapp}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>アプリ内メッセージの準備と送信</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-an-in-app-message.md"><strong>こちらを参照</strong></a> アプリ内メッセージを準備し、ターゲットオーディエンスに送信する方法を説明します。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>アプリ内メッセージのカスタマイズ</strong></p>
    </div>
    <p>Adobe Campaignでは、配信を微調整するために、アプリ内メッセージのデザイン中に、一連の詳細設定オプションにアクセスできます。詳しくは、</br><a href="../../channels/using/customizing-an-in-app-message.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>ローカル通知メッセージタイプのカスタマイズ</strong></p>
    </div>
    <p>ローカル通知は、特定の時間に、またはイベントに応じて、アプリでのみトリガーできます。詳しくは、</br><a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>アプリ内レポート</strong></p>
    </div>
    <p>アプリ内配信レポートには、アプリ内配信に関する詳細が表示されます。詳しくは、</br><a href="../../reporting/using/in-app-report.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
</table>

## SMS メッセージの作成 {#create-sms}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>SMS メッセージの作成</strong></p>
    </div>
    <p>SMS 配信の作成は、通常のメールの作成と非常に似ています。</br>手順 <a href="../../channels/using/creating-an-sms-message.md"><strong>詳細はこちら</strong></a> このチャネルに固有の設定について説明します。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>SMS メッセージのカスタマイズ
</strong></p>
    </div>
    <p>Adobe Campaignでは、配信を微調整するために、SMS メッセージのデザイン中に一連の詳細設定オプションにアクセスできます。</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong>詳しくは、ここをクリックしてください。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>受信 SMS の管理</strong></p>
    </div>
    <p>プロファイルが Campaign 経由で送信された SMS メッセージに返信する場合、自動的に返信されるメッセージと、実行するアクションを設定できます。ローカル通知メッセージタイプのカスタマイズ</br><a href="../../channels/using/managing-incoming-sms.md"><strong>詳しくは、ここをクリックしてください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>SMS レポート</strong></p>
    </div>
    <p>SMS レポートには、配信率やバウンス率など、SMS 配信に関する詳細が表示されます。詳しくは、</br><a href="../../reporting/using/sms-report.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
</table>

## モバイルのトラブルシューティング {#mobile-troubleshooting}

以下のページは、Adobe Campaign Classicでモバイル配信を使用する際に発生する最も一般的な問題の解決に役立ちます。

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>プッシュ通知の FAQ</strong></p>
    </div>
    <p><a href="../../channels/using/about-push-notifications.md#push-faq"><strong>詳しくは、ここをクリックしてください。</p>
  </td>
  <td>
    <div>
    <p><strong>Adobe Launch 同期に関する FAQ</strong></p>
    </div>
    <p><a href="../../channels/using/in-app-faq.md"><strong>詳しくは、ここをクリックしてください。</p>
  </td>
  <td>
    <div>
    <p><strong>アプリ内 FAQ</strong></p>
    </div>
    <p><a href="../../administration/using/syncwithlaunch-faq.md"><strong>詳しくは、ここをクリックしてください。</p>
  </td>
</tr>
</table>

---
title: Campaign Standard モバイルガイド
description: モバイルアプリの設定方法やプッシュ通知およびアプリ内メッセージの作成方法など、Adobe Campaign Standardのモバイル配信に関する一般的なガイドラインについて詳しく説明します。
audience: channels
content-type: reference
topic-tags: mobile-guide
feature: Overview
role: User
level: Beginner
hidefromtoc: true
source-git-commit: 34270a2caff0932b56d00ccf721bdba87eb61f81
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 23%

---

# モバイルチャネルの概要 {#mobile-guide}

<table style="table-layout:fixed">
<tr>
<td><img src="assets/do-not-localize/config_push.png" width="60px"><p>プッシュ通知用にモバイルアプリケーションを設定する方法を説明します。</br><a href="#configuration-push">ここをクリック</a></p></td>
<td><img src="assets/do-not-localize/config_inapp.png" width="60px"><p>アプリ内メッセージ用にモバイルアプリケーションを設定する方法を説明します。</br><a href="#configuring-mobile-app">ここをクリック</a></p></td>
</tr>
<tr>
<td><img src="assets/do-not-localize/push2.png" width="60px"><p>プッシュ通知の作成方法の詳細</br><a href="#create-push">ここをクリック</a></p></td>
<td><img src="assets/do-not-localize/inapp.png" width="60px"><p>アプリ内メッセージの作成方法を説明します。</br><a href="#create-inapp">ここをクリック</a></p></td></tr>
</table>

## モバイル配信について {#about-mobile}

Adobe Campaignでは、専用レポートを使用して、パーソナライズされたメッセージを作成して様々なチャネルに送信し、その効果を測定できます。

Adobe Campaign Standardでは、次の3つの異なるチャネルを使用してモバイル配信を送信できます。

* SMS（ SMSメッセージについての節で説明）
* プッシュ通知（プッシュ通知についての節で説明）。
* アプリ内メッセージ（アプリ内メッセージについての節で説明）。

## プッシュ通知用のモバイルアプリケーションの設定 {#configuration-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Adobe Experience Platform SDKを使用したモバイルアプリケーションの設定</strong></p>
    </div>
    <p>アプリ内メッセージとプッシュ通知を送信するには、Adobe Experience Platform SDKを利用して、モバイルアプリケーションをAdobe Campaignで設定する必要があります。詳しくは、</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Campaign Standardプッシュ通知のペイロード構造について</strong></p>
    </div>
    <p>プッシュ通知がAdobe Campaign Standardからアプリに正常に送信された場合にモバイルアプリで受信されるペイロードの構造について説明します。詳しくは、</br><a href="../../administration/using/push-payload.md"><strong>ここをクリック</strong></a>してください。</p>
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
    <p>iOSおよびAndroidでプッシュ通知トラッキングが正しく実装されていることを確認する方法について説明します。詳しくは、</br><a href="../../administration/using/push-tracking.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
</table>

## アプリ内メッセージ用のモバイルアプリの設定 {#configuring-mobile-app}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Adobe Experience Platform SDKを使用したモバイルアプリケーションの設定</strong></p>
    </div>
    <p>アプリ内メッセージとプッシュ通知を送信するには、Adobe Experience Platform SDKを利用して、モバイルアプリケーションをAdobe Campaignで設定する必要があります。詳しくは、</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Adobe Experience Platform SDKを使用してサポートされるモバイルの使用例</strong></p>
    </div>
    <p>Adobe Experience Platform SDKを使用してAdobe Campaign Standardでサポートされるモバイルの使用例について詳しく説明します。詳しくは、</br><a href="../../administration/using/supported-mobile-use-cases.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Adobe Campaign Standardの使用例をサポートするためのAdobe Experience Platform Launchルールの設定</strong></p>
    </div>
    <p><a href="../../administration/using/configuring-rules-launch.md"><strong>「ここをク</strong></a> リックして、Adobe Experience Platform Launchでデータ要素とルールの作成を開始し、モバイルアプリケーションからAdobe Campaign StandardにPIIやその他のデータを送信します。</p>
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
    <p><a href="../../channels/using/preparing-and-sending-a-push-notification.md"><strong>ここ</strong></a> では、プッシュ通知を準備し、ターゲットオーディエンスに送信する方法について説明します。</p>
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
    <p>ユーザーの好みの言語と地域に基づいてメッセージを送信することで、プッシュ通知のコンテンツをパーソナライズします。詳しくは、</br><a href="../../channels/using/creating-a-multilingual-push-notification.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Adobe Campaign Standard のプッシュ通知からの画像の表示</strong></p>
    </div>
    <p><a href="../../administration/using/image-push-notification.md"><strong>iOSデ</strong></a> バイスでAdobe Campaignのプッシュ通知から画像を表示する方法を説明します。</p>
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
    <p><a href="../../channels/using/preparing-and-sending-an-in-app-message.md"><strong>アプリ</strong></a> 内メッセージを準備し、ターゲットオーディエンスに送信する方法を説明します。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>アプリ内メッセージのカスタマイズ</strong></p>
    </div>
    <p>Adobe Campaignでは、配信を微調整するために、アプリ内メッセージのデザイン中に一連の詳細設定オプションにアクセスできます。詳しくは、</br><a href="../../channels/using/customizing-an-in-app-message.md"><strong>ここをクリック</strong></a>してください。</p>
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
    <p>アプリ内配信に関する詳細は、アプリ内レポートで確認できます。詳しくは、</br><a href="../../reporting/using/in-app-report.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
</table>

## SMSメッセージの作成 {#create-sms}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>SMS メッセージの作成</strong></p>
    </div>
    <p>SMS 配信の作成は、通常の E メールの作成と非常に似ています。</br>ここで説明 <a href="../../channels/using/creating-an-sms-message.md"><strong>する</strong></a> 手順は、このチャネルに固有の設定について説明します。</br></p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>SMSメッセージのカスタマイズ
</strong></p>
    </div>
    <p>Adobe Campaignでは、配信を微調整するために、SMSメッセージのデザイン中に一連の詳細設定オプションにアクセスできます。詳しくは、</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong>ここをクリックしてください。</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong></p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>受信 SMS の管理</strong></p>
    </div>
    <p>プロファイルがCampaign経由で送信されたSMSメッセージに返信する場合、自動的に返信されるメッセージと実行するアクションを設定できます。ローカル通知メッセージタイプのカスタマイズ</br><a href="../../channels/using/managing-incoming-sms.md"><strong>詳しくは、ここをクリックしてください。</br><a href="../../channels/using/managing-incoming-sms.md"><strong></p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>SMS レポート</strong></p>
    </div>
    <p>SMSレポートは、配信率やバウンス率など、SMS配信に関する詳細を提供します。詳しくは、</br><a href="../../reporting/using/sms-report.md"><strong>ここをクリック</strong></a>してください。</p>
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
    <p><strong>プッシュ通知のFAQ</strong></p>
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



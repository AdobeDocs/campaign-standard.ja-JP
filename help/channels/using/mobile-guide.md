---
title: Campaign Standard モバイルガイド
description: モバイルアプリケーションの設定方法、プッシュ通知やアプリ内メッセージの作成方法など、Adobe Campaign Standardのモバイル配信に関する一般的なガイドラインについて説明します。
audience: channels
content-type: reference
topic-tags: mobile-guide
feature: Overview
role: User
level: Beginner
exl-id: d4e1b935-b21f-4a24-99ba-f455db0f7cfc
TQID: https://experienceleague.adobe.com/sBjTFd0Su7In8xai4J8cp5QAsAh6pOVOf4OVAijQmXo
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 799
ht-degree: 18%

---

# モバイルチャネルの概要 {#mobile-guide}

<table style="table-layout:fixed">
<tr>
<td><img src="assets/do-not-localize/config_push.png" width="60px"><p>プッシュ通知用にモバイルアプリケーションを設定する方法について説明します</br><a href="#configuration-push">ここをクリック </a></p></td>
<td><img src="assets/do-not-localize/config_inapp.png" width="60px"><p>アプリ内メッセージ用にモバイルアプリケーションを設定する方法について説明します</br><a href="#configuring-mobile-app">ここをクリック </a></p></td>
</tr>
<tr>
<td><img src="assets/do-not-localize/push2.png" width="60px"><p>プッシュ通知の作成方法について詳しくは、</br><a href="#create-push">ここをクリック </a></p></td>
<td><img src="assets/do-not-localize/inapp.png" width="60px"><p>アプリ内メッセージの作成方法について説明します</br><a href="#create-inapp">ここをクリック </a></p></td></tr>
</table>

## モバイル配信について {#about-mobile}

Adobe Campaignを活用すれば、パーソナライズされたメッセージをさまざまなチャネルで作成および送信し、専用のレポートを通じてその効果を測定できます。

Adobe Campaign Standardでは、3つの異なるチャネルを通じてモバイル配信を送信できます。

* SMSについては、「SMS メッセージについて」セクションに表示されます。
* プッシュ通知。プッシュ通知の概要セクションに表示されます。
* アプリ内メッセージ。アプリ内メッセージについてセクションに表示されます。

## モバイルアプリケーションのプッシュ通知設定 {#configuration-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Adobe Experience Platform SDKを使用したモバイルアプリケーションの設定</strong></p>
    </div>
    <p>アプリ内メッセージとプッシュ通知を送信するには、モバイルアプリケーションをAdobe Campaign SDKを活用してAdobe Experience Platformで設定する必要があります。</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>詳細については、こちらをクリック </strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Campaign Standard プッシュ通知ペイロード構造について</strong></p>
    </div>
    <p>Adobe Campaign Standardからアプリにプッシュ通知が正常に送信されたときに、モバイルアプリケーションで受信されるペイロードの構造について詳しくは、</br><a href="../../administration/using/push-payload.md"><strong>ここをクリック </strong></a>してください。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>ローカル通知トラッキングの実装</strong></p>
    </div>
    <p>ローカル通知トラッキングが正しく実装されていることを確認する方法については、こちらを参照してください。 詳しくは、</br><a href="../../administration/using/local-tracking.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>プッシュトラッキングの実装</strong></p>
    </div>
    <p>IOSとAndroidでプッシュ通知トラッキングが正しく実装されていることを確認する方法について説明します。</br><a href="../../administration/using/push-tracking.md"><strong>詳細については、こちらをクリック </strong></a>してください。</p>
    <br>
  </td>
</tr>
</table>

## アプリ内メッセージ用モバイルアプリケーションの設定 {#configuring-mobile-app}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Adobe Experience Platform SDKを使用したモバイルアプリケーションの設定</strong></p>
    </div>
    <p>アプリ内メッセージとプッシュ通知を送信するには、モバイルアプリケーションをAdobe Campaign SDKを活用してAdobe Experience Platformで設定する必要があります。</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>詳細については、こちらをクリック </strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Adobe Experience Platform SDKを使用してサポートされるモバイルのユースケース</strong></p>
    </div>
    <p>Adobe Experience Platform SDKを使用してAdobe Campaign Standardでサポートされているモバイルユースケースについて詳しくは、</br><a href="../../administration/using/supported-mobile-use-cases.md"><strong>ここをクリック </strong></a>してください。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Adobe Campaign Standard のユースケースをサポートするタグルールの設定</strong></p>
    </div>
    <p><a href="../../administration/using/configuring-rules-launch.md"><strong> モバイルアプリケーションからAdobe Campaign StandardにPIIおよびその他のデータを送信するために、データ収集UIでデータ要素とルールの作成を開始するには、ここをクリック </strong></a>します。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>ローカル通知トラッキングの実装</strong></p>
    </div>
    <p>ローカル通知トラッキングが正しく実装されていることを確認する方法については、こちらを参照してください。 詳しくは、</br><a href="../../administration/using/local-tracking.md"><strong>ここをクリック</strong></a>してください。</p>
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
    <p><a href="../../channels/using/preparing-and-sending-a-push-notification.md"><strong>ここでは</strong></a> プッシュ通知を準備する方法と、ターゲットオーディエンスにプッシュ通知を送信する方法について説明します。</p>
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
    <p>顧客が好む言語や地域にもとづいてメッセージを送信することで、プッシュ通知コンテンツをパーソナライズできます。詳しくは、</br><a href="../../channels/using/creating-a-multilingual-push-notification.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Adobe Campaign Standard プッシュ通知からの画像の表示</strong></p>
    </div>
    <p><a href="../../administration/using/image-push-notification.md"><strong>iOS デバイスでAdobe Campaign プッシュ通知から画像を表示する方法について、こちらを学びましょう</strong></a>。</p>
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
    <p><a href="../../channels/using/preparing-and-sending-an-in-app-message.md"><strong>ここでは</strong></a> アプリ内メッセージを準備する方法と、ターゲットオーディエンスに送信する方法について説明します。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>アプリ内メッセージのカスタマイズ</strong></p>
    </div>
    <p>配信を微調整するために、Adobe Campaignでは、アプリ内デザイン中に一連の高度なオプションにアクセスできます。</br><a href="../../channels/using/customizing-an-in-app-message.md"><strong>詳細については、こちらをクリック </strong></a>してください。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>ローカル通知メッセージタイプのカスタマイズ</strong></p>
    </div>
    <p>ローカル通知は、特定の時間に、またはイベントに応じて、アプリでのみトリガーできます。 詳しくは、</br><a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>アプリ内レポート</strong></p>
    </div>
    <p>アプリ内レポートには、アプリ内配信に関連する詳細が表示されます。詳しくは、</br><a href="../../reporting/using/in-app-report.md"><strong>ここをクリック</strong></a>してください。</p>
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
    <p>SMS 配信の作成は、通常のメールの作成と非常に似ています。 </br>ここでは</strong></a>詳細な手順<a href="../../channels/using/creating-an-sms-message.md"><strong>は、このチャネルに固有の設定を示しています。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>SMS メッセージのカスタマイズ
</strong></p>
    </div>
    <p>配信を微調整するために、Adobe Campaignでは、SMS メッセージのデザイン中に一連の高度なオプションにアクセスできます。</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong>詳細については、ここをクリックしてください。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>受信 SMS の管理</strong></p>
    </div>
    <p>Campaignを介して送信されたSMS メッセージに対してプロファイルが返信する場合、自動的に返信されるメッセージと、実行するアクションを設定できます。ローカル通知メッセージの種類をカスタマイズする</br><a href="../../channels/using/managing-incoming-sms.md"><strong>詳細については、ここをクリックしてください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>SMS レポート</strong></p>
    </div>
    <p>SMS レポートには、配信率や直帰率など、SMS配信に関する詳細が表示されます。詳しくは、</br><a href="../../reporting/using/sms-report.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
</table>

## モバイルのトラブルシューティング {#mobile-troubleshooting}

次のページでは、Adobe Campaign Standardでモバイル配信を使用する際に発生する最も一般的な問題を解決する方法を説明します。

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>プッシュ通知に関するFAQ</strong></p>
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

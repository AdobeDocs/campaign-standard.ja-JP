---
title: Campaign Standardモバイルガイド
description: モバイルアプリケーションの設定方法や、プッシュ通知とアプリ内メッセージの作成方法など、Adobe Campaign Standardのモバイル配信の一般的なガイドラインについて詳しく説明します。
audience: channels
content-type: reference
topic-tags: mobile-guide
feature: Overview
role: User
level: Beginner
exl-id: d4e1b935-b21f-4a24-99ba-f455db0f7cfc
source-git-commit: afb988281f00dc17b484872259d44f51864d55f1
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 22%

---

# モバイルチャネルの概要 {#mobile-guide}

<table style="table-layout:fixed">
<tr>
<td><img src="assets/do-not-localize/config_push.png" width="60px"><p>プッシュ通知用にモバイルアプリケーションを設定する方法については、こちらをクリックしてください </br><a href="#configuration-push"></a></p></td>
<td><img src="assets/do-not-localize/config_inapp.png" width="60px"><p>アプリ内メッセージ用にモバイルアプリケーションを設定する方法を学ぶ </br><a href="#configuring-mobile-app"> ここをクリック </a></p></td>
</tr>
<tr>
<td><img src="assets/do-not-localize/push2.png" width="60px"><p>プッシュ通知の作成方法の詳細については、</br><a href="#create-push"> ここをクリック </a></p></td>
<td><img src="assets/do-not-localize/inapp.png" width="60px"><p>アプリ内メッセージの作成方法については </br><a href="#create-inapp"> ここをクリックしてください </a></p></td></tr>
</table>

## モバイル配信について {#about-mobile}

Adobe Campaignでは、様々なチャネルでパーソナライズされたメッセージを作成して送信し、専用のレポートでメッセージの効果を測定できます。

Adobe Campaign Standardを使用すると、次の 3 つの異なるチャネルを介してモバイル配信を送信できます。

* SMS。SMS メッセージについての節に記載されています。
* プッシュ通知（プッシュ通知についてセクションに表示）。
* アプリ内メッセージ。アプリ内メッセージについての節に記載されています。

## プッシュ通知用のモバイルアプリケーションの設定 {#configuration-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Adobe Experience Platform SDK を使用したモバイルアプリケーションの設定</strong></p>
    </div>
    <p>アプリ内メッセージとプッシュ通知を送信するには、Adobe Experience Platform SDK を活用してモバイルアプリケーションをAdobe Campaignで設定する必要があります。詳しくは、</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Campaign Standardプッシュ通知のペイロード構造について</strong></p>
    </div>
    <p>プッシュ通知がAdobe Campaign Standardからアプリに正常に送信された場合に、モバイルアプリケーションで受信されるペイロードの構造について詳しく説明します。詳しくは、</br><a href="../../administration/using/push-payload.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>ローカル通知トラッキングの実装</strong></p>
    </div>
    <p>ローカル通知トラッキングが正しく実装されていることを確認する方法について説明します。 詳しくは、</br><a href="../../administration/using/local-tracking.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>プッシュトラッキングの実装</strong></p>
    </div>
    <p>iOSとAndroidにプッシュ通知トラッキングが正しく実装されていることを確認する方法を説明します。詳しくは、</br><a href="../../administration/using/push-tracking.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
</table>

## アプリ内メッセージ用のモバイルアプリケーションの設定 {#configuring-mobile-app}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Adobe Experience Platform SDK を使用したモバイルアプリケーションの設定</strong></p>
    </div>
    <p>アプリ内メッセージとプッシュ通知を送信するには、Adobe Experience Platform SDK を活用してモバイルアプリケーションをAdobe Campaignで設定する必要があります。詳しくは、</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Adobe Experience Platform SDK を使用してサポートされるモバイルの使用例</strong></p>
    </div>
    <p>Adobe Experience Platform SDK を使用してAdobe Campaign Standardでサポートされるモバイルユースケースについて詳しく説明します。詳しくは、</br><a href="../../administration/using/supported-mobile-use-cases.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Adobe Campaign Standard のユースケースをサポートするタグルールの設定</strong></p>
    </div>
    <p>データ収集 UI でデータ要素とルールの作成を開始して、モバイルアプリケーションからAdobe Campaign Standardに PII およびその他のデータを送信するには、<a href="../../administration/using/configuring-rules-launch.md"><strong> ここをクリック </strong></a> します。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>ローカル通知トラッキングの実装</strong></p>
    </div>
    <p>ローカル通知トラッキングが正しく実装されていることを確認する方法について説明します。 詳しくは、</br><a href="../../administration/using/local-tracking.md"><strong>ここをクリック</strong></a>してください。</p>
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
    <p><a href="../../channels/using/preparing-and-sending-a-push-notification.md"><strong> こちら </strong></a> プッシュ通知を準備する方法と、ターゲットオーディエンスに送信する方法について説明します。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>プッシュ通知のカスタマイズ</strong></p>
    </div>
    <p>配信を微調整するために、Adobe Campaignでは、プッシュ通知をデザインする際に一連のオプションにアクセスできます。詳しくは、</br><a href="../../channels/using/customizing-a-push-notification.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>多言語プッシュ通知の作成</strong></p>
    </div>
    <p>ユーザーの優先言語および地域に基づいてメッセージを送信することで、プッシュ通知コンテンツをパーソナライズします。詳しくは、</br><a href="../../channels/using/creating-a-multilingual-push-notification.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Adobe Campaign Standardのプッシュ通知からの画像を表示</strong></p>
    </div>
    <p>iOS デバイスでAdobe Campaign プッシュ通知から画像を表示する方法については、<a href="../../administration/using/image-push-notification.md"><strong> こちら </strong></a> を参照してください。</p>
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
    <p><a href="../../channels/using/preparing-and-sending-an-in-app-message.md"><strong> こちら </strong></a> アプリ内メッセージの準備方法と、ターゲットオーディエンスへの送信方法について説明します。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>アプリ内メッセージのカスタマイズ</strong></p>
    </div>
    <p>配信を微調整するために、Adobe Campaignでは、アプリ内をデザインする際に、一連の高度なオプションにアクセスできます。詳しくは、</br><a href="../../channels/using/customizing-an-in-app-message.md"><strong>ここをクリック</strong></a>してください。</p>
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
    <p>アプリ内レポートは、アプリ内配信に関連する詳細を提供します。詳しくは、</br><a href="../../reporting/using/in-app-report.md"><strong>ここをクリック</strong></a>してください。</p>
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
    <p>SMS 配信の作成は、通常のメールの作成と非常に似ています。</br> 手順 <a href="../../channels/using/creating-an-sms-message.md"><strong> 詳細はこちら </strong></a> では、このチャネルに固有の設定について説明します。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>SMS メッセージのカスタマイズ
</strong></p>
    </div>
    <p>配信を微調整するために、Adobe Campaignでは、SMS メッセージのデザイン中に、一連の高度なオプションにアクセスできます。</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong> 詳しくは、ここをクリックしてください。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>受信 SMS の管理</strong></p>
    </div>
    <p>Campaign 経由で送信された SMS メッセージにプロファイルが返信した場合、自動的に送り返されるメッセージと実行するアクションを設定できます。ローカル通知メッセージタイプのカスタマイズ </br><a href="../../channels/using/managing-incoming-sms.md"><strong> 詳しくは、ここをクリックします。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>SMS レポート</strong></p>
    </div>
    <p>SMS レポートは、配信やバウンス率など、SMS 配信に関する詳細を提供します。詳しくは、</br><a href="../../reporting/using/sms-report.md"><strong>ここをクリック</strong></a>してください。</p>
    <br>
  </td>
</tr>
</table>

## モバイルのトラブルシューティング {#mobile-troubleshooting}

以下のページは、Adobe Campaign Standardでモバイル配信を使用する際に発生する最も一般的な問題を解決する際に役立ちます。

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

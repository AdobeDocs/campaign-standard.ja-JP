---
title: 指標の計算
description: 各指標の数式をリストして、レポートの結果を把握する。
page-status-flag: never-activated
uuid: dfbc9d7e-62db-4e77-bb8e-0ac826ec7333
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: about-reporting
discoiquuid: 45b11631-6b32-4074-8c8d-affd06407810
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 9%

---


# 指標の計算{#indicator-calculation}

>[!NOTE]
>
>大量の分析とリアルタイム分析をより適切に処理および管理するために、動的レポートでは、明確な数の予測に対して概算の集計を使用します。 近似集計オファーのメモリ使用量に制限があり、多くの場合、正確な計算よりも高速です。

次の表に、様々なレポートで使用されるインジケータのリストと、配信のタイプに応じたその計算式を示します。

## E メール配信 {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>ラベル</strong> <br /> </th> 
   <th> <strong>フィールド名</strong> <br /> </th> 
   <th> <strong>指標の計算式</strong> <br /> </th> 
   <th> <strong>コメント</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 無効なアカウント<br /> </td> 
   <td> @disabled<br /> </td> 
   <td> count(@failureReason=4)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> On denylist<br /> </td> 
   <td> @blacklisted<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Denylist rate<br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @ブラックリスト登録済み/@sent<br /> </td> 
   <td> レート計算の分母は、送信回数（配信済み+バウンス）に基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> バウンス数 + エラー数<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Bounce + Error rate<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> @bounces/@sent<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> クリック<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> count（@trackingUrlType=1または10または11）<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Click through rate<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@delivered<br /> </td> 
   <td> レート計算の分母は、[配信済み]にのみ基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Delivered rate<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivered/@sent<br /> </td> 
   <td> レート計算の分母は、送信回数（配信済み+バウンス）に基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> ハードバウンス<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2 AND @failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 直帰率<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> レート計算の分母は、送信回数（配信済み+バウンス）に基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> 無効なドメイン<br /> </td> 
   <td> @invalidDomain<br /> </td> 
   <td> count(@failureReason=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> メールボックス容量超過<br /> </td> 
   <td> @mailBoxFull<br /> </td> 
   <td> count(@failureReason=5)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> ミラーページ<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> レート計算の分母は、[配信済み]にのみ基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> Mirror page rate<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@delivered<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 未接続<br /> </td> 
   <td> @notConnected<br /> </td> 
   <td> count(@failureReason=6)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 開封数<br /> </td> 
   <td> @uniqueOpens<br /> </td> 
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2,3,6,10,11) - unique(@trackingUrlType=2))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @opens/@delived<br /> </td> 
   <td> レート計算の分母は、[配信済み]にのみ基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> 強制隔離<br /> </td> 
   <td> @quarantine<br /> </td> 
   <td> isQuarantine=true<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Quarantine rate<br /> </td> 
   <td> @rateQuarantine<br /> </td> 
   <td> @強制隔離/@sent<br /> </td> 
   <td> レート計算の分母は、送信回数（配信済み+バウンス）に基づきます。<br /> </td> 
  </tr>
  <tr> 
   <td> 却下<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Rejected rate<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @rejected/@sent<br /> </td> 
   <td> レート計算の分母は、送信回数（配信済み+バウンス）に基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> Processed/sent<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delivered + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Soft bounce<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failureType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Soft bounce rate<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> レート計算の分母は、送信回数（配信済み+バウンス）に基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> ユニーククリック数<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 個別クリック数は、ThetaSketchの概念を使用して計算されます。 For more on this, refer to this <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">example</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unique opens<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> unique(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 未到達 <br /> </td> 
   <td> @未到達<br /> </td> 
   <td> count(@failureReason=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 購読解除<br /> </td> 
   <td> @unsubscribes<br /> </td> 
   <td> count(@trackingUrlType=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unsubscribe rate<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@delivered<br /> </td> 
   <td> レート計算の分母は、[配信済み]にのみ基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不明なユーザー<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count(@failureReason=1)<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

## プッシュ通知配信 {#push-notification-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>ラベル</strong> <br /> </th> 
   <th> <strong>フィールド名</strong> <br /> </th> 
   <th> <strong>指標の計算式</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Processed/sent<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivered rate<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Bounce + Error rate<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 開封数<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opens/@delivered)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Unique opens<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> 一意の開きは、ThetaSketchの一意のRecipientIdの概念を使用して計算されます。 For more on this, refer to this <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">example</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> インプレッション<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> Unique impressions<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=表示))<br /> </td> 
  </tr> 
  <tr> 
   <td> クリック<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> ユニーククリック数<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 個別クリック数は、ThetaSketchの概念を使用して計算されます。 For more on this, refer to this <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">example</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Click through rate<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@delived)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## アプリ内配信 {#in-app-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>ラベル</strong> <br /> </th> 
   <th> <strong>フィールド名</strong> <br /> </th> 
   <th> <strong>指標の計算式</strong> <br /> </th> 
   <th> <strong>コメント</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Processed/sent<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
   <td> sent=delived<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
   <td> delived=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> インプレッション<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=表示)または@count(status=button 1 click + button 2 click + docsals)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unique impressions<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=表示))<br /> </td> 
   <td> キャンペーンプロファイル(inAppProfile) <span class="uicontrol"></span> ターゲットに基づく受信者ユーザーの場合は、user = template Idです。<br /> モバイルアプリ(inAppBroadcast) <span class="uicontrol">および</span> ターゲットユーザーのすべてのユーザーをモバイルプロファイル(inApp) <span class="uicontrol"></span> テンプレートに基づいてターゲットする場合は、user = MC Idまたはユーザー、モバイルアプリ、デバイスの一意の組み合わせを表す同等のユーザー。<br /> </td> 
  </tr> 
  <tr> 
   <td> In-App clicks <br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count(status=click)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 個別アプリ内クリック数<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count (status=clicks))<br /> </td> 
   <td> キャンペーンプロファイル(inAppProfile) <span class="uicontrol"></span> ターゲットに基づく受信者ユーザーの場合は、user = template Idです。<br /> モバイルアプリ(inAppBroadcast) <span class="uicontrol">および</span> ターゲットユーザーのすべてのユーザーをモバイルプロファイル(inApp) <span class="uicontrol"></span> テンプレートに基づいてターゲットする場合は、user = MC Idまたはユーザー、モバイルアプリ、デバイスの一意の組み合わせを表す同等のユーザー。<br /> </td> 
  </tr> 
  <tr> 
   <td> In-App click through rate<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> ボタン1またはボタン2の合計クリック数/合計インプレッション数*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> In-App dismissal<br /> </td> 
   <td> @解雇<br /> </td> 
   <td> @count (status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 個別のアプリ内課金<br /> </td> 
   <td> @uniqueejounce<br /> </td> 
   <td> @unique(@count (status=close))<br /> </td> 
   <td> キャンペーンプロファイル(inAppProfile) <span class="uicontrol"></span> ターゲットに基づく受信者ユーザーの場合は、user = template Idです。<br /> モバイルアプリ(inAppBroadcast) <span class="uicontrol">および</span> ターゲットユーザーのすべてのユーザーをモバイルプロファイル(inApp) <span class="uicontrol"></span> テンプレートに基づいてターゲットする場合は、user = MC Idまたはユーザー、モバイルアプリ、デバイスの一意の組み合わせを表す同等のユーザー。<br /> </td> 
  </tr> 
  <tr> 
   <td> In-App dismissal rate<br /> </td> 
   <td> @docsalate<br /> </td> 
   <td> 終了/合計インプレッション数*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>


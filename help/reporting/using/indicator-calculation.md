---
solution: Campaign Standard
product: campaign
title: 指標の計算
description: 各指標の数式をリストして、レポートの結果を把握する。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 10%

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
   <td> ブロックリスト<br /> </td> 
   <td> @ブラックリスト登録済み<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> ブロックリストレート<br /> </td> 
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
   <td> バウンス+エラー率<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> @bounces/@sent<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> クリック<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> count(@trackingUrlType=1 or 10 or 11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> クリックスルー率<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@delivered<br /> </td> 
   <td> レート計算の分母は配信済みのみに基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 配信率<br /> </td> 
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
   <td> ハードバウンス率<br /> </td> 
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
   <td> レート計算の分母は配信済みのみに基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> ミラーページ率<br /> </td> 
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
   <td> オープンレート<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @opens/@delivered<br /> </td> 
   <td> レート計算の分母は配信済みのみに基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> 強制隔離<br /> </td> 
   <td> @強制隔離<br /> </td> 
   <td> isQuarantine=true<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 強制隔離率<br /> </td> 
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
   <td> 却下レート<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @rejected/@sent<br /> </td> 
   <td> レート計算の分母は、送信回数（配信済み+バウンス）に基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> 処理済み/送信済み<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delivered + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> ソフトバウンス<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failureType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> ソフトバウンス率<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> レート計算の分母は、送信回数（配信済み+バウンス）に基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> ユニーククリック数<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 個別クリック数は、ThetaSketchの概念を使用して計算されます。 詳しくは、<a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">例</a><br />を参照してください。 </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 一意のオープン<br /> </td> 
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
   <td> 登録解除率<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@delived<br /> </td> 
   <td> レート計算の分母は配信済みのみに基づきます。<br /> </td> 
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
   <td> 処理済み/送信済み<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delived)<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信率<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> バウンス+エラー率<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 開封数<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> オープンレート<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opens/@delivered)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 一意のオープン<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> 一意の開きは、ThetaSketchの一意のRecipientIdの概念を使用して計算されます。 詳しくは、<a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">例</a><br />を参照してください。 </td> 
  </tr> 
  <tr> 
   <td> インプレッション<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=delived)<br /> </td> 
  </tr> 
  <tr> 
   <td> 一意のインプレッション数<br /> </td> 
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
   <td> 個別クリック数は、ThetaSketchの概念を使用して計算されます。 詳しくは、<a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">例</a><br />を参照してください。 </td> 
  </tr> 
  <tr> 
   <td> クリックスルー率<br /> </td> 
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
   <td> 処理済み/送信済み<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
   <td> sent=delivered<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delived)<br /> </td> 
   <td> delivered=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> インプレッション<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=表示)または@count(status=button 1 click + button 2 click + docsals)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 一意のインプレッション数<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=表示))<br /> </td> 
   <td> <span class="uicontrol">ターゲットユーザーのキャンペーンプロファイル(inAppProfile)</span>テンプレートに基づくユーザーの場合、user =受信者ID。<br /> モバイルアプリ(inAppBroadcast)のすべてのユーザー <span class="uicontrol">と、モバイルプロファイル(inApp)</span> テンプレートに基づく <span class="uicontrol">ターゲットユーザーを</span> ターゲットする場合は、user = MC Idまたは、ユーザー、モバイルアプリ、デバイスの一意の組み合わせを表す同等のユーザー。<br /> </td> 
  </tr> 
  <tr> 
   <td> アプリ内クリック数<br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count (status=click)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 個別アプリ内クリック数<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count (status=clicks))<br /> </td> 
   <td> <span class="uicontrol">ターゲットユーザーのキャンペーンプロファイル(inAppProfile)</span>テンプレートに基づくユーザーの場合、user =受信者ID。<br /> モバイルアプリ(inAppBroadcast)のすべてのユーザー <span class="uicontrol">と、モバイルプロファイル(inApp)</span> テンプレートに基づく <span class="uicontrol">ターゲットユーザーを</span> ターゲットする場合は、user = MC Idまたは、ユーザー、モバイルアプリ、デバイスの一意の組み合わせを表す同等のユーザー。<br /> </td> 
  </tr> 
  <tr> 
   <td> アプリ内クリックスルー率<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> ボタン1またはボタン2の合計クリック数/合計インプレッション数*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> アプリ内解雇<br /> </td> 
   <td> @empoince<br /> </td> 
   <td> @count (status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 個別のアプリ内課金は<br />を却下 </td> 
   <td> @uniqueejousence<br /> </td> 
   <td> @unique(@count (status=close))<br /> </td> 
   <td> <span class="uicontrol">ターゲットユーザーのキャンペーンプロファイル(inAppProfile)</span>テンプレートに基づくユーザーの場合、user =受信者ID。<br /> モバイルアプリ(inAppBroadcast)のすべてのユーザー <span class="uicontrol">と、モバイルプロファイル(inApp)</span> テンプレートに基づく <span class="uicontrol">ターゲットユーザーを</span> ターゲットする場合は、user = MC Idまたは、ユーザー、モバイルアプリ、デバイスの一意の組み合わせを表す同等のユーザー。<br /> </td> 
  </tr> 
  <tr> 
   <td> アプリ内解雇率<br /> </td> 
   <td> @docsalrate<br /> </td> 
   <td> 終了/合計インプレッション数*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>


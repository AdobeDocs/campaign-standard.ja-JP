---
title: 指標の計算
description: 各指標の数式のリストを使用して、レポートの結果を把握します。
page-status-flag: 非活性化の
uuid: dfbc9d7e-62db-4e77-bb8e-0ac826ec7333
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: レポート
content-type: 参照
topic-tags: 報告に関する
discoiquuid: 45b11631-6b32-4074-8c8d-affd06407810
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 指標の計算{#indicator-calculation}

以下の表に、様々なレポートで使用されるインジケーターのリストと、配信タイプに応じた計算式を示します。

## E メール配信 {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>ラベル</strong><br /> </th> 
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
   <td> ブラックリスト<br /> </td> 
   <td> @blacklisted<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> ブラックリスト記載率<br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklisted/@sent<br /> </td> 
   <td> レート計算の分母は、送信回数（配信済み+バウンス）に基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> バウンス+エラー<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 直帰率+エラー率<br /> </td> 
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
   <td> クリックスルー率<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@delivered<br /> </td> 
   <td> レート計算の分母は、[配信済み]のみに基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 配送率<br /> </td> 
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
   <td> レート計算の分母は、[配信済み]のみに基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> ミラーページレート<br /> </td> 
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
   <td> @opens<br /> </td> 
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2,3,6,10,11) - unique(@trackingUrlType=2))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> オープン率<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @opens/@delivered<br /> </td> 
   <td> レート計算の分母は、[配信済み]のみに基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> 強制隔離<br /> </td> 
   <td> @quarantine<br /> </td> 
   <td> isQuarantine=true<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 検疫率<br /> </td> 
   <td> @rateQuarantine<br /> </td> 
   <td> @quarantine/@sent<br /> </td> 
   <td> レート計算の分母は、送信回数（配信済み+バウンス）に基づきます。<br /> </td> 
  </tr> 
  <tr> 
   <td> 拒否<br /> </td> 
   <td> @拒否<br /> </td> 
   <td> count(@failureReason=20)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 却下<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 却下率<br /> </td> 
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
   <td> 個別クリック数<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 個別クリック数は、ThetaSketchの概念を使用して計算されます。<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 個別オープン<br /> </td> 
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
   <td> @unsubscribe<br /> </td> 
   <td> count(@trackingUrlType=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 登録解除率<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribe/@delivered<br /> </td> 
   <td> レート計算の分母は、[配信済み]のみに基づきます。<br /> </td> 
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
   <th> <strong>ラベル</strong><br /> </th> 
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
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> 配送率<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 直帰率+エラー率<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 開封数<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> オープン率<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opens/@delivered)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 個別オープン<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> 個別オープンは、ThetaSketchの一意のRecipientIdの概念を使用して計算されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> インプレッション<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> 個別インプレッション数<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> クリック<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> 個別クリック数<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 個別クリック数は、ThetaSketchの概念を使用して計算されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> クリックスルー率<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@delivered)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## アプリ内配信 {#in-app-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>ラベル</strong><br /> </th> 
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
   <td> @count(status=delivered)<br /> </td> 
   <td> delivered=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> インプレッション<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=view)または@count(status=button 1 click + button 2 click + dosics)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 個別インプレッション数<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> キャンペ <span class="uicontrol">ーンプロファイル(inAppProfile)テンプレートに基づくTargetユーザーの場合</span> 、user = Recipient Id。<br /> Mobileアプリ( <span class="uicontrol">inAppBroadcast)と</span> Targetユーザーのすべてのユーザーを、モバイルプロファイル(inApp)テンプレートに基づいてターゲットにする場合は <span class="uicontrol"></span> 、ユーザー= MC IDまたはユーザー、モバイルアプリ、デバイスの一意の組み合わせを表す同等のユーザー。<br /> </td> 
  </tr> 
  <tr> 
   <td> アプリ内クリック数 <br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count (status=click)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 個別アプリ内クリック数<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count (status=clicks))<br /> </td> 
   <td> キャンペ <span class="uicontrol">ーンプロファイル(inAppProfile)テンプレートに基づくTargetユーザーの場合</span> 、user = Recipient Id。<br /> Mobileアプリ( <span class="uicontrol">inAppBroadcast)と</span> Targetユーザーのすべてのユーザーを、モバイルプロファイル(inApp)テンプレートに基づいてターゲットにする場合は <span class="uicontrol"></span> 、ユーザー= MC IDまたはユーザー、モバイルアプリ、デバイスの一意の組み合わせを表す同等のユーザー。<br /> </td> 
  </tr> 
  <tr> 
   <td> アプリ内クリックスルー率<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> ボタン1またはボタン2の合計クリック数/合計インプレッション数*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> アプリ内却下<br /> </td> 
   <td> @解雇<br /> </td> 
   <td> @count (status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 個別のアプリ内投稿の却下<br /> </td> 
   <td> @uniquejousince<br /> </td> 
   <td> @unique(@count (status=close))<br /> </td> 
   <td> キャンペ <span class="uicontrol">ーンプロファイル(inAppProfile)テンプレートに基づくTargetユーザーの場合</span> 、user = Recipient Id。<br /> Mobileアプリ( <span class="uicontrol">inAppBroadcast)と</span> Targetユーザーのすべてのユーザーを、モバイルプロファイル(inApp)テンプレートに基づいてターゲットにする場合は <span class="uicontrol"></span> 、ユーザー= MC IDまたはユーザー、モバイルアプリ、デバイスの一意の組み合わせを表す同等のユーザー。<br /> </td> 
  </tr> 
  <tr> 
   <td> アプリ内解雇率<br /> </td> 
   <td> @domsalrate<br /> </td> 
   <td> クローズインプレッション数合計*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>


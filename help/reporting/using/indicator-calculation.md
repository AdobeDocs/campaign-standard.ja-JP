---
title: 指標の計算
description: 各指標の式のリストを使用して、レポートの結果を把握できます。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 47cc11d7-89e8-4d1c-9638-5f66a53cef7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 7%

---

# 指標の計算{#indicator-calculation}

>[!NOTE]
>
>大量の分析とリアルタイム分析をより適切に処理および管理するために、動的レポートでは個別カウントの予測に概算集計を使用します。 概算集計は、制限付きメモリ使用量を提供し、多くの場合、正確な計算よりも高速です。

次の表に、様々なレポートで使用される指標のリストと、配信タイプに応じた計算式を示します。

## メール配信 {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>ラベル</strong> <br /> </th> 
   <th> <strong>フィールド名</strong> <br /> </th> 
   <th> <strong>指標の計算式</strong> <br /> </th> 
   <th> <strong> コメント </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 無効なアカウント<br /> </td> 
   <td> @disabled<br /> </td> 
   <td> count （@failureReason=4） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> On^ブロックリスト<br /> </td> 
   <td> @blacklisted<br /> </td> 
   <td> count （@failureReason=8, @failureType=2） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> ブロックリスト率 <br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklisted/@sent<br /> </td> 
   <td> レート計算の分母は、送信済みカウント （配信済み+ バウンス）に基づいています。<br /> </td> 
  </tr> 
  <tr> 
   <td> バウンス + エラー <br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count （@status=2） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> バウンス率+ エラー率 <br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> @bounces/@sent<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> クリック <br /> </td> 
   <td> @clicks<br /> </td> 
   <td> count （@trackingUrlType=1 または 10 または 11） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> クリックスルー率 <br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@delivered<br /> </td> 
   <td> レート計算の分母は、配信済みのみに基づいています。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count （@status=1） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 配信率 <br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivered/@sent<br /> </td> 
   <td> レート計算の分母は、送信済みカウント （配信済み+ バウンス）に基づいています。<br /> </td> 
  </tr> 
  <tr> 
   <td> ハードバウンス<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count （@failureType=2 および@failureReason=8） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> ハードバウンス率 <br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> レート計算の分母は、送信済みカウント （配信済み+ バウンス）に基づいています。<br /> </td> 
  </tr> 
  <tr> 
   <td> 無効なドメイン<br /> </td> 
   <td> @invalidDomain<br /> </td> 
   <td> count （@failureReason=2） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> メールボックス容量超過 <br /> </td> 
   <td> @mailBoxFull<br /> </td> 
   <td> count （@failureReason=5） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> ミラーページ <br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count （@trackingUrlType=6） <br /> </td> 
   <td> レート計算の分母は、配信済みのみに基づいています。<br /> </td> 
  </tr> 
  <tr> 
   <td> ミラーページ率 <br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@delivered<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 接続されていません <br /> </td> 
   <td> @notConnected<br /> </td> 
   <td> count （@failureReason=6） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 開封数<br /> </td> 
   <td> @uniqueOpens<br /> </td> 
   <td> count （@trackingUrlType=2 + unique （@trackingUrlType=1,2,3,6,10,11） - unique （@trackingUrlType=2）） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 開封率 <br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @opens/@delivered<br /> </td> 
   <td> レート計算の分母は、配信済みのみに基づいています。<br /> </td> 
  </tr> 
  <tr> 
   <td> 強制隔離 <br /> </td> 
   <td> @quarantine<br /> </td> 
   <td> isQuarantine=true<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 強制隔離率 <br /> </td> 
   <td> @rateQuarantine<br /> </td> 
   <td> @quarantine/@sent<br /> </td> 
   <td> レート計算の分母は、送信済みカウント （配信済み+ バウンス）に基づいています。<br /> </td> 
  </tr>
  <tr> 
   <td> 却下<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count （@failureReason=20, @failureType=2） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 却下率 <br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @rejected/@sent<br /> </td> 
   <td> レート計算の分母は、送信済みカウント （配信済み+ バウンス）に基づいています。<br /> </td> 
  </tr> 
  <tr> 
   <td> 処理済み/送信済み <br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delivered + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> ソフトバウンス <br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count （@failureType=1） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> ソフトバウンス率 <br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> レート計算の分母は、送信済みカウント （配信済み+ バウンス）に基づいています。<br /> </td> 
  </tr> 
  <tr> 
   <td> ユニーククリック数 <br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> ユニーククリック数は、ThetaSketch の概念を使用して計算されます。 詳しくは、この <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match"> 例 </a>.<br /> を参照してください。 </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> ユニーク開封数 <br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> 一意（@trackingUrlType=1,2,3,6,10,11） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 未到達 <br /> </td> 
   <td> @未到達<br /> </td> 
   <td> count （@failureReason=3） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 購読解除 <br /> </td> 
   <td> @unsubscribes<br /> </td> 
   <td> count （@trackingUrlType=3） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 登録解除率 <br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@delivered<br /> </td> 
   <td> レート計算の分母は、配信済みのみに基づいています。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不明なユーザー<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count （@failureReason=1） <br /> </td> 
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
   <td> 処理済み/送信済み <br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count （status=sent） <br /> </td> 
  </tr> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count （status=delivered） <br /> </td> 
  </tr> 
  <tr> 
   <td> 配信率 <br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> （@delivered/@sent）*100<br /> </td> 
  </tr> 
  <tr> 
   <td> バウンス率+ エラー率 <br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> （@delivered/@sent）*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 開封数<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count （status=open） <br /> </td> 
  </tr> 
  <tr> 
   <td> 開封率 <br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> （@opens/@delivered）*100<br /> </td> 
  </tr> 
  <tr> 
   <td> ユニーク開封数 <br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> ユニーク開封数は、一意の RecipientIds の ThetaSketch の概念を使用して計算されます。 詳しくは、この <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match"> 例 </a>.<br /> を参照してください。 </td> 
  </tr> 
  <tr> 
   <td> インプレッション数 <br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count （status=delivered） <br /> </td> 
  </tr> 
  <tr> 
   <td> ユニークインプレッション数 <br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique （@count （status=view）） <br /> </td> 
  </tr> 
  <tr> 
   <td> クリック <br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count （status=interact） <br /> </td> 
  </tr> 
  <tr> 
   <td> ユニーククリック数 <br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> ユニーククリック数は、ThetaSketch の概念を使用して計算されます。 詳しくは、この <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match"> 例 </a>.<br /> を参照してください。 </td> 
  </tr> 
  <tr> 
   <td> クリックスルー率 <br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> （@interact/@delivered）*100<br /> </td> 
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
   <th> <strong> コメント </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 処理済み/送信済み <br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count （status=sent） <br /> </td> 
   <td> 送信済み=配信済み <br /> </td> 
  </tr> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count （status=delivered） <br /> </td> 
   <td> 配信済み=送信済み <br /> </td> 
  </tr> 
  <tr> 
   <td> インプレッション数 <br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count （status=view）または@count （status=button 1 click + button 2 click + dismissals） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> ユニークインプレッション数 <br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique （@count （status=view）） <br /> </td> 
   <td> <span class="uicontrol">Campaign プロファイル（inAppProfile） </span> テンプレートに基づく Target ユーザーの場合は、ユーザー=受信者 ID。<br /> <span class="uicontrol"> モバイルアプリ（inAppBroadcast）のすべてのユーザーをターゲットにする） </span> および <span class="uicontrol"> モバイルプロファイル（inApp） </span> テンプレートに基づく Target ユーザー、ユーザー= MC ID またはユーザー、モバイルアプリ、デバイスの一意の組み合わせを表す同等の識別子。<br /> </td> 
  </tr> 
  <tr> 
   <td> アプリ内クリック数 <br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count （ステータス=クリック） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> ユニークアプリ内クリック数 <br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique （@count （ステータス=クリック数）） <br /> </td> 
   <td> <span class="uicontrol">Campaign プロファイル（inAppProfile） </span> テンプレートに基づく Target ユーザーの場合は、ユーザー=受信者 ID。<br /> <span class="uicontrol"> モバイルアプリ（inAppBroadcast）のすべてのユーザーをターゲットにする） </span> および <span class="uicontrol"> モバイルプロファイル（inApp） </span> テンプレートに基づく Target ユーザー、ユーザー= MC ID またはユーザー、モバイルアプリ、デバイスの一意の組み合わせを表す同等の識別子。<br /> </td> 
  </tr> 
  <tr> 
   <td> アプリ内クリックスルー率 <br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> ボタン 1 またはボタン 2 の合計クリック数/合計インプレッション数*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> アプリ内解除 <br /> </td> 
   <td> @dismissal<br /> </td> 
   <td> @count （ステータス=閉じる） <br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> ユニークアプリ内解除数 <br /> </td> 
   <td> @uniquedismissal<br /> </td> 
   <td> @unique （@count （status=close）） <br /> </td> 
   <td> <span class="uicontrol">Campaign プロファイル（inAppProfile） </span> テンプレートに基づく Target ユーザーの場合は、ユーザー=受信者 ID。<br /> <span class="uicontrol"> モバイルアプリ（inAppBroadcast）のすべてのユーザーをターゲットにする） </span> および <span class="uicontrol"> モバイルプロファイル（inApp） </span> テンプレートに基づく Target ユーザー、ユーザー= MC ID またはユーザー、モバイルアプリ、デバイスの一意の組み合わせを表す同等の識別子。<br /> </td> 
  </tr> 
  <tr> 
   <td> アプリ内解除率 <br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> 総クローズ/総インプレッション数*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

---
title: Campaign Standardの廃止および削除された機能
description: このページには、Adobe Campaign Standardの廃止および削除された機能が一覧表示されます。
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 490908e5fe0810c0a07c73fef5040ddb42983019

---


# 廃止および削除された機能 {#deprecated-and-removed-features}

アドビは、製品の機能を評価し続けて、より最新の代替手段に置き換えるべき旧機能を特定し、全体的な顧客価値を向上させ、常に後方互換性を慎重に考慮します。

キャンペーン標準機能の差し迫った削除/置き換えについて伝えるには、次のルールが適用されます。

* 廃止のお知らせが先に来ます。 非推奨の機能は既存のユーザーに対して引き続き使用できますが、それ以上の拡張やドキュメント化は行われません。
* 非推奨の機能が削除されるのは、以下のリリース以降です。 削除の実際の目標日は、このページで発表されています。

このプロセスにより、お客様は、実際に削除される前に、新しいバージョンまたは廃止された機能の後継バージョンに実装を適合させるために、少なくとも1つのリリースサイクルを提供できます。

>[!NOTE]
>Adobe Campaign Standardのリリースと新機能については、リリースノートに記載さ [れています](../../rn/using/release-notes.md)。


## 廃止された機能 {#deprecated-features}

ここでは、最新のCampaign Standardリリースで非推奨とマークされている機能について説明します。

一般に、将来のリリースで削除される予定の機能は、代替機能として提供される非推奨の機能に設定されます。 これらの機能は、新しいCampaign Standardのお客様はご利用いただけなくなったり、新しい実装には使用しないでください。 また、製品ドキュメントからも削除されます。

お客様には、現在の導入で機能を利用しているかどうかを確認し、提供されている代替機能を使用するように実装を変更する計画を立てることをお勧めします。 目標の削除日を参照して、環境とプロジェクトの更新を計画してください。

<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK v4でのプッシュ通知</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 20.1リリース以降、SDK v4は非推奨となります。 <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">詳細情報</a></p><br/>
   <p>Adobe Experience Platform Mobile SDK <a href="https://aep-sdks.gitbook.io/docs/"></a> （旧称v5）は、今後のAdobe Experience cloudの機能のみをサポートする予定です。</p></br>
     <p>削除予定日：2020年9月30日</p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK for Campaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Creative SDKは廃止されました。 その結果、Campaign Standardの電子メールでCreative SDKが提供するImage Editionは、20.1リリース以降で廃止されます。</p></br>
  <p> 削除予定日：2020年3月 — Campaign 20.2リリース</p>
   </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>プライバシーリクエスト — キャンペーンAPIとインターフェイス</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Campaign 19.4リリース以降、アクセス要求と削除要求に対するCampaign APIとインターフェイスの使用は廃止されました。 アドビのプ <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">ライバシーコアサービスを使用しま</a>す。</p></br>
   <p>Campaign Standardの「プライバ <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">シー管理」も参照してください</a>。</p>
  <p> 削除予定日：2020年7月 — Campaign 20.5リリース</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>電子メールデザイン — レガシー電子メールエディター</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Campaign 19.0リリース以降、レガシー電子メールエディターは廃止されました。 新しい電 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">子メールデザイナーを使用して</a> 、電子メールコンテンツを作成し、パーソナライズします。 </p></br>
   <p>この節では、新 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">しいエディター用に</a> 、電子メールテンプレートを適応させる方法について説明します。</p></br>
  <p> 削除予定日：2020年10月 — Campaign 20.6リリース</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>ユーザーとセキュリティ — 地理的単位</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>18.7リリース以降、地理的単位は廃止されました。 組織単位と地理的単位は、Campaignでは同じ構成要素です。 ユーザーは、組織単位のみを使用して、ユーザー権限/データアクセス階層を作成する必要があります。 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">詳細情報</a>新しいキャンペーン標準インスタンスと、地理的単位が作成されていない既存のインスタンスでは、18.7リリースからこの機能を実装できないことに注意してください。</p>
   </td> 
  </tr> 
 </tbody> 
</table>


## 互換性の終了 {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Internet Explorer 11</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe CampaignとAdobe Experience cloudは、Microsoft Internet Explorer 11のサポートを2019年春から、Campaign 19.2リリースに終了しました。 Microsoft edgeまたはサポートされている別のブラウザーに切り替えてください。 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/getting-started/discovering-the-interface/compatible-browsers.html">詳細情報</a></p>
   </td> 
  </tr> 
 </tbody> 
</table>

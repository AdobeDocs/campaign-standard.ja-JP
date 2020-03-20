---
title: キャンペーン標準の廃止および削除された機能
description: このページには、Adobe Campaign Standardの廃止および削除された機能の一覧が表示されます。
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
source-git-commit: d8ad3801dba50e357c21a7551e897e0e2c5aedc5

---


# 廃止および削除された機能 {#deprecated-and-removed-features}

アドビは、製品の機能を評価し続けて、より最新の代替手段に置き換える必要のある旧機能を特定し、全体的な顧客価値を向上させ、常に下位互換性を慎重に考慮します。

キャンペーン標準の機能の差し迫った削除/置き換えについて伝えるため、次のルールが適用されます。

* 廃止のお知らせが先に来ます。 非推奨の機能は引き続き既存のユーザーが使用できますが、それ以上の拡張やドキュメント化は行われません。
* 非推奨の機能が削除されるのは、以下のリリースでは早くても可能です。 削除の実際の目標日は、このページで発表されています。

このプロセスにより、お客様は、実際に削除される前に、新しいバージョンまたは廃止された機能の後継バージョンに実装を適合させるために、少なくとも1つのリリースサイクルを提供します。

>[!NOTE]
>Adobe Campaign Standardのリリースと新機能は、リリースノートに記載さ [れています](../../rn/using/release-notes.md)。


## 廃止された機能 {#deprecated-features}

この節では、最新のCampaign Standardリリースで非推奨とマークされている機能と機能を示します。

一般に、将来のリリースで削除される予定の機能は、代替機能と共に非推奨に設定されます。 これらの機能は、新しいキャンペーン標準のお客様は使用できなくなったり、新しい実装には使用しないでください。 また、製品ドキュメントからも削除されます。

お客様は、現在の導入で機能を利用しているかどうかを確認し、提供されている代替機能を使用するように導入を変更する計画を立てることをお勧めします。 お使いの環境とプロジェクトの更新を計画するには、削除の目標日を参照してください。

<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK v4を使用したプッシュ通知</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 20.1リリース以降、SDK v4は非推奨となります。 <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">詳細情報</a></p><br/>
   <p>Adobe Experience Platform Mobile SDK <a href="https://aep-sdks.gitbook.io/docs/"></a> （旧称v5）は、今後のAdobe Experience Cloudの機能のみをサポートする予定です。</p></br>
     <p>削除の対象日：2020年9月30日</p>
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
   <td> <p>Adobe Creative SDKは廃止されました。 その結果、Campaign Standardの電子メールでCreative SDKを使用したImage Editionは、20.1リリース以降で廃止されます。</p></br>
  <p> 削除の対象日：2020年3月 — Campaign 20.2リリース</p>
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
   <td> <p>Campaign 19.4リリース以降、アクセスおよび削除の要求に対するCampaign APIとインターフェイスの使用は廃止されました。 2ステップのプロファイルの削除は使用できません。 アドビのプ <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">ライバシーコアサービスを使用</a>。</p></br>
   <p>キャンペーン標準 <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">の「プライバシー管理」も参照してくださ</a>い。</p>
  <p> 削除の対象日：2020年7月 — Campaign 20.5リリース</p>
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
   <td> <p>Campaign 19.0リリース以降、レガシーの電子メールエディターは廃止されました。 新しい電 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">子メールデザイナーを使用して</a> 、電子メールコンテンツを作成し、パーソナライズします。 </p></br>
   <p>この節を読 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">んで</a> 、新しいエディター用に電子メールテンプレートを適応させる方法を学びます。</p></br>
  <p> 削除の対象日：2020年10月 — Campaign 20.6リリース</p>
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
   <td> <p>18.7リリース以降、地理単位は廃止されました。 組織単位と地理的単位は、Campaignでは同じ構成要素です。 ユーザは、組織単位のみを使用して、ユーザ権限/データアクセス階層を構築する必要があります。 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">詳細情報</a>新しいキャンペーン標準のインスタンスと、地理的単位が作成されていない既存のインスタンスは、18.7リリースからこの機能を実装できないことに注意してください。</p>
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
   <td> <p>Adobe CampaignとAdobe Experience Cloudは、Microsoft Internet Explorer 11のサポートを2019年春から、Campaign 19.2リリースから終了しました。 Microsoft Edgeまたは他のサポートされているブラウザーに切り替えてください。 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/getting-started/discovering-the-interface/compatible-browsers.html">詳細情報</a></p>
   </td> 
  </tr> 
 </tbody> 
</table>

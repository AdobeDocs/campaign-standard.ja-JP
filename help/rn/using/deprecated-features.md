---
title: Campaign Standardの廃止および削除された機能
description: このページリストは、Mac OSの機能を廃止し、削除しました。Adobe Campaign標準の機能は
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
source-git-commit: c35468d7c9a3177d755dad2a9ab2e09510d680fa

---


# 廃止および削除された機能 {#deprecated-and-removed-features}

アドビは、製品の機能を評価し続けて、より最新の代替手段に置き換える必要のある旧機能を特定し、全体的な顧客価値を向上させ、常に下位互換性を慎重に考慮します。

差し迫ったCampaign Standard機能の削除/交換を伝えるため、次のルールが適用されます。

* 廃止のお知らせが先に来ます。 非推奨の機能は引き続き既存のユーザーが使用できますが、それ以上の拡張やドキュメント化は行われません。
* 非推奨の機能が削除されるのは、以下のリリースでは早くても可能です。 実際のターゲット削除日は、このページで発表されています。

このプロセスにより、お客様は、実際に削除される前に、新しいバージョンまたは廃止された機能の後継バージョンに実装を適合させるために、少なくとも1つのリリースサイクルを提供します。

>[!NOTE]
>Adobe Campaign標準リリースと新機能については、リリースノートを参 [照してください](../../rn/using/release-notes.md)。


## 廃止された機能 {#deprecated-features}

この節では、リストの最新リリースで非推奨とマークされている機能についてCampaign Standardします。

一般に、将来のリリースで削除される予定の機能は、代替機能と共に非推奨に設定されます。 これらの機能は、新しいCampaign Standardのお客様は利用できなくなったか、新しい実装には使用しないでください。 また、製品ドキュメントからも削除されます。

お客様は、現在の導入で機能を利用しているかどうかを確認し、提供されている代替機能を使用するように導入を変更する計画を立てることをお勧めします。 ターゲットの削除日を参照して、それに応じて環境とプロジェクトの更新を計画してください。

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
     <p>
     <em>ターゲットの削除日：2020年9月30日</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>プライバシーリクエスト —キャンペーンAPIとインターフェイス</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>キャンペーン19.4リリース以降、アクセス要求と削除要求に対するキャンペーンAPIとインターフェイスの使用は非推奨となりました。 2段階のプロファイル削除は使用できません。 アドビのプ <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">ライバシーコアサービスを使用</a>。</p></br>
   <p>「プライバシー管 <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">理」も参照してください</a>。</p>
  <p> 
  <em>ターゲットの削除日：2020年7月 —キャンペーン20.5リリース </em></p>
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
   <td> <p>キャンペーン19.0リリース以降、レガシーの電子メールエディターは廃止されました。 新しい電 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">子メールデザイナーを使用して</a> 、電子メールコンテンツを作成し、パーソナライズします。 </p></br>
   <p>この節を読 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">んで</a> 、新しいエディター用に電子メールテンプレートを適応させる方法を学びます。</p></br>
  <p> 
  <em>ターゲットの削除日：2020年10月 —キャンペーン20.6リリース </em></p>
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
   <td> <p>18.7リリース以降、地理単位は廃止されました。 組織単位と地理的単位は、同じ構成キャンペーンです。 ユーザは、組織単位のみを使用して、ユーザ権限/データアクセス階層を構築する必要があります。 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">詳細情報</a>新しいCampaign Standardインスタンスと、地理的な単位が作成されていない既存のインスタンスは、18.7リリースからこの機能を実装できないことに注意してください。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## 削除された機能 {#removed-features}

この節では、リストから削除された機能に関するCampaign Standardを示します。

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK forCampaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Creative SDKは廃止されました。 その結果、Campaign Standard電子メールのCreative SDKを利用したImage Editionは、キャンペーン20.2リリース以降では使用できなくなりました。</p></br>
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
   <td> <p>Adobe CampaignおよびAdobe Experience Cloudは、Microsoft Internet Explorer 11のサポートを2019年春から、キャンペーン19.2リリースに廃止しました。 Microsoft Edgeまたは他のサポートされているブラウザーに切り替えてください。 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/getting-started/discovering-the-interface/compatible-browsers.html">詳細情報</a></p>
   </td> 
  </tr> 
 </tbody> 
</table>

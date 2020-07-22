---
title: Campaign Standardの廃止/削除された機能
description: このページリストはAdobe Campaign Standardの機能を廃止および削除しました。
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
source-git-commit: 2d4b1ba38a7aa33d1fff3415d71080e370cb80f4
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 38%

---


# 廃止および削除された機能 {#deprecated-and-removed-features}

アドビは、製品の機能を評価し続けて、より新しい代替手段に置き換えるべき旧機能を特定し、全体的な顧客の価値を向上させ、常に後方互換性を慎重に考慮します。

Campaign Standard機能の差し迫った取り外し/交換を伝えるため、次の規則が適用されます。

* まず、廃止予定のお知らせが来ます。非推奨（廃止予定）の機能は引き続き既存のユーザーに提供できますが、それ以上の機能強化やドキュメント化はおこなわれません。
* 非推奨（廃止予定）の機能は、以下のリリースで最も早く削除されます。削除の実際のターゲット日は、このページで発表されます。

このプロセスにより、顧客は、実際に削除する前に、新しいバージョンや非推奨（廃止予定）の機能の後継バージョンに実装を適応させるために、少なくとも 1 つのリリースサイクルを提供できます。

>[!NOTE]
>Adobe Campaign Standard releases and new capabilities are listed in the [Release Notes](../../rn/using/release-notes.md).


## 廃止された機能 {#deprecated-features}

この節では、最新のCampaign Standardリリースで非推奨とマークされている機能と機能についてリストします。

一般に、将来のリリースで削除される予定の機能は、まず非推奨に設定され、代わりの機能も提供されます。これらの機能は、新しい Campaign Standard の顧客は利用できなくなるか、新しい実装には使用するべきではないものです。また、製品ドキュメントからも削除されます。

顧客は現在のデプロイメントで機能を利用しているかどうかを確認し、提供される代替機能を使用するように実装を変更する計画を立てるようお勧めします。ターゲットの削除のバージョンを参照して、環境とプロジェクトの更新を計画してください。

<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK v4を使用したプッシュ通知</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 20.1リリース以降、SDK v4は非推奨となります。 <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">詳細情報</a>。</p><br/>
   <p><a href="https://aep-sdks.gitbook.io/docs/">Adobe Experience PlatformモバイルSDK</a> （旧称v5）は、今後のAdobe Experience Cloudの機能のみをサポートします。</p></br>
     <p>
     <em>Targetの削除日： 2020年9月30日</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>プライバシー要求 —キャンペーンAPIとインターフェイス</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>キャンペーン19.4リリース以降、アクセス要求および削除要求に対するキャンペーンAPIおよびインターフェイスの使用は廃止されました。 2段階のプロファイルの削除は使用できません。 アド <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">ビのプライバシーコアサービスを使用します</a>。</p></br>
   <p>「Campaign Standardの <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">プライバシー管理</a>」も参照してください。</p>
  <p> 
  <em>削除予定日：2021 年</em></p>
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
   <td> <p>キャンペーン19.0リリース以降、レガシー電子メールエディターは非推奨となりました。 新しい電子メ <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">ールデザイナーを使用して</a> 、電子メールコンテンツを作成し、パーソナライズします。 </p></br>
   <p>この節では <a href="https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/designing-content/building-email-content/using-existing-content.html"></a> 、新しいエディター用に電子メールテンプレートを適応させる方法について説明します。</p></br>
  <p> 
  <em>削除予定日：2021 年</em></p>
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
   <td> <p>18.7リリース以降、地理単位は非推奨となりました。 組織単位と地理的単位は、キャンペーンでは同じ構成です。 ユーザーは、組織単位(OU)のみを使用して、ユーザー権限/データアクセス階層を作成する必要があります。 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">詳細情報</a>。新しいCampaign Standardインスタンスと、地理単位が作成されていない既存のインスタンスには、18.7リリースからこの機能を実装することはできません。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Removed Features {#removed-features}

このセクションでは、Campaign Standard から削除された機能を一覧表示します。

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK forCampaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Creative SDKは廃止されました。 その結果、Campaign Standardの電子メールでCreative SDKを使用するImage Editionは、キャンペーン20.2リリース以降では使用できなくなります。</p></br>
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
   <td> <p>Adobe CampaignとAdobe Experience Cloudは、Microsoft Internet Explorer 11の2019年春以降、キャンペーン19.2リリースのサポートを終了しました。 Microsoft Edgeまたはサポートされている別のブラウザーに切り替えてください。 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/about-configuration-guidelines.html#compatible-browsers">詳細情報</a>。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

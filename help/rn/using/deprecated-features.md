---
solution: Campaign Standard
product: campaign
title: Campaign Standard の非推奨（廃止予定）および削除された機能
description: このページリストは、Adobe Campaign Standard の非推奨（廃止予定）および削除された機能です。
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
feature: Overview
role: User
level: Beginner
exl-id: 03797137-c01c-48dc-b25b-8e72741abb04
source-git-commit: bb964907851b11f8cc247425024f6e7c828aed5d
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 66%

---

# 廃止および削除された機能 {#deprecated-and-removed-features}

アドビは、製品の機能を評価し続けて、より新しい代替手段に置き換えるべき旧機能を特定し、全体的な顧客の価値を向上させ、常に後方互換性を慎重に考慮します。

Campaign Standard 機能の差し迫った削除／置換を伝達するため、次のルールが適用されます。

* まず、廃止予定のお知らせが来ます。非推奨（廃止予定）の機能は引き続き既存のユーザーに提供できますが、それ以上の機能強化やドキュメント化はおこなわれません。
* 非推奨（廃止予定）の機能は、以下のリリースで最も早く削除されます。実際の削除予定日は、このページで発表されます。

このプロセスにより、顧客は、実際に削除する前に、新しいバージョンや非推奨（廃止予定）の機能の後継バージョンに実装を適応させるために、少なくとも 1 つのリリースサイクルを提供できます。

>[!NOTE]
>Adobe Campaign Standard のリリースと新機能は、[リリースノート](../../rn/using/release-notes.md)に一覧表示されています。


## 非推奨（廃止予定）の機能 {#deprecated-features}

この節では、最新の Campaign Standard リリースで非推奨とマークされている機能が記載されています。

一般に、将来のリリースで削除される予定の機能は、まず非推奨に設定され、代わりの機能も提供されます。これらの機能は、新しい Campaign Standard の顧客は利用できなくなるか、新しい実装には使用するべきではないものです。また、製品ドキュメントからも削除されます。

顧客は現在のデプロイメントで機能を利用しているかどうかを確認し、提供される代替機能を使用するように実装を変更する計画を立てるようお勧めします。ターゲットの削除バージョンを参照し、それに応じて環境やプロジェクトの更新を計画してください。

<table> 
 <thead> 
  <tr> 
   <th> <strong>Audience Destinationsサービスとの統合</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Campaign Standard21.3リリースより、Audience Destinationsサービスとの統合は非推奨（廃止予定）となります。 </p>
   <p>新しい実装の場合、Audience DestinationsサービスをAdobe Campaign Standardと統合できなくなりました。 ただし、CampaignとAdobe Experience Platformをソースと宛先を使用して統合することはできます。 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html?lang=en">詳細情報</a>。</p>
     <em>削除予定：2022 年</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connectorとの統合</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Campaign Standard21.3リリースより、Adobe Experience Platform Data Connectorとの統合は非推奨（廃止予定）となります。 </p>
   <p>新しい実装の場合、Adobe Experience Platform Data ConnectorをAdobe Campaign Standardと統合できなくなりました。 ただし、CampaignとAdobe Experience Platformをソースと宛先を使用して統合することはできます。 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html?lang=en">詳細情報</a>。</p>
     <em>削除予定：2022 年</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>


<table> 
 <thead> 
  <tr> 
   <th> <strong>E メールデザイン - レガシー E メールエディター</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Campaign 19.0 リリース以降、レガシー E メールエディターは非推奨となりました。 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">Campaign Eメールデザイナー</a>を使用して、Eメールコンテンツを作成し、パーソナライズします。 </p></br>
   <p><a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">この節</a>で、新しいエディター用に E メールテンプレートを適応させる方法を説明しています。</p></br>
  <p> 
  <em>削除予定：2022 年</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>ユーザーとセキュリティ - 地理的単位</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Campaign 18.7リリースより、地理的単位は非推奨（廃止予定）となります。 組織単位と地理的単位は、Campaign では同じ構成です。 ユーザーは、組織単位のみを使用して、ユーザー権限／データアクセス階層を作成する必要があります。 <a href="https://helpx.adobe.com/jp/campaign/standard/administration/using/organizational-units.html">詳細情報</a>。新しい Campaign Standard インスタンスと、地理的単位が作成されていない既存のインスタンスには、18.7 リリースからこの機能を実装することはできません。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## 削除された機能 {#removed-features}

この節では、Campaign Standard から削除された機能を一覧表示します。



<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK v4 を使用したプッシュ通知</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Campaign 20.1リリースより、SDK v4は非推奨（廃止予定）となります。 <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">詳細情報</a>。</p><br/>
   <p><a href="https://aep-sdks.gitbook.io/docs/">Adobe Experience Platform Mobile SDK</a>（旧称v5）は、今後のAdobe Experience Cloudの機能のみをサポートするようになりました。</p>
   <p>2021年8月31日以降は、引き続きバージョン4のSDKをダウンロードして使用できますが、カスタマーケアのサポートやフォーラムへのアクセスはありません。</p>
   <p>SDK v4からAdobe Experience Platform Mobile SDK <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html">に移行する方法については、このページ</a>を参照してください。</p></br>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>プライバシーリクエスト - Campaign API とインターフェイス</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>21.2 リリース以降、アクセス要求および削除要求に対する Campaign API およびインターフェイスの使用は廃止されます。2 段階のプロファイルの削除は使用できません。 <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe Privacy Core Service</a> を使用します。</p></br>
   <p><a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=en">プライバシーリクエストの管理</a>も参照してください。</p>
  </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
 <tr> 
   <th> <strong>予測件名行</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 2021年4月以降、予測件名行機能は廃止されます。</p><br/>
   <p>AIを利用したEメール機能を活用して、過去のエンゲージメント指標に基づいて、開封率、最適な送信時間、および予想される解約を分析し、予測することをお勧めします。 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/preparing-and-testing-messages/predictive.html">詳細情報</a></p></br>
     </td> 
  </tr> 
  </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Experience Cloud トリガーを使用した傾向スコア</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p><b>傾向スコア</b>は、Adobe Experience Cloud トリガーから廃止されました。 その結果、このオプションは Adobe Campaign Standard から削除されました。 エンリッチメントスキーマで傾向スコアの値が古くならないようにするには、スキーマを更新して最新の変更を取得し、既存のトリガーを再公開することをお勧めします。 詳しくは、<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html">Campaign でのトリガーの公開</a>を参照してください。
</p></br>
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
   <td> <p>[!DNL Adobe Creative SDK] は廃止されました。その結果、Campaign Standard の E メール内の [!DNL Creative SDK] を使用した画像エディションは、Campaign 20.2 リリース以降では使用できなくなりました。</p></br>
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
   <td> <p>Adobe Campaign と Adobe Experience Cloud は、2019 年春から Campaign 19.2 リリース以降、Microsoft Internet Explorer 11 のサポートを終了しました。 Microsoft Edge またはサポートされている別のブラウザーに切り替えてください。 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/about-configuration-guidelines.html">詳細情報</a>。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

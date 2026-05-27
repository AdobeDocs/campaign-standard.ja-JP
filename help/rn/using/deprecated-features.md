---
title: Campaign Standard の非推奨（廃止予定）および削除された機能
description: このページリストは、Adobe Campaign Standard の非推奨（廃止予定）および削除された機能です。
feature: Overview
role: User
level: Beginner
exl-id: 03797137-c01c-48dc-b25b-8e72741abb04
TQID: https://experienceleague.adobe.com/S430SyqHAam2JE4LQppJUy3xuEdS6lw1qGQE9viVCS8
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
  - id: b631758a-142d-425f-b9aa-f756d85cb979
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
subfeature_v2:
  - id: c8da4fdd-eb94-4751-a43c-f82733fb2d6e
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 1045
ht-degree: 50%

---

# 廃止および削除された機能 {#deprecated-and-removed-features}

アドビは、製品の機能を評価し続けて、より新しい代替手段に置き換えるべき旧機能を特定し、全体的な顧客の価値を向上させ、常に後方互換性を慎重に考慮します。

Campaign Standard 機能の差し迫った削除／置換を伝達するため、次のルールが適用されます。

* まず、廃止予定のお知らせが来ます。 非推奨（廃止予定）の機能は引き続き既存のユーザーに提供できますが、それ以上の機能強化やドキュメント化はおこなわれません。
* 非推奨（廃止予定）の機能は、以下のリリースで最も早く削除されます。 実際の削除予定日は、このページで発表されます。

このプロセスにより、顧客は、実際に削除する前に、新しいバージョンや非推奨（廃止予定）の機能の後継バージョンに実装を適応させるために、少なくとも 1 つのリリースサイクルを提供できます。

>[!NOTE]
>Adobe Campaign Standard のリリースと新機能は、[リリースノート](../../rn/using/release-notes.md)に一覧表示されています。


## 非推奨（廃止予定）の機能 {#deprecated-features}

この節では、最新の Campaign Standard リリースで非推奨とマークされている機能が記載されています。

一般に、将来のリリースで削除される予定の機能は、まず非推奨に設定され、代わりの機能も提供されます。 これらの機能は、新しい Campaign Standard の顧客は利用できなくなるか、新しい実装には使用するべきではないものです。 また、製品ドキュメントからも削除されます。

顧客は現在のデプロイメントで機能を利用しているかどうかを確認し、提供される代替機能を使用するように実装を変更する計画を立てるようお勧めします。 ターゲットの削除バージョンを参照し、それに応じて環境やプロジェクトの更新を計画してください。



<table> 
 <thead> 
  <tr> 
   <th> <strong> モバイルアプリケーション用SDK V4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Experience Platform Mobile バージョン 4 SDKのサポートは、2021年8月31日（PT）をもって終了しました。 Adobe Campaign Standardで引き続きこのレガシーバージョンのSDKを使用している場合は、2024年6月の終わりまでにAdobe Experience Platform SDK <strong>で実装を更新する必要があります</strong>。 </p></br>
   <p>実装を適応させ、最新のExperience Platform SDKに移行する方法については、<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html">この記事</a>を参照してください。</p></br>
   <p><strong>注意</strong>: SDK V4は、2024年6月末以降、Campaign Standardではサポートされなくなります。</p>
  </td> 
  </tr> 
 </tbody> 
</table>




<table> 
 <thead> 
  <tr> 
   <th> <strong>メールデザイン - レガシーメールエディター</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Campaign 19.0 リリース以降、レガシーメールエディターは非推奨となりました。 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">Campaign Email Designer</a>を使用して、メールコンテンツを作成およびパーソナライズします。 </p></br>
   <p><a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">この節</a>で、新しいエディター用にメールテンプレートを適応させる方法を説明しています。</p></br>
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
   <td> <p>Campaign 18.7 リリース以降、地理的単位は非推奨（廃止予定）です。 組織単位と地理的単位は、Campaign では同じ構成です。 ユーザーは、組織単位のみを使用して、ユーザー権限／データアクセス階層を作成する必要があります。 <a href="https://helpx.adobe.com/jp/campaign/standard/administration/using/organizational-units.html">詳細情報</a>。 新しい Campaign Standard インスタンスと、地理的単位が作成されていない既存のインスタンスには、18.7 リリースからこの機能を実装することはできません。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## 削除された機能 {#removed-features}

この節では、Campaign Standard から削除された機能を一覧表示します。

<table> 
 <thead> 
  <tr> 
   <th> <strong> オーディエンス宛先サービスとの統合</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Campaign Standard 21.3 リリース以降、Audience Destinations サービスとの統合は推奨されません。  が削除されました。</p>
   <p>新しい実装では、Audience Destinations サービスをAdobe Campaign Standardと統合できなくなります。 ただし、CampaignとAdobe Experience Platformは、ソースと宛先から統合できます。 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html">詳細情報</a>。</p>
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
   <td> <p> Campaign Standard 21.3 リリース以降、Adobe Experience Platform Data Connectorとの統合は推奨されません。  が削除されました。</p>
   <p>新しい実装では、Adobe Experience Platform Data ConnectorとAdobe Campaign Standardを統合できなくなります。 ただし、CampaignとAdobe Experience Platformは、ソースと宛先から統合できます。 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html">詳細情報</a>。</p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK v4 を使用したプッシュ通知</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Campaign 20.1 リリース以降、SDK v4は非推奨（廃止予定）です。 が削除されました。 <a href="https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html?lang=ja">詳細情報</a>。</p><br/>
   <p><a href="https://developer.adobe.com/client-sdks/documentation/">Adobe Experience Platform モバイルSDK</a> （以前はv5と呼ばれていました）は、今後のAdobe Experience Cloud機能と機能のみをサポートするようになりました。</p>
   <p>2021年8月31日以降、お客様は引き続きバージョン 4 SDKをダウンロードして使用できますが、カスタマーケアのサポートやフォーラムへのアクセスはありません。</p>
   <p>SDK v4からAdobe Experience Platform Mobile SDK <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html">に移行する方法については、このページ </a>を参照してください。</p></br>
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
   <td> <p>21.2 リリース以降、アクセス要求および削除要求に対する Campaign API およびインターフェイスの使用は廃止されます。 2段階のプロファイル削除は使用できなくなりました。 <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service">Adobe Privacy Core Service</a>を使用します。</p></br>
   <p><a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html">プライバシーリクエストの管理</a>も参照してください。</p>
  </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
 <tr> 
   <th> <strong>予測件名</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> 2021年4月より、予測件名の機能は廃止されました。</p><br/>
   <p>そこで、AIを活用した電子メール機能を利用して、開封率、最適な送信時間、過去のエンゲージメント指標にもとづく解約の可能性などを分析、予測することをお勧めします。 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/preparing-and-testing-messages/predictive.html">詳細情報</a></p></br>
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
   <td> <p>[!DNL Adobe Creative SDK] は廃止された。 これにより、Campaign 20.2 リリース以降、Campaign Standard メールの[!DNL Creative SDK]による画像編集は利用できなくなります。</p></br>
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

---
solution: Campaign Standard
product: campaign
title: 'Adobe Campaign統合を通じた電子メールのデザイン '
description: 電子メールデザイナーでAdobe Campaign統合を使用して電子メールをデザインする方法を確認します。
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 6%

---


# マルチソリューション電子メールデザイン {#multi-solution-email-design}

Adobe Campaignオファーには、複数の電子メールオーサリングオプションがあります。 Dreamweaverなどのソリューションを使用して、電子メールコンテンツを編集し、電子メールデザイナーでレスポンシブメッセージを作成できます。 また、Adobe Experience Managerとコンテンツを電子メールで送信し、Adobe Campaign Standardの電子メールに使用することもできます。

## Dreamweaver{#editing-content-in-dreamweaver}でのコンテンツの編集

Adobe Campaign StandardとDreamweaverの統合により、Dreamweaverのインターフェイスで電子メールのコンテンツを編集できます。 レスポンシブ電子メールコンテンツをデザインし開発する際に、Dreamweaverの強力なインターフェイスにアクセスできます。

* **双方向同期**

   ある製品で編集が行われると、別の製品でリアルタイムに更新されます。 Dreamweaverでテキストの色を変更する場合、編集を行うとすぐに、テキストの色がキャンペーンでライブになります。 また、Dreamweaverまたはキャンペーンでコードを選択した場合、行番号が同じなので、2つの商品の間に選択範囲が残るので、コード内で特定のものを探す場合に非常に役立ちます。

* **Dreamweaver を使用した Adobe Campaign へのローカルイメージのアップロード**

   Dreamweaver内で電子メールを作成または編集する場合は、デスクトップまたはローカルマシンから画像を選択するだけで済みます。 Dreamweaverはこれを常に許可していますが、Dreamweaverとキャンペーンが接続されている場合、ローカルファイルはすぐにAdobe Campaignサーバにアップロードされます。コンテンツの変更に応じて、手動で画像をアップロードする必要はありません。 また、最新の画像は常にキャンペーンで表示されます。

* **Dreamweaverの追加キャンペーンパーソナライゼーション**

   電子メール開発者は、`[[FIRSTNAME_PLACEHOLDER]]`のようなテキストを追加したり、データモデルのテーブルの構文を調べたりする必要がなくなりました。 Dreamweaverのキャンペーンツールバーは、キャンペーンインスタンスのデータモデルに直接接続します。 つまり、名から住所までのようなパーソナライゼーション用の任意のデータを取り込むことができます。 コンテンツブロックをキャンペーン内に作成した場合は、コンテンツブロックを直接Dreamweaverに引き出すこともできます。

この機能の詳細は、[こちら](https://helpx.adobe.com/jp/dreamweaver/using/working-with-dreamweaver-and-campaign.html)からアクセス可能なDreamweaver文書を参照してください。

![](assets/do-not-localize/how-to-video.png) [動画でこの機能を確認する](#video)

## Experience Manager{#editing-content-in-experience-manager}でのコンテンツの編集

電子メールコンテンツはExperience Managerで編集でき、Adobe Campaign Standardの1つまたは複数の電子メールメッセージに使用できます。 [このドキュメント](../../integrating/using/integrating-with-experience-manager.md)を参照してください。

## 製品リスト{#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="製品リストの使用"
>abstract="製品リストでは、データ収集を参照して電子メールコンテンツに表示できます。"

製品リストでは、電子メールコンテンツ内の1つ以上のデータコレクションを参照できます。 これらのリストは、トランザクション電子メールで使用できます。 この機能の専用のセクションは、[ここ](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)で入手できます。

## 電子メールデザインオプションの比較{#email-design-options-comparison}

Adobe Campaignオファーには、複数の電子メールオーサリングオプションがあります。 次の表に、それぞれの主な可能性、利点、制限を示します。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Email Designer <br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>開始の空白の電子メール</strong><br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポート<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTMLを書き込む</strong><br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポート<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTMLを更新</strong><br /> </td> 
   <td> HTMLコンポーネント内のみ<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポート<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>基本的なパーソナライゼーション</strong><br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポート<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>高度なパーソナライゼーション</strong><br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>配達確認/プレビュー</strong><br /> </td> 
   <td> サポート<br /> </td> 
   <td> キャンペーン<br />のAEM<br />配達確認のプレビュー </td> 
   <td> キャンペーン<br />のプレビューと配達確認 </td> 
  </tr> 
  <tr> 
   <td> <strong>製品リスト</strong><br /> </td> 
   <td> 電子メールトランザクションメッセージでサポート<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>利点</strong><br /> </td> 
   <td> 
     <p> — ドラッグアンドドロップ操作で簡単に電子メールを作成</p>
     <p> — レガシーコンテンツエディターと同様の機能</p>
     <p> — フラグメントを含む再利用可能なコンテンツ</p>
  </td> 
   <td> 
     <p> — 電子メール内のWebサイトのアセットの再利用</p>
     <p> — 電子メールコンテンツにExperience Managerの機能を活用</p>
    </td> 
   <td> 
    <p> — 開発者が電子メールを直接コーディングする機能</p>
    <p> — 双方向の同期</p>
    <p>-Dreamweaverでオフライン編集し、後で同期</p>
    <p>-Dreamweaver経由でAdobe Campaignに画像をアップロード</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>制限事項</strong><br /> </td> 
   <td> 
     <p> — フラグメント内に条件付きコンテンツがない</p>
     <p>-Experience Managerフラグメントを使用できません</p>
  </td> 
   <td> 
     <p> — 高度なパーソナライゼーションは導入が困難</p>
     <p> — テストをAdobe Campaignで送信する必要がある</p>
  </td> 
   <td> 動的コンテンツがサポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>オーディエンス</strong><br /> </td> 
   <td> ドラッグ&amp;ドロップ機能と組み合わせてHTMLコンポーネントを柔軟に使用したいマーケター<br /> </td> 
   <td> パーソナライゼーションの低い標準的な電子メールテンプレートを使用したいExperience Managerが既に使用されています<br /> </td> 
   <td> 電子メールコンテンツをコード化し、Adobe Campaign<br />と直接統合したい開発者 </td> 
  </tr> 
  <tr> 
   <td> <strong>詳細情報</strong><br /> </td> 
   <td> <a href="../../designing/using/designing-content-in-adobe-campaign.md">電子メールデザイナーについて</a>を参照してください。<br /> </td> 
   <td> <a href="../../integrating/using/integrating-with-experience-manager.md">Experience Managerとの統合</a>を参照してください。<br /> </td> 
   <td> <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaverとキャンペーン</a>を見て、この<a href="#video">ビデオ</a>を見てください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## チュートリアルビデオ {#video}

このビデオでは、Dreamweaverを使用してAdobe Campaign Standard向けのコンテンツを作成および編集する方法を紹介します。

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

追加のCampaign Standardハウツービデオは[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)で参照できます。

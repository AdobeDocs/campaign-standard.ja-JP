---
solution: Campaign Standard
product: campaign
title: 'Adobe Campaign統合を使用したEメールのデザイン '
description: EメールデザイナーでAdobe Campaign統合を使用してEメールをデザインする方法を説明します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Eメールデザイン
role: User
level: Intermediate
exl-id: d5c72f69-68a2-4523-956f-f265ae79b470
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 8%

---

# マルチソリューション電子メールデザイン {#multi-solution-email-design}

Adobe Campaignでは、複数のeメールオーサリングオプションが用意されています。 Dreamweaverなどのソリューションを使用して、EメールデザイナーでEメールコンテンツを編集し、レスポンシブメッセージを作成できます。 Adobe Experience ManagerでコンテンツをEメールで送信し、Adobe Campaign StandardのEメールで使用することもできます。

## Dreamweaverでのコンテンツの編集 {#editing-content-in-dreamweaver}

Adobe Campaign StandardとDreamweaverの統合により、DreamweaverインターフェイスでEメールのコンテンツを編集できます。 Dreamweaverの強力なインターフェイスを利用して、レスポンシブなEメールコンテンツをデザインし、開発することができます。

* **双方向同期**

   1つの製品で編集がおこなわれるたびに、他の製品でリアルタイムに更新されます。 Dreamweaverでテキストの色を変更する場合は、編集を行うとすぐに、Campaignでテキストの色がライブになります。 また、DreamweaverまたはCampaignでコードを選択する場合、行番号が同じなので、選択は2つの製品の間に残るので、コード内で特定のものを探す際に非常に役立ちます。

* **Dreamweaver を使用した Adobe Campaign へのローカルイメージのアップロード**

   Dreamweaver内でEメールを作成または編集する際には、デスクトップまたはローカルマシンから画像を選択するだけで済みます。 Dreamweaverでは常にこの操作が許可されていますが、DreamweaverとCampaignが接続されると、ローカルファイルがAdobe Campaignサーバーに直ちにアップロードされます。コンテンツの変更に合わせて画像を手動でアップロードする必要はありません。 さらに、最新の画像が常にCampaignで公開されます。

* **DreamweaverでのCampaignパーソナライゼーションの追加**

   電子メール開発者は、`[[FIRSTNAME_PLACEHOLDER]]`のようなテキストを追加したり、データモデルのテーブルの構文を調べたりする必要がなくなりました。 DreamweaverのCampaignツールバーは、Campaignインスタンスのデータモデルに直接接続します。 つまり、名から住所など、パーソナライゼーションに必要なデータを取り込むことができます。 Campaign内でコンテンツブロックを作成した場合は、それらを直接Dreamweaverに取り込むこともできます。

この機能について詳しくは、Dreamweaverのドキュメントを参照してください。[こちら](https://helpx.adobe.com/jp/dreamweaver/using/working-with-dreamweaver-and-campaign.html)からアクセスできます。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

## Experience Manager内のコンテンツの編集 {#editing-content-in-experience-manager}

Eメールのコンテンツは、Experience Managerで編集し、Adobe Campaign Standardで1つまたは複数のEメールメッセージに使用できます。 [このドキュメント](../../integrating/using/integrating-with-experience-manager.md)を参照してください。

## 製品リスト {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="製品リストの使用"
>abstract="製品リストを使用すると、データ収集を参照してEメールコンテンツに表示できます。"

製品リストでは、Eメールコンテンツ内の1つ以上のデータコレクションを参照できます。 これらのリストはトランザクションEメールで使用できます。 この機能の専用のセクションは、[ここ](../../designing/using/using-product-listings.md)から入手できます。

## Eメールデザインオプションの比較 {#email-design-options-comparison}

Adobe Campaignでは、複数のeメールオーサリングオプションが用意されています。 次の表に、それぞれの主な可能性、利点、制限を示します。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> 電子メールデザイナー<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>空白の電子メールを開始</strong><br /> </td> 
   <td> サポート対象<br /> </td> 
   <td> サポート対象<br /> </td> 
   <td> サポート対象<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTMLを書き込む</strong><br /> </td> 
   <td> サポート対象<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポート対象<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTMLを更新</strong><br /> </td> 
   <td> HTMLコンポーネント内のみ<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポート対象<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>基本的なパーソナライゼーション</strong><br /> </td> 
   <td> サポート対象<br /> </td> 
   <td> サポート対象<br /> </td> 
   <td> サポート対象<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>高度なパーソナライゼーション</strong><br /> </td> 
   <td> サポート対象<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>配達確認/プレビュー</strong><br /> </td> 
   <td> サポート対象<br /> </td> 
   <td> AEM<br /> Campaignの配達確認でのプレビュー<br /> </td> 
   <td> Campaignでのプレビューと配達確認<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>製品リスト</strong><br /> </td> 
   <td> Eメールトランザクションメッセージでサポート<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>利点</strong><br /> </td> 
   <td> 
     <p> — ドラッグ&amp;ドロップ操作によるEメール作成が容易</p>
     <p> — レガシーコンテンツエディターと似た機能</p>
     <p> — フラグメントを含む再利用可能なコンテンツ</p>
  </td> 
   <td> 
     <p>- Webサイトのアセットを電子メールで再利用する</p>
     <p>- EメールコンテンツのExperience Managerの機能を活用</p>
    </td> 
   <td> 
    <p> — 開発者が電子メールを直接コード化する機能</p>
    <p> — 双方向同期</p>
    <p>- Dreamweaverでオフラインで編集し、後で同期する</p>
    <p>- Dreamweaverを使用したAdobe Campaignへの画像のアップロード</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>制限事項</strong><br /> </td> 
   <td> 
     <p> — フラグメント内に条件付きコンテンツがない</p>
     <p>-Experience Managerフラグメントの使用は不可</p>
  </td> 
   <td> 
     <p> — 高度なパーソナライゼーションは実装が困難</p>
     <p>- Adobe Campaignでテストを送信する必要がある</p>
  </td> 
   <td> 動的コンテンツがサポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>オーディエンス</strong><br /> </td> 
   <td> ドラッグ&amp;ドロップ機能と組み合わせてHTMLコンポーネントを柔軟に使用したいマーケター<br /> </td> 
   <td> パーソナライゼーションの少ない標準のEメールExperience Managerを使用したいマーケターは既に使用しています。<br /> </td> 
   <td> Eメールコンテンツをコーディングし、Adobe Campaign<br />と直接統合する開発者 </td> 
  </tr> 
  <tr> 
   <td> <strong>詳細情報</strong><br /> </td> 
   <td> <a href="../../designing/using/designing-content-in-adobe-campaign.md">Eメールデザイナーについて</a>.<br />を参照してください。 </td> 
   <td> <a href="../../integrating/using/integrating-with-experience-manager.md">Experience Managerとの統合</a>を参照してください。<br /> </td> 
   <td> <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaverとキャンペーン</a>を参照し、この<a href="#video">ビデオ</a>を見てください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## チュートリアルビデオ {#video}

このビデオでは、Dreamweaverを使用してAdobe Campaign Standardのコンテンツを作成および編集する方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

追加のCampaign Standardハウツービデオは[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)からご覧いただけます。

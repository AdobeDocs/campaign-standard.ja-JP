---
title: Adobe Campaignとの連携による電子メールのデザイン
description: Adobe Campaignとの連携による電子メールのデザイン方法を、メールDesignerでご確認ください。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d5c72f69-68a2-4523-956f-f265ae79b470
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 5%

---

# マルチソリューションのメールデザイン {#multi-solution-email-design}

Adobe Campaignには、メール作成オプションがいくつかあります。 Dreamweaverなどのソリューションを使用して、メールコンテンツを編集し、メールDesignerでレスポンシブメッセージを作成できます。 また、Adobe Experience Managerでコンテンツを電子メールで送信し、Adobe Campaign Standardの電子メールで使用することもできます。

## Dreamweaverでのコンテンツの編集 {#editing-content-in-dreamweaver}

Adobe Campaign StandardとDreamweaverの連携により、Dreamweaverのインターフェイスで電子メールのコンテンツを編集できます。 Dreamweaverの強力なインターフェイスを利用して、レスポンシブなメールコンテンツをデザインおよび制作できます。

* **双方向同期**

  一方の製品で編集を行うと、もう一方の製品でリアルタイムに更新されます。 Dreamweaverでテキストの色を変更する場合は、その編集を行うと、すぐにCampaignでテキストの色がライブになります。 さらに、DreamweaverまたはCampaignでコードを選択する場合、行番号は同じであるため、2つの製品間で選択範囲が残ります。これは、コード内の特定の項目を探す場合に非常に便利です。

* **Dreamweaverを通じてAdobe Campaignにローカル画像をアップロード**

  Dreamweaver内で電子メールを作成または編集する場合は、デスクトップまたはローカルマシンから画像を選択するだけです。 Dreamweaverでは常に、この操作が可能ですが、DreamweaverとCampaignが接続されている場合、ローカルファイルはすぐにAdobe Campaign サーバーにアップロードされます。コンテンツの変更に応じて画像を手動でアップロードする必要はありません。 さらに、最新の画像が常にCampaignに反映されます。

* **DreamweaverでのCampaign パーソナライゼーションの追加**

  メール開発者の場合、`[[FIRSTNAME_PLACEHOLDER]]`などのテキストを追加したり、データモデルのテーブルの構文を検索したりする必要はありません。 DreamweaverのCampaign ツールバーは、Campaign インスタンスのデータモデルに直接接続されます。 つまり、パーソナライズしたいデータを「名」から「アドレス」などに取り込むことができます。 Adobe Campaign内でコンテンツブロックを作成した場合は、それらのコンテンツブロックをDreamweaverに直接取り込むこともできます。

この機能について詳しくは、[こちら](https://helpx.adobe.com/jp/dreamweaver/using/working-with-dreamweaver-and-campaign.html)からアクセス可能なDreamweaver ドキュメントを参照してください。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

## Experience Managerでのコンテンツの編集 {#editing-content-in-experience-manager}

メールコンテンツは、Experience Managerで編集し、Adobe Campaign Standardの1つまたは複数のメールメッセージに使用できます。 [このドキュメント](../../integrating/using/integrating-with-experience-manager.md)を参照してください。

## 製品リスト {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="製品リストの使用"
>abstract="製品リストを使用すると、データ収集を参照し、メールコンテンツに表示できます。"

製品リストを使用すると、メールコンテンツ内の1つ以上のデータコレクションを参照できます。 これらのリストは、トランザクションメールで利用できます。 この機能の専用セクションは[こちら](../../designing/using/using-product-listings.md)で利用できます。

## メールデザインオプションの比較 {#email-design-options-comparison}

Adobe Campaignには、メール作成オプションがいくつかあります。 それぞれの主な可能性、メリット、制限事項を次の表に示します。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> E メールデザイナー<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>空のメールを開始</strong><br /> </td> 
   <td> サポートされている<br /> </td> 
   <td> サポートされている<br /> </td> 
   <td> サポートされている<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTMLの書き込み</strong><br /> </td> 
   <td> サポートされている<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポートされている<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTMLを更新</strong><br /> </td> 
   <td> HTML コンポーネント <br />内のみ </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポートされている<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>基本的なパーソナライゼーション </strong><br /> </td> 
   <td> サポートされている<br /> </td> 
   <td> サポートされている<br /> </td> 
   <td> サポートされている<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>高度なパーソナライゼーション </strong><br /> </td> 
   <td> サポートされている<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> プルーフ/プレビュー</strong><br /> </td> 
   <td> サポートされている<br /> </td> 
   <td> AEM<br /> Proof in Campaign<br />でのプレビュー </td> 
   <td> Campaign<br />でのプレビューとプルーフ </td> 
  </tr> 
  <tr> 
   <td> <strong>製品リスト </strong><br /> </td> 
   <td> メールのトランザクションメッセージでサポートされています<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> メリット </strong><br /> </td> 
   <td> 
     <p>- ドラッグ&amp;ドロップ操作による容易なメール作成</p>
     <p>- レガシーコンテンツエディターに似た機能</p>
     <p>- フラグメント付きの再利用可能なコンテンツ</p>
  </td> 
   <td> 
     <p>- メールでweb サイトからアセットを再利用する</p>
     <p>- メールコンテンツにExperience Managerの力を活用</p>
    </td> 
   <td> 
    <p> – 開発者が直接メールをコーディングする機能</p>
    <p> – 双方向同期</p>
    <p>- Dreamweaverでオフラインを編集し、後で同期</p>
    <p>- Dreamweaverを介したAdobe Campaignへの画像のアップロード</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>制限事項</strong><br /> </td> 
   <td> 
     <p>- フラグメント内に条件付きコンテンツはない</p>
     <p>- Experience Manager フラグメントの使用はできません</p>
  </td> 
   <td> 
     <p> – 高度なパーソナライゼーションは実装が困難</p>
     <p>- Adobe Campaignでテストを行う必要がある</p>
  </td> 
   <td> 動的コンテンツはサポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>オーディエンス</strong><br /> </td> 
   <td> HTML コンポーネントとドラッグ&amp;ドロップ機能を組み合わせて柔軟に使用したいマーケター<br /> </td> 
   <td> 既にExperience Managerを使用しているマーケターで、パーソナライズされた内容の少ない標準メールテンプレートを使用したい場合<br /> </td> 
   <td> メールの内容をコーディングし、Adobe Campaignと直接統合したい開発者<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>詳細を見る</strong><br /> </td> 
   <td> メール Designerについて<a href="../../designing/using/designing-content-in-adobe-campaign.md">を参照してください</a>。<br /> </td> 
   <td> <a href="../../integrating/using/integrating-with-experience-manager.md">Experience Managerとの統合</a>を参照してください。<br /> </td> 
   <td> <a href="https://helpx.adobe.com/jp/dreamweaver/using/working-with-dreamweaver-and-campaign.html">DreamweaverとCampaign</a>を参照し、この<a href="#video">動画</a>をご覧ください。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## チュートリアルビデオ {#video}

このビデオでは、Dreamweaverを使用してAdobe Campaign Standardのコンテンツを作成および編集する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/37614?quality=12&captions=jpn)

その他のCampaign Standardのハウツー動画は[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)でご覧いただけます。

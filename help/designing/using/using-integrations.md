---
title: Adobe Campaign統合を使用したメールのデザイン
description: メールDesignerのAdobe Campaign統合を通じてメールをデザインする方法について説明します。
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

# マルチソリューションの電子メールの設計 {#multi-solution-email-design}

Adobe Campaignには、複数のメール作成オプションが用意されています。 Dreamweaverなどのソリューションを使用して、メールコンテンツを編集し、メールDesignerでレスポンシブメッセージを作成できます。 また、Adobe Experience Managerでコンテンツをメールで送信し、Adobe Campaign Standardのメールで使用することもできます。

## Dreamweaverのコンテンツの編集 {#editing-content-in-dreamweaver}

Adobe Campaign StandardとDreamweaverの統合により、Dreamweaver インターフェイスでメールのコンテンツを編集できます。 Dreamweaverの強力なインターフェイスにアクセスして、レスポンシブなメールコンテンツをデザインおよび開発できます。

* **双方向同期**

  ある製品で編集が行われると、別の製品でリアルタイムに更新されます。 Dreamweaverのテキストの色を変更する場合は、編集を行うとすぐに、テキストの色が Campaign に表示されます。 さらに、Dreamweaverまたは Campaign でコードを選択した場合、行番号が同じなので、2 つの商品間に選択範囲が残ります。これは、コード内で特定の要素を検索する場合に非常に便利です。

* **Dreamweaverを使用したAdobe Campaignへのローカル画像のアップロード**

  Dreamweaver内でメールを作成または編集する際に、デスクトップまたはローカルマシンから画像を選択するだけです。 Dreamweaverでは常にこれを行うことが許可されていますが、Dreamweaverと Campaign が接続されると、ローカルファイルがAdobe Campaign サーバーにすぐにアップロードされます。コンテンツの変更に合わせて画像を手動でアップロードする必要はありません。 さらに、最新の画像が常に Campaign に公開されるようにします。

* **Dreamweaverでの Campaign パーソナライゼーションの追加**

  メール開発者は、`[[FIRSTNAME_PLACEHOLDER]]` のようなテキストを追加したり、データモデルのテーブルの構文を検索したりする必要がなくなりました。 Dreamweaverの Campaign ツールバーは、Campaign インスタンスのデータモデルに直接接続します。 つまり、名前（名）からアドレスなど、パーソナライゼーションに必要な任意のデータを取り込むことができます。 Campaign 内でコンテンツブロックを作成した場合は、それらをDreamweaverに直接取り込むこともできます。

この機能について詳しくは、[&#x200B; こちら &#x200B;](https://helpx.adobe.com/jp/dreamweaver/using/working-with-dreamweaver-and-campaign.html) からアクセスできるDreamweaver ドキュメントを参照してください。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

## Experience Manager内のコンテンツの編集 {#editing-content-in-experience-manager}

メールコンテンツをExperience Managerで編集して、Adobe Campaign Standardで 1 つまたは複数のメールメッセージに使用できます。 [このドキュメント](../../integrating/using/integrating-with-experience-manager.md)を参照してください。

## 製品リスト {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="製品リストの使用"
>abstract="製品リストを使用すると、データ収集を参照し、メールコンテンツに表示できます。"

製品リストを使用すると、メールコンテンツ内の 1 つ以上のデータコレクションを参照できます。 これらのリストは、トランザクションメールで使用できます。 この機能の専用セクションは [&#x200B; こちら &#x200B;](../../designing/using/using-product-listings.md) で参照できます。

## メールデザインオプションの比較 {#email-design-options-comparison}

Adobe Campaignには、複数のメール作成オプションが用意されています。 次の表に、それぞれの主な可能性、メリットおよび制限事項を示します。

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
   <td> <strong> 空白のメールを開始 </strong><br /> </td> 
   <td> サポート対象 <br /> </td> 
   <td> サポート対象 <br /> </td> 
   <td> サポート対象 <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> 書き込みHTML</strong><br /> </td> 
   <td> サポート対象 <br /> </td> 
   <td> サポート対象外 <br /> </td> 
   <td> サポート対象 <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> 更新HTML</strong><br /> </td> 
   <td> HTMLコンポーネント内のみ <br /> </td> 
   <td> サポート対象外 <br /> </td> 
   <td> サポート対象 <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> 基本パーソナライゼーション </strong><br /> </td> 
   <td> サポート対象 <br /> </td> 
   <td> サポート対象 <br /> </td> 
   <td> サポート対象 <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> 高度なパーソナライゼーション </strong><br /> </td> 
   <td> サポート対象 <br /> </td> 
   <td> サポート対象外 <br /> </td> 
   <td> サポート対象外 <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> プルーフ/プレビュー </strong><br /> </td> 
   <td> サポート対象 <br /> </td> 
   <td> AEMでプレビュー <br /> Campaign で配達確認 <br /> </td> 
   <td> Campaign でのプレビューと配達確認 <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> 製品リスト </strong><br /> </td> 
   <td> 電子メールトランザクションメッセージでサポート <br /> </td> 
   <td> サポート対象外 <br /> </td> 
   <td> サポート対象外 <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> 便益 </strong><br /> </td> 
   <td> 
     <p>- ドラッグ&amp;ドロップ操作による簡単なメール作成</p>
     <p> – 従来のコンテンツエディターと類似した機能</p>
     <p>- フラグメントを使用した再利用可能なコンテンツ</p>
  </td> 
   <td> 
     <p>- メールで web サイトのアセットを再利用</p>
     <p>- メールコンテンツのExperience Manager機能の活用</p>
    </td> 
   <td> 
    <p>- デベロッパーがメールを直接コーディングできる機能</p>
    <p> – 双方向の同期</p>
    <p>- Dreamweaverでのオフライン編集と後での同期</p>
    <p>- Dreamweaverを使用したAdobe Campaignへの画像のアップロード</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>制限事項</strong><br /> </td> 
   <td> 
     <p>- フラグメント内に条件付きコンテンツがない</p>
     <p>-Experience Managerフラグメントを使用できない</p>
  </td> 
   <td> 
     <p> – 高度なパーソナライゼーションの実装が困難</p>
     <p>- Adobe Campaignでテストを送信する必要がある</p>
  </td> 
   <td> 動的コンテンツはサポートされていません <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>オーディエンス</strong><br /> </td> 
   <td> HTMLコンポーネントをドラッグ&amp;ドロップ機能と組み合わせて柔軟に使用したいマーケター <br /> </td> 
   <td> Experience Managerを既に使用しているマーケターが、パーソナライゼーションをほとんど使用せずに標準のメールテンプレートを使用したい場合 <br /> </td> 
   <td> メールコンテンツをコーディングし、Adobe Campaignと直接統合する開発者 <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> 詳細情報 </strong><br /> </td> 
   <td> <a href="../../designing/using/designing-content-in-adobe-campaign.md">E メールDesignerについて </a> を参照してください。<br /> </td> 
   <td> <a href="../../integrating/using/integrating-with-experience-manager.md">Experience Managerとの統合 </a> を参照してください。<br /> </td> 
   <td> <a href="https://helpx.adobe.com/jp/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaverと Campaign</a> を参照して、この <a href="#video"> ビデオ </a> をご覧ください <br />。 </td> 
  </tr> 
 </tbody> 
</table>

## チュートリアルビデオ {#video}

このビデオでは、Dreamweaverを使用してAdobe Campaign Standardのコンテンツを作成および編集する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/37614?quality=12&captions=jpn)

その他のCampaign Standardチュートリアルビデオについては、[&#x200B; こちら &#x200B;](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja) を参照してください。

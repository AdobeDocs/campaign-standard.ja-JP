---
title: Adobe Campaign統合を通じた E メールのデザイン
description: 電子メールデザイナーでAdobe Campaign統合を通じて電子メールを設計する方法を説明します。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d5c72f69-68a2-4523-956f-f265ae79b470
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 8%

---

# マルチソリューション電子メールデザイン {#multi-solution-email-design}

Adobe Campaignでは、いくつかの電子メールオーサリングオプションを提供しています。 Dreamweaverなどのソリューションを使用して、電子メールコンテンツを編集し、電子メールデザイナーでレスポンシブメッセージを作成できます。 また、コンテンツをAdobe Experience Managerで電子メールで送信し、Adobe Campaign Standardの電子メールで使用することもできます。

## Dreamweaverでのコンテンツの編集 {#editing-content-in-dreamweaver}

Adobe Campaign StandardとDreamweaverの統合により、Dreamweaverインターフェイスで E メールのコンテンツを編集できます。 Dreamweaverの強力なインターフェイスを使用して、レスポンシブ E メールコンテンツを設計および開発できます。

* **双方向同期**

   1 つの製品で編集がおこなわれるたびに、他の製品でリアルタイムに更新されます。 Dreamweaverでテキストの色を変更する場合は、編集を行うとすぐに、Campaign でテキストの色が有効になります。 また、Dreamweaverまたは Campaign でコードを選択する場合、行番号が同じなので、2 つの製品の間で選択が維持されるので、コード内の特定の項目を探す際に非常に役立ちます。

* **Dreamweaver を使用した Adobe Campaign へのローカルイメージのアップロード**

   Dreamweaver内で E メールを作成または編集する際には、デスクトップまたはローカルマシンから画像を選択するだけで済みます。 Dreamweaverでは常にこの操作が可能ですが、Dreamweaverと Campaign が接続されると、ローカルファイルがAdobe Campaignサーバーに直ちにアップロードされます。コンテンツの変更時に画像を手動でアップロードする必要はありません。 さらに、最新の画像が常に Campaign 内で有効になるようにします。

* **Dreamweaverでの Campaign パーソナライゼーションの追加**

   電子メール開発者は、次のようなテキストを追加する必要がなくなりました。 `[[FIRSTNAME_PLACEHOLDER]]` また、データモデルのテーブルの構文を調べることもできません。 Dreamweaverの Campaign ツールバーは、Campaign インスタンスのデータモデルに直接接続します。 つまり、名から住所へのパーソナライゼーションに必要なデータを取り込むことができます。 Campaign 内でコンテンツブロックを作成している場合は、それらをDreamweaverに直接取り込むこともできます。

この機能について詳しくは、 Dreamweaver Documentation を参照してください。 [ここ](https://helpx.adobe.com/jp/dreamweaver/using/working-with-dreamweaver-and-campaign.html).

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

## Experience Manager内のコンテンツの編集 {#editing-content-in-experience-manager}

E メールのコンテンツは、Experience Managerで編集し、Adobe Campaign Standardで 1 つまたは複数の E メールメッセージに使用できます。 [このドキュメント](../../integrating/using/integrating-with-experience-manager.md)を参照してください。

## 製品リスト {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="製品リストの使用"
>abstract="製品リストを使用すると、データ収集を参照し、E メールコンテンツに表示できます。"

製品リストでは、E メールコンテンツ内の 1 つ以上のデータコレクションを参照できます。 これらのリストは、トランザクション E メールで使用できます。 この機能に関する専用の節を利用できます。 [ここ](../../designing/using/using-product-listings.md).

## E メールデザインオプションの比較 {#email-design-options-comparison}

Adobe Campaignでは、いくつかの電子メールオーサリングオプションを提供しています。 次の表に、それぞれの主な可能性、メリットおよび制限を示します。

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
   <td> <strong>空のメールを開始</strong><br /> </td> 
   <td> サポート対象<br /> </td> 
   <td> サポート対象<br /> </td> 
   <td> サポート対象<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>書き込みHTML</strong><br /> </td> 
   <td> サポート対象<br /> </td> 
   <td> サポートなし<br /> </td> 
   <td> サポート対象<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>更新HTML</strong><br /> </td> 
   <td> HTMLコンポーネント内のみ<br /> </td> 
   <td> サポートなし<br /> </td> 
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
   <td> サポートなし<br /> </td> 
   <td> サポートなし<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>配達確認/プレビュー</strong><br /> </td> 
   <td> サポート対象<br /> </td> 
   <td> AEMでプレビュー<br /> キャンペーン内の配達確認<br /> </td> 
   <td> Campaign でのプレビューと配達確認<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>製品リスト</strong><br /> </td> 
   <td> E メールトランザクションメッセージでサポート<br /> </td> 
   <td> サポートなし<br /> </td> 
   <td> サポートなし<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>利点</strong><br /> </td> 
   <td> 
     <p> — ドラッグ&amp;ドロップ操作で簡単に E メールを作成</p>
     <p> — 従来のコンテンツエディターと似た機能</p>
     <p> — フラグメントを含む再利用可能なコンテンツ</p>
  </td> 
   <td> 
     <p>- Web サイトのアセットを電子メールで再利用する</p>
     <p>- E メールコンテンツのExperience Managerの力を活用</p>
    </td> 
   <td> 
    <p> — 開発者が電子メールを直接コーディングする機能</p>
    <p> — 双方向同期</p>
    <p>- Dreamweaverでオフラインで編集し、後で同期する</p>
    <p>- Dreamweaverを使用したAdobe Campaignへの画像のアップロード</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>制限事項</strong><br /> </td> 
   <td> 
     <p> — フラグメント内に条件付きコンテンツがない</p>
     <p>-Experience Managerフラグメントを使用できません</p>
  </td> 
   <td> 
     <p> — 高度なパーソナライゼーションは実装が困難</p>
     <p>- Adobe Campaignでテストを送信する必要がある</p>
  </td> 
   <td> 動的コンテンツがサポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>オーディエンス</strong><br /> </td> 
   <td> ドラッグ&amp;ドロップ機能と組み合わせて、HTMLコンポーネントを柔軟に使用し続けたいマーケター<br /> </td> 
   <td> パーソナライゼーションをほとんど行わずに標準のメールExperience Managerを使用したいと考えているマーケターは既にテンプレートを使用しています<br /> </td> 
   <td> E メールコンテンツのコーディングとAdobe Campaignとの直接統合をおこなう開発者<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>詳細はこちら</strong><br /> </td> 
   <td> 詳しくは、 <a href="../../designing/using/designing-content-in-adobe-campaign.md">E メールデザイナーについて</a>.<br /> </td> 
   <td> 詳しくは、 <a href="../../integrating/using/integrating-with-experience-manager.md">統合とExperience Manager</a>.<br /> </td> 
   <td> 詳しくは、 <a href="https://helpx.adobe.com/jp/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaverと Campaign</a> これを見て <a href="#video">ビデオ</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## チュートリアルビデオ {#video}

このビデオでは、Dreamweaverを使用してAdobe Campaign Standard用のコンテンツを作成および編集する方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

その他のCampaign Standardのハウツービデオも利用できます [ここ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja).

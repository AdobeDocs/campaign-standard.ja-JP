---
title: 'Adobe Campaign統合を通じた電子メールのデザイン '
description: 電子メールデザイナーでAdobe Campaign統合を使用して電子メールをデザインする方法を確認します。
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8e4f25a1d9ad2aa8fb74a6ddd096bda696f502da
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 7%

---


# マルチソリューション電子メールデザイン {#multi-solution-email-design}

Adobe Campaignオファーには、複数の電子メールオーサリングオプションがあります。 Dreamweaverなどのソリューションを使用して、電子メールコンテンツを編集し、電子メールデザイナーでレスポンシブメッセージを作成できます。 また、Adobe Experience Managerとコンテンツを電子メールで送信し、Adobe Campaign Standardの電子メールに使用することもできます。

## Dreamweaverでのコンテンツの編集 {#editing-content-in-dreamweaver}

Adobe Campaign StandardとDreamweaverの統合により、Dreamweaverのインターフェイスで電子メールのコンテンツを編集できます。 レスポンシブ電子メールコンテンツをデザインし開発する際に、Dreamweaverの強力なインターフェイスにアクセスできます。

* **双方向同期**

   ある製品で編集が行われると、別の製品でリアルタイムに更新されます。 Dreamweaverでテキストの色を変更する場合、編集を行うとすぐに、テキストの色がキャンペーンでライブになります。 また、Dreamweaverまたはキャンペーンでコードを選択した場合、行番号が同じなので、2つの商品の間に選択範囲が残るので、コード内で特定のものを探す場合に非常に役立ちます。

* **Dreamweaver を使用した Adobe Campaign へのローカルイメージのアップロード**

   Dreamweaver内で電子メールを作成または編集する場合は、デスクトップまたはローカルマシンから画像を選択するだけで済みます。 Dreamweaverはこれを常に許可していますが、Dreamweaverとキャンペーンが接続されている場合、ローカルファイルはすぐにAdobe Campaignサーバにアップロードされます。コンテンツの変更に応じて、手動で画像をアップロードする必要はありません。 また、最新の画像は常にキャンペーンで表示されます。

* **Dreamweaverの追加キャンペーンパーソナライゼーション**

   電子メール開発者は、のようなテキストを追加したり、データモデルのテーブルの構文を調べ `[[FIRSTNAME_PLACEHOLDER]]` たりする必要がなくなりました。 Dreamweaverのキャンペーンツールバーは、キャンペーンインスタンスのデータモデルに直接接続します。 つまり、名から住所までのようなパーソナライゼーション用の任意のデータを取り込むことができます。 コンテンツブロックをキャンペーン内に作成した場合は、コンテンツブロックを直接Dreamweaverに引き出すこともできます。

この機能の詳細については、 [こちらからアクセスできる「Dreamweaverドキュメント](https://helpx.adobe.com/jp/dreamweaver/using/working-with-dreamweaver-and-campaign.html)」を参照してください。 デモ [ビデオ](https://docs.adobe.com/content/help/ja-JP/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.translate.html) もご覧いただけます。

## Experience Managerでのコンテンツの編集 {#editing-content-in-experience-manager}

電子メールコンテンツはExperience Managerで編集でき、Adobe Campaign Standardの1つまたは複数の電子メールメッセージに使用できます。 [このドキュメント](../../integrating/using/integrating-with-experience-manager.md)を参照してください。

## 製品リスト {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="製品リストの使用"
>abstract="製品リストでは、電子メールコンテンツ内の1つ以上のデータコレクションを参照できます。"

製品リストでは、電子メールコンテンツ内の1つ以上のデータコレクションを参照できます。 これらのリストは、トランザクション電子メールで使用できます。 この機能に関するセクションは、こちら [を参照してください](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)。

## 電子メールデザインオプションの比較 {#email-design-options-comparison}

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
   <td> サポート対象<br /> </td> 
   <td> サポート対象<br /> </td> 
   <td> サポート対象<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTMLを書き込む</strong><br /> </td> 
   <td> サポート対象<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> サポート対象<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTMLを更新</strong><br /> </td> 
   <td> HTMLコンポーネント内のみ<br /> </td> 
   <td> Not supported<br /> </td> 
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
   <td> Not supported<br /> </td> 
   <td> Not supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>配達確認/プレビュー</strong><br /> </td> 
   <td> サポート対象<br /> </td> 
   <td> キャンペーン内のAEM<br /> 配達確認のプレビュー<br /> </td> 
   <td> キャンペーンのプレビューと配達確認<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>製品リスト</strong><br /> </td> 
   <td> 電子メールトランザクションメッセージでサポート<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> Not supported<br /> </td> 
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
   <td> 既にExperience Managerを使用しており、パーソナライゼーションがほとんどない標準の電子メールテンプレートを使用したい<br /> </td> 
   <td> 電子メールコンテンツをコード化し、Adobe Campaignと直接統合したい開発者<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>詳細情報</strong><br /> </td> 
   <td> See <a href="../../designing/using/designing-content-in-adobe-campaign.md">About the Email Designer</a>.<br /> </td> 
   <td> See <a href="../../integrating/using/integrating-with-experience-manager.md">Integrating with Experience Manager</a>.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/jp/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaverとキャンペーンを見て</a> 、この <a href="https://docs.adobe.com/content/help/ja-JP/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.translate.html">ビデオを見てください</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

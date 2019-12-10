---
title: 'Adobe Campaign統合を使用した電子メールのデザイン '
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
source-git-commit: 021bea88b69a85b9a9535143ec8d689858af517b

---


# マルチソリューション電子メールデザイン {#multi-solution-email-design}

Adobe Campaignには、複数の電子メールオーサリングオプションが用意されています。 Dreamweaverなどのソリューションを使用して、電子メールコンテンツを編集し、電子メールデザイナーでレスポンシブメッセージを作成できます。 また、Adobe Experience Managerでコンテンツを電子メールで送信し、Adobe Campaign Standardの電子メールで使用することもできます。

## Dreamweaverでのコンテンツの編集 {#editing-content-in-dreamweaver}

Adobe Campaign StandardとDreamweaverの統合により、Dreamweaverインターフェイスで電子メールのコンテンツを編集できます。 Dreamweaverの強力なインターフェイスを使用して、レスポンシブな電子メールコンテンツをデザインし、開発することができます。

* **双方向同期**

   ある製品で編集が行われると、他の製品でもリアルタイムに更新されます。 Dreamweaverでテキストの色を変更する場合、編集を行うとすぐに、Campaignでテキストの色が反映されます。 また、DreamweaverまたはCampaignでコードを選択した場合、行番号が同じなので、2つの製品の間で選択が維持されるので、コード内で特定のものを探す場合に非常に役立ちます。

* **Dreamweaverを使用したAdobe Campaignへのローカル画像のアップロード**

   Dreamweaverで電子メールを作成または編集する場合は、デスクトップまたはローカルマシンからイメージを選択するだけで済みます。 Dreamweaverでは常にこの操作が許可されていますが、DreamweaverとCampaignが接続されている場合、ローカルファイルは直ちにAdobe Campaignサーバにアップロードされます。コンテンツの変更時に画像を手動でアップロードする必要はありません。 さらに、最新の画像が常にCampaign内で使用されるようにします。

* **Dreamweaverでのキャンペーンパーソナライゼーションの追加**

   電子メール開発者は、データモデルのテーブルのようなテキストを追加したり、 `[[FIRSTNAME_PLACEHOLDER]]` 構文を調べたりする必要がなくなりました。 Dreamweaverのキャンペーンツールバーは、Campaignインスタンスのデータモデルに直接接続します。 つまり、名から住所へのパーソナライゼーションに必要な任意のデータを取り込むことができます。 キャンペーン内にコンテンツブロックを作成した場合は、Dreamweaverに直接コンテンツブロックを取り込むこともできます。

この機能について詳しくは、Dreamweaverマニュアルを参照して [ください](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html)。 デモビデ [オも](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) 、ご覧いただけます。

## Experience Managerでのコンテンツの編集 {#editing-content-in-experience-manager}

電子メールコンテンツはExperience Managerで編集し、Adobe Campaign Standardで1つまたは複数の電子メールメッセージに使用できます。 本書を参 [照](../../integrating/using/integrating-with-experience-manager.md)。

## 電子メールデザインオプションの比較 {#email-design-options-comparison}

Adobe Campaignには、複数の電子メールオーサリングオプションが用意されています。 次の表に、それぞれの主な可能性、利点、制限を示します。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Email Designer<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>空白の電子メールの開始</strong><br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポート<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTMLの書き込み</strong><br /> </td> 
   <td> サポート<br /> </td> 
   <td> 未サポート<br /> </td> 
   <td> サポート<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTMLの更新</strong><br /> </td> 
   <td> HTMLコンポーネント内のみ<br /> </td> 
   <td> 未サポート<br /> </td> 
   <td> サポート<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>基本パーソナライゼーション</strong><br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポート<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>高度なパーソナライゼーション</strong><br /> </td> 
   <td> サポート<br /> </td> 
   <td> 未サポート<br /> </td> 
   <td> 未サポート<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>校正/プレビュー</strong><br /> </td> 
   <td> サポート<br /> </td> 
   <td> キャンペーンでのAEM<br /> Proofでのプレビュー<br /> </td> 
   <td> キャンペーンでのプレビューと校正<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>製品リスト</strong><br /> </td> 
   <td> 電子メールトランザクションメッセージでサポート<br /> </td> 
   <td> 未サポート<br /> </td> 
   <td> 未サポート<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>メリット</strong><br /> </td> 
   <td> 
     <p> — ドラッグアンドドロップ操作で簡単に電子メールを作成</p>
     <p> — レガシーコンテンツエディターと同様の機能</p>
     <p> — フラグメントを含む再利用可能なコンテンツ</p>
  </td> 
   <td> 
     <p> — 電子メール内のWebサイトのアセットの再利用</p>
     <p>- Experience Managerの機能を電子メールコンテンツで活用</p>
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
     <p>- Experience Managerフラグメントを使用できない</p>
  </td> 
   <td> 
     <p> — 導入が困難な高度なパーソナライゼーション</p>
     <p>- Adobe Campaignでテストを送信する必要がある</p>
  </td> 
   <td> 動的コンテンツはサポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>オーディエンス</strong><br /> </td> 
   <td> ドラッグ&amp;ドロップ機能と組み合わせてHTMLコンポーネントを柔軟に使用したいマーケター<br /> </td> 
   <td> マーケティング担当者は、既にExperience Managerを使用しており、パーソナライゼーションをほとんど行わずに標準の電子メールテンプレートを使用する必要があります。<br /> </td> 
   <td> 電子メールコンテンツをコーディングし、Adobe Campaignと直接統合する開発者<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>詳細情報</strong><br /> </td> 
   <td> 電子メー <a href="../../designing/using/overview.md">ルデザイナーについてを参照してくださ</a>い。<br /> </td> 
   <td> See <a href="../../integrating/using/integrating-with-experience-manager.md">Integrating with Experience Manager</a>.<br /> </td> 
   <td> 詳しくは、 <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">DreamweaverとCampaignを参照し</a> 、このビデオをご覧 <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">ください</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

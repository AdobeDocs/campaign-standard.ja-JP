---
title: 'Adobe Campaign統合を通じた電子メールの設計 '
seo-title: 'Adobe Campaign統合を通じた電子メールの設計  '
description: 'Adobe Campaign統合を通じた電子メールの設計 '
seo-description: 電子メールデザイナでAdobe Campaignを統合して電子メールをデザインする方法を説明します。
page-status-flag: 未活性化の
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 設計
content-type: 参照
topic-tags: 編集，電子メールの内容
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 195e8db45609b8f92f0ec60c987cf6eadfd463eb

---

# マルチソリューションのEメール設計 {#multi-solution-email-design}

## Dreamweaverでのコンテンツの編集 {#editing-content-in-dreamweaver}

Adobe Campaign StandardとDreamweaverの統合により、Dreamweaverインタフェースで電子メールのコンテンツを編集できます。 Dreamweaverの強力なインタフェースにアクセスして、応答性の高い電子メールコンテンツを設計し、開発できます。

* **双方向同期**

   1つの製品で編集が行われるたびに、別の製品でリアルタイムに更新されます。 Dreamweaverでテキストの色を変更する場合は、編集を行うとすぐに、そのテキストの色がキャンペーンに反映されます。 また、Dreamweaverまたはキャンペーンでコードを選択した場合は、行番号が同じため、2つの製品の間で選択が維持され、コード内の特定の項目を検索する場合に非常に便利です。

* **Dreamweaverを使用してローカルイメージをAdobe Campaignにアップロード**

   Dreamweaverで電子メールを作成または編集する場合は、デスクトップまたはローカルマシンからイメージを選択するだけで済みます。 Dreamweaverでは常にこの操作が許可されていますが、DreamweaverとCampaignが接続されると、ローカルファイルがAdobe Campainサーバに直ちにアップロードされます。コンテンツの変更時にイメージを手動でアップロードする必要はありません。 また、最新の画像が常にキャンペーンに反映されます。

* **Dreamweaverでのキャンペーンのパーソナライズの追加**

   Eメール開発者は、データ·モデルの表の構文を検索するようなテキ `[[FIRSTNAME_PLACEHOLDER]]` ストを追加する必要がなくなりました。 Dreamweaverの[キャンペーン]ツールバーは、キャンペーンインスタンスのデータモデルに直接接続します。 つまり、個人用設定に必要なデータを、名から住所へと取り込むことができます。 キャンペーン内にコンテンツブロックを作成した場合は、Dreamweaverに直接取り込むこともできます。

この機能の詳細は、ここでアクセス可能なDreamweaverのマニュアルを参照し [てください](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html)。 デモビデ [オも](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) 。

## エクスペリエンスマネージャでのコンテンツの編集 {#editing-content-in-experience-manager}

Eメールコンテンツは、Experience Managerで編集し、Adobe Campaign Standardで1つまたは複数のEメールメッセージに使用できます。 この文書を参 [照してください](../../integrating/using/integrating-with-experience-manager.md)。

## 電子メールデザインオプションの比較 {#email-design-options-comparison}

Adobe Campaignには、いくつかの電子メールオーサリングオプションが用意されています。 次の表に、各々の主な可能性、メリット、制限を示します。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> 電子メールデザイナ<br /> </th> 
   <th> 経験マネージャ<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>空の電子メールを開始</strong><br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポート<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTMLの書き込み</strong><br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポート<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTMLの更新</strong><br /> </td> 
   <td> HTMLコンポーネント内のみ<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポート<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>基本的な個人用設定</strong><br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポート<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>高度なカスタマイズ</strong><br /> </td> 
   <td> サポート<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>校正/プレビュー</strong><br /> </td> 
   <td> サポート<br /> </td> 
   <td> キャンペーンのAEM<br /> Proofでプレビュー<br /> </td> 
   <td> キャンペーンのプレビューと校正<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>製品一覧</strong><br /> </td> 
   <td> 電子メールトランザクションメッセージでサポート<br /> </td> 
   <td> サポートされていません<br /> </td> 
   <td> サポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>メリット</strong><br /> </td> 
   <td> 
     -ドラッグ·アンド·ドロップ操作によるEメールの容易な構築<br/>-従来のコンテンツ·エディタと同様の機能<br/>-断片を含む再利用可能なコンテンツ
  </td> 
   <td> 
     - webサイトの資産をEメールで再利用<br/>- Experience Managerの機能をEメールコンテンツで活用
    </td> 
   <td> 
    -開発者が電子メールを直接コーディングする機能<br/>-双方向の同期<br/>- Dreamweaverでのオフライン編集と後での同期<br/>- Dreamweaverを介したAdobeキャンペーンへの画像のアップロード
  </td> 
  </tr> 
  <tr> 
   <td> <strong>制限事項</strong><br /> </td> 
   <td> 
     -フラグメント内に条件付きコンテンツがありません<br/>-エクスペリエンスマネージャのフラグメントを使用できません
  </td> 
   <td> 
     -高度なパーソナライズは実装が難しい<br/>- Adobeキャンペーンでテストを送信する必要がある
  </td> 
   <td> 動的コンテンツはサポートされていません<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>対象</strong><br /> </td> 
   <td> HTMLコンポーネントをドラッグアンドドロップ機能と組み合わせて使用する柔軟性を維持したいマーケティング担当者<br /> </td> 
   <td> マーケティング担当者は既にエクスペリエンスマネージャを使用しており、個人用設定の少ない標準の電子メールテンプレートを使用する<br /> </td> 
   <td> 電子メールの内容をコーディングし、Adobe Campaignと直接統合する開発者<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>詳細はこちら</strong><br /> </td> 
   <td> 電子メー <a href="../../designing/using/overview.md">ルデザイナについて</a><br /> </td> 
   <td> 「エクスペリ <a href="../../integrating/using/integrating-with-experience-manager.md">エンスマネージャとの統合」を参照</a><br /> </td> 
   <td> 「 <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaverとキャンペーン</a> 」を参照し、このビデオを <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">見る</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

---
title: Analytics のキャンペーンディメンションと指標
description: Adobe AnalyticsでAdobe Campaignからの電子メール配信の追跡を開始するための様々なディメンションについて説明します。
page-status-flag: 非活性化の
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: キャンペーンと分析の連携
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Analytics のキャンペーンディメンションと指標{#campaign-dimensions-and-metrics-in-analytics}

Adobe CampaignとAdobe Analyticsの統合により、電子メール配信の成功をAdobe Analyticsで直接追跡できます。

Analyticsで見つ **[!UICONTROL dimensions]** かったキャンペーンを以下に示します。

<table> 
 <thead> 
  <tr> 
   <th> ディメンション<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> キャンペーン ID<br /> </td> 
   <td> Campaignで確認できるキャンペーンの内部名<br /> </td> 
  </tr> 
  <tr> 
   <td> キャンペーンラベル<br /> </td> 
   <td> キャンペーンでのキャンペーンのラベル<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信 ID<br /> </td> 
   <td> Campaignで確認できる、配信の内部名。<br /> 例えば、DM1は繰り返し配信され、毎週子の配信がスケジュールされます。 DM2、DM3、DM4は最初の3週間で送信されます。 その後、配信IDディメンションは、すべての配信の結果(DM1 ～ DM4)を表示します。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 配信ラベル<br /> </td> 
   <td> キャンペーンでの配信のラベル<br /> </td> 
  </tr> 
  <tr> 
   <td> 実行された配信ID<br /> </td> 
   <td> Campaignで確認できる、配信の内部名。 これは、キャンペーンでの実行時の配信に関するだけです。<br /> 例えば、DM1は繰り返し配信され、毎週子の配信がスケジュールされます。 DM2、DM3、DM4は最初の3週間で送信されます。 次に、実行された配信IDディメンションは、実行された配信の結果、すなわち子配信DM2、DM3、DM4を表示します。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 実行された配信ラベル<br /> </td> 
   <td> キャンペーンでの配信のラベル。 これは、キャンペーンでの実行時の配信に関するだけです。<br /> </td> 
  </tr> 
 </tbody> 
</table>

Analyticsで見つ **[!UICONTROL metrics]** かったキャンペーンを以下に示します。

<table> 
 <thead> 
  <tr> 
   <th> 指標<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> クリック済み<br /> </td> 
   <td> 配信でコンテンツがクリックされた回数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> 送信されたメッセージの合計数に関連して正常に送信されたメッセージの数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開封済み<br /> </td> 
   <td> 配信でメッセージが開かれた回数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 送信済み<br /> </td> 
   <td> 配信の送信の合計数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 合計バウンス数<br /> </td> 
   <td> 送信されたメッセージの合計数に関して、配信および自動返信処理中に累積されたエラーの合計。<br /> </td> 
  </tr> 
  <tr> 
   <td> 個別オープン<br /> </td> 
   <td> 配信を開いた受信者の数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 個別クリック<br /> </td> 
   <td> 配信内のコンテンツをクリックした受信者の数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 購読解除済み<br /> </td> 
   <td> 購読解除リンクのクリック数。<br /> </td> 
  </tr> 
 </tbody> 
</table>


---
title: Analytics での Campaign のディメンションと指標
description: Adobe Campaignから電子メール配信を追跡する開始に対して、Adobe Analyticsで見られる様々なディメンションについて説明します。
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 10%

---


# Analytics での Campaign のディメンションと指標{#campaign-dimensions-and-metrics-in-analytics}

Adobe CampaignとAdobe Analyticsの統合により、Adobe Analyticsで電子メール配信の成功を直接追跡できます。

Analyticsで見つかったキャンペーン **[!UICONTROL dimensions]** を以下に示します。

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
   <td> キャンペーンで見たキャンペーンの内部名<br /> </td> 
  </tr> 
  <tr> 
   <td> キャンペーンラベル<br /> </td> 
   <td> キャンペーンで見たキャンペーンのラベル<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信 ID<br /> </td> 
   <td> キャンペーンに表示される配信の内部名。<br /> 例えば、DM1は、子配信を毎週送信するようにスケジュールされた繰り返しの配信です。 DM2、DM3、DM4は最初の3週間送信されます。 次に、配信IDディメンションは、DM1 ～ DM4の各配信の結果を表示します。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 配信ラベル<br /> </td> 
   <td> キャンペーンで見た配信のラベル<br /> </td> 
  </tr> 
  <tr> 
   <td> 実行された配信ID<br /> </td> 
   <td> キャンペーンに表示される配信の内部名。 これは、キャンペーンでの実行の配信に関するだけです。<br /> 例えば、DM1は、子配信を毎週送信するようにスケジュールされた繰り返しの配信です。 DM2、DM3、DM4は最初の3週間送信されます。 次に、実行配信IDディメンションは、子配信DM2,DM3,DM4である実行配信の結果を表示する。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 実行された配信ラベル<br /> </td> 
   <td> 配信のラベルをキャンペーンで確認できます。 これは、キャンペーンでの実行の配信に関するだけです。<br /> </td> 
  </tr> 
 </tbody> 
</table>

Analyticsで見つかったキャンペーン **[!UICONTROL metrics]** を以下に示します。

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
   <td> 配信内でコンテンツがクリックされた回数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> 送信されたメッセージの合計数に関連して、正常に送信されたメッセージの数。<br /> </td> 
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
   <td> 配信および自動返信処理中に発生したエラーの合計で、送信されたメッセージの合計数に関連して計算されたエラーの合計です。<br /> </td> 
  </tr> 
  <tr> 
   <td> 一意のオープン<br /> </td> 
   <td> 配信を開いた受信者の数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> 個別クリック<br /> </td> 
   <td> 配信内のコンテンツをクリックした受信者の数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> 購読解除済み<br /> </td> 
   <td> 購読解除リンクのクリック数。<br /> </td> 
  </tr> 
 </tbody> 
</table>


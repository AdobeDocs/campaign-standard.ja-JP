---
solution: Campaign Standard
product: campaign
title: Analytics での Campaign のディメンションと指標
description: Adobe Campaignから電子メール配信を追跡する開始に対して、Adobe Analyticsで見られる様々なディメンションについて説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 10%

---


# Analytics での Campaign のディメンションと指標{#campaign-dimensions-and-metrics-in-analytics}

Adobe CampaignとAdobe Analyticsの統合により、Adobe Analyticsで電子メール配信の成功を直接追跡できます。

Analyticsで見つかったキャンペーン&#x200B;**[!UICONTROL dimensions]**&#x200B;を以下に示します。

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
   <td> キャンペーン<br />に示すキャンペーンの内部名 </td> 
  </tr> 
  <tr> 
   <td> キャンペーンラベル<br /> </td> 
   <td> キャンペーン<br />で見たキャンペーンのラベル </td> 
  </tr> 
  <tr> 
   <td> 配信 ID<br /> </td> 
   <td> キャンペーンに表示される配信の内部名。<br /> 例えば、DM1は、子配信を毎週送信するようにスケジュールされた繰り返しの配信です。DM2、DM3、DM4は最初の3週間送信されます。 次に、配信IDディメンションは、配信ごとにDM1 ～ DM4の結果を表示します。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信ラベル<br /> </td> 
   <td> キャンペーン<br />で見た配信のラベル </td> 
  </tr> 
  <tr> 
   <td> 実行された配信ID<br /> </td> 
   <td> キャンペーンに表示される配信の内部名。 これは、キャンペーンでの実行の配信に関するだけです。<br /> 例えば、DM1は、子配信を毎週送信するようにスケジュールされた繰り返しの配信です。DM2、DM3、DM4は最初の3週間送信されます。 次に、実行された配信IDディメンションは、実行された配信、すなわち子配信DM2、DM3、DM4の結果を表示します。<br /> </td> 
  </tr> 
  <tr> 
   <td> 実行された配信ラベル<br /> </td> 
   <td> 配信のラベルをキャンペーンで確認できます。 これはキャンペーンでの実行時の配信に関するだけです。<br /> </td> 
  </tr> 
 </tbody> 
</table>

Analyticsで見つかったキャンペーン&#x200B;**[!UICONTROL metrics]**&#x200B;を以下に示します。

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
   <td> 正常に送信されたメッセージの数（送信されたメッセージの合計数に関連）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開封済み<br /> </td> 
   <td> 配信でメッセージが開かれた回数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 送信済み<br /> </td> 
   <td> 配信の送信の総数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> バウンス合計<br /> </td> 
   <td> 配信および自動返信処理中に発生したエラーの合計（送信メッセージの合計数に関するエラー）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 一意のオープン<br /> </td> 
   <td> 配信を開いた受信者の数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> 一意クリック<br /> </td> 
   <td> 配信内のコンテンツをクリックした受信者の数です。<br /> </td> 
  </tr> 
  <tr> 
   <td> 購読解除済み<br /> </td> 
   <td> 購読解除リンクのクリック数。<br /> </td> 
  </tr> 
 </tbody> 
</table>


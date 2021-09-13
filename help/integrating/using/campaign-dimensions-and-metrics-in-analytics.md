---
title: Analytics での Campaign のディメンションと指標
description: Adobe CampaignからEメール配信のトラッキングを開始するために、Adobe Analyticsで見つけられる様々なディメンションについて説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 6516c71a-efa8-4778-82bb-10615378f985
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 11%

---

# Analytics での Campaign のディメンションと指標{#campaign-dimensions-and-metrics-in-analytics}

Adobe CampaignとAdobe Analyticsの統合により、Eメール配信の成功をAdobe Analyticsで直接追跡できます。

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
   <td> Campaign<br />で確認できるキャンペーンの内部名 </td> 
  </tr> 
  <tr> 
   <td> キャンペーンラベル<br /> </td> 
   <td> キャンペーンのラベル<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信 ID<br /> </td> 
   <td> Campaignで確認できる、配信の内部名。<br /> 例えば、DM1は、毎週子配信を送信するようにスケジュールされた繰り返し配信です。DM2、DM3、DM4は最初の3週間に送信されます。 次に、配信IDディメンションに、すべての配信の結果(DM1 ～ DM4)が表示されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信ラベル<br /> </td> 
   <td> キャンペーン<br />に表示される配信のラベル </td> 
  </tr> 
  <tr> 
   <td> 実行された配信ID<br /> </td> 
   <td> Campaignで確認できる、配信の内部名。 これは、Campaignでの実行時の配信にのみ関係します。<br /> 例えば、DM1は、毎週子配信を送信するようにスケジュールされた繰り返し配信です。DM2、DM3、DM4は最初の3週間に送信されます。 次に、実行された配信IDディメンションに、実行された配信（子配信DM2、DM3、DM4）の結果が表示されます。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 実行された配信ラベル<br /> </td> 
   <td> キャンペーンで表示される配信のラベル。 これは、Campaignでの実行中の配信にのみ関係します。<br /> </td> 
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
   <td> 送信されたメッセージの合計数に対する、正常に送信されたメッセージの数。<br /> </td> 
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
   <td> 送信されたメッセージの合計数に関して、配信および自動返信処理中に累積したエラーの合計。<br /> </td> 
  </tr> 
  <tr> 
   <td> ユニーク開封数<br /> </td> 
   <td> 配信を開封した受信者の数。<br /> </td> 
  </tr> 
  <tr> 
   <td> ユニーククリック<br /> </td> 
   <td> 配信内のコンテンツをクリックした受信者の数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 購読解除済み<br /> </td> 
   <td> 購読解除リンクのクリック数。<br /> </td> 
  </tr> 
 </tbody> 
</table>

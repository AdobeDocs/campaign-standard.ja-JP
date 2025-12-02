---
title: Analytics での Campaign のディメンションと指標
description: Adobe Campaignからメール配信のトラッキングを開始するためにAdobe Analyticsで見つけることができる様々なディメンションについて説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 6516c71a-efa8-4778-82bb-10615378f985
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 32%

---

# Analytics での Campaign のディメンションと指標{#campaign-dimensions-and-metrics-in-analytics}

Adobe CampaignとAdobe Analyticsの統合により、メール配信の成功をAdobe Analyticsで直接トラッキングできます。

Analytics にある Campaign **[!UICONTROL dimensions]** を以下に示します。

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
   <td> Campaign に表示される Campaign の内部名 <br /> </td> 
  </tr> 
  <tr> 
   <td> キャンペーンラベル <br /> </td> 
   <td> Campaign に表示されるキャンペーンのラベル <br /> </td> 
  </tr> 
  <tr> 
   <td> 配信 ID<br /> </td> 
   <td> Campaign に表示される配信の内部名。<br /> 例えば、DM1 は、毎週子の配信を送信するようにスケジュールされた繰り返し配信です。 DM2、DM3、DM4 は最初の 3 週間に送信されます。 この場合、配信 ID ディメンションには、配信ごとに結果が表示されます（DM1 から DM4 まで）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信ラベル <br /> </td> 
   <td> Campaign に表示される配信のラベル <br /> </td> 
  </tr> 
  <tr> 
   <td> 実行された配信 ID <br /> </td> 
   <td> Campaign に表示される配信の内部名。 これは、Campaign での実行時の配信にのみ関係します。<br /> 例えば、DM1 は、毎週子の配信を送信するようにスケジュールされた繰り返し配信です。 DM2、DM3、DM4 は最初の 3 週間に送信されます。 実行済み配信 ID ディメンションには、実行済み配信の結果（子配信 DM2、DM3、DM4）が表示されます。<br /> </td> 
  </tr> 
  <tr> 
   <td> 実行された配信ラベル <br /> </td> 
   <td> キャンペーンに表示される配信のラベル。 これは、Campaign で実行される配信にのみ関係します。<br /> </td> 
  </tr> 
 </tbody> 
</table>

Analytics にある Campaign **[!UICONTROL metrics]** を以下に示します。

<table> 
 <thead> 
  <tr> 
   <th> 指標<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> クリック <br /> </td> 
   <td> 1 つの配信で、あるコンテンツがクリックされた回数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信済み<br /> </td> 
   <td> 送信されたメッセージの合計数に対して、正常に送信されたメッセージの数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 開封済み<br /> </td> 
   <td> 1 つの配信で、あるメッセージが開かれた回数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 送信済み<br /> </td> 
   <td> 配信の合計送信数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 合計バウンス数 <br /> </td> 
   <td> 送信されたメッセージの合計数に対して、配信および自動返信処理時のエラー累計の合計。<br /> </td> 
  </tr> 
  <tr> 
   <td> ユニーク開封数 <br /> </td> 
   <td> 配信を開いた受信者の数。<br /> </td> 
  </tr> 
  <tr> 
   <td> ユニーククリック <br /> </td> 
   <td> 1 つの配信で、あるコンテンツをクリックした受信者の数。<br /> </td> 
  </tr> 
  <tr> 
   <td> 購読解除済み<br /> </td> 
   <td> 購読解除リンクがクリックされた回数。<br /> </td> 
  </tr> 
 </tbody> 
</table>

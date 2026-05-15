---
title: Analytics での Campaign のディメンションと指標
description: Adobe Analyticsで確認できる様々なディメンションについて説明し、Adobe Campaignからのメール配信のトラッキングを開始します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 6516c71a-efa8-4778-82bb-10615378f985
TQID: https://experienceleague.adobe.com/PSAzSStMFWofMteBu3jMSizD2kj1M9F7-0iO3dcugjY
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 320
ht-degree: 32%

---

# Analytics での Campaign のディメンションと指標{#campaign-dimensions-and-metrics-in-analytics}

Adobe CampaignとAdobe Analyticsの連携により、メール配信の成果をAdobe Analyticsで直接追跡できます。

Analyticsで見つかったキャンペーン **[!UICONTROL dimensions]**&#x200B;を以下に示します。

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
   <td> Campaign<br />に表示されるCampaignの内部名 </td> 
  </tr> 
  <tr> 
   <td> キャンペーンラベル <br /> </td> 
   <td> Campaign<br />に表示されるCampaignのラベル </td> 
  </tr> 
  <tr> 
   <td> 配信ID <br /> </td> 
   <td> Campaignに表示される配信の内部名。<br /> 例えば、DM1は、毎週子の配信を送信するようにスケジュールされた定期的な配信です。 DM2、DM3、DM4は最初の3週間に送信されます。 次に、配信ID ディメンションは、各配信の結果（つまり、DM1からDM4まで）を表示します。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信ラベル <br /> </td> 
   <td> Campaign<br />に表示される配信のラベル </td> 
  </tr> 
  <tr> 
   <td> 配信ID <br />を実行しました </td> 
   <td> Campaignに表示される配信の内部名。 これは、Campaignでの実行中の配信にのみ関係します。<br /> 例えば、DM1は、毎週子の配信を送信するようにスケジュールされた定期的な配信です。 DM2、DM3、DM4は最初の3週間に送信されます。 実行された配信ID ディメンションは、実行された配信、つまり子の配信DM2、DM3、およびDM4の結果を表示します。<br /> </td> 
  </tr> 
  <tr> 
   <td> 配信ラベル <br />を実行しました </td> 
   <td> Campaignに表示される配信のラベル。 これは、Campaignでの実行中の配信にのみ関係します。<br /> </td> 
  </tr> 
 </tbody> 
</table>

Analyticsで見つかったキャンペーン **[!UICONTROL metrics]**&#x200B;を以下に示します。

<table> 
 <thead> 
  <tr> 
   <th> 指標<br /> </th> 
   <th> 定義<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <br />をクリックしました </td> 
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
   <td> 合計バウンス数<br /> </td> 
   <td> 送信されたメッセージの合計数に対して、配信および自動返信処理時のエラー累計の合計。<br /> </td> 
  </tr> 
  <tr> 
   <td> ユニーク開封<br /> </td> 
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

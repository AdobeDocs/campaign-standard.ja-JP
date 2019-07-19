---
title: Analyticsのキャンペーンディメンションと指標
seo-title: Analyticsのキャンペーンディメンションと指標
description: Analyticsのキャンペーンディメンションと指標
seo-description: Adobe Analyticsで、Adobe Campaignからの電子メール配信の追跡を開始するための様々なディメンションについて説明します。
page-status-flag: 常にアクティブ化されていない
uuid: effa1028-66b2-4bef- b5e4-7319dbb23d5d
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- analytics
discoiquuid: eb3639f5-7246-46c4-8ddb- da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Campaign dimensions and metrics in Analytics{#campaign-dimensions-and-metrics-in-analytics}

Adobe CampaignとAdobe Analyticsの統合により、Adobe Analyticsで電子メール配信の成功を追跡できます。

Campaign **[!UICONTROL dimensions]** found in Analytics are listed below:

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Campaign ID<br /> </td> 
   <td> Campaign's internal name as seen in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign label<br /> </td> 
   <td> Campaign's label as seen in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery ID<br /> </td> 
   <td> キャンペーンで表示される配信の内部名。<br /> 例えば、DM1は、子配信を毎週送信するようにスケジュールされた定期配信です。DM2、DM3およびDM4には最初の3週間が送信されます。The Delivery ID dimension will then display the results for every delivery, namely DM1 to DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery label<br /> </td> 
   <td> Delivery's label as seen in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Executed delivery ID<br /> </td> 
   <td> キャンペーンで表示される配信の内部名。これは、キャンペーンでの実行の配信にのみ影響します。<br /> 例えば、DM1は、子配信を毎週送信するようにスケジュールされた定期配信です。DM2、DM3およびDM4には最初の3週間が送信されます。The Executed delivery ID dimension will then display the results for the executed deliveries, namely the child deliveries DM2, DM3 and DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Executed delivery label<br /> </td> 
   <td> キャンペーンで表示される配信のラベル。This only concerns delivery in execution in Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Campaign **[!UICONTROL metrics]** found in Analytics are listed below:

<table> 
 <thead> 
  <tr> 
   <th> Metric<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Clicked<br /> </td> 
   <td> Number of times a content was clicked in a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivered<br /> </td> 
   <td> Number of messages successfully sent, in relation to the total number of sent messages.<br /> </td> 
  </tr> 
  <tr> 
   <td> Opened<br /> </td> 
   <td> Number of times a message was opened in a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sent<br /> </td> 
   <td> Total number of sends for the delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Total Bounces<br /> </td> 
   <td> Total of errors cumulated during delivery and automatic return processing in relation to the total number of sent messages.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unique Open<br /> </td> 
   <td> Number of recipients who opened the delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unique Click<br /> </td> 
   <td> Number of recipients who clicked on a content in a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unsubscribed<br /> </td> 
   <td> Number of clicks on the unsubscription link.<br /> </td> 
  </tr> 
 </tbody> 
</table>


---
title: トラブルシューティング
seo-title: トラブルシューティング
description: トラブルシューティング
seo-description: 動的レポートに関する一般的な質問を参照してください。
page-status-flag: 常にアクティブ化されていない
uuid: a84a18bd-4e33-466e- a6ce- d7008fe12746
contentOwner: below
products: SG_ CAMPAIGN/STANDARD
audience: レポート
content-type: 参照
topic-tags: トラブルシューティング
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e0cbdfecde495d7c9f8bfa33dd5ee8598cdfe60a

---


# Troubleshooting{#troubleshooting}

この節では、動的レポートに関する一般的な質問について説明します。

## For Unique opens and Unique clicks, the count in the aggregate row is not matching the ones in individual rows {#unique-open-clicks-no-match}

これは期待される動作です。
この動作を説明する例を以下に示します。

P1およびP2プロファイルに電子メールが送信されます。

P1は、最初の日に2回電子メールを開き、2日目にツリー時間をかけます。

一方、P2は最初の日に1回電子メールを開き、次の日で再度開きません。
次に、送信された電子メールとのプロファイルのインタラクションを視覚的に示します。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>日</strong><br /> </th> 
   <th align="center"> <strong>開く</strong><br /> </th> 
   <th align="center"> <strong>個別開封</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Day 1<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> Day 2<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

To understand the overall number of unique opens, we need to sum up the row counts of **[!UICONTROL Unique Opens]** which gives us the value 3. ただし、電子メールは2つのプロファイルのみをターゲットとしているので、開くレートは150%になります。

To not obtain percentage higher than 100, the definition of **[!UICONTROL Unique Opens]** is maintained to be the number of unique broadlogs that were opened. この場合、P1がDay1およびDay2の電子メールを開いた場合でも、一意のオープンが1になります。

これにより、次の表が表示されます。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>日</strong><br /> </th> 
   <th align="center"> <strong>開く</strong><br /> </th> 
   <th align="center"> <strong>個別開封</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Day 1<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Day 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>一意の数はHLLベースのスケッチに基づいているので、大きな数の不正確な結果になる可能性があります。

## Open counts do not match the Database count {#open-counts-no-match-database}

This may be due to the fact that, heuristics are used in Dynamic reporting to track opens even when we can't track the **[!UICONTROL Open]** action.

For example, if a user has disabled images on their client and click on a link in the email, the **[!UICONTROL Open]** may not be tracked by the database but the **[!UICONTROL Click]** will.

Therefore, the **[!UICONTROL Open]** tracking logs counts may not have the same count in the database.

Such occurrences are added as **"an email click implies an email open"**.

>[!NOTE]
>
>一意の数はHLLベースのスケッチに基づいているので、カウント間の小さな不一致を経験できます。

## 定期的な配信/トランザクション配信のカウントはどのように計算されますか。

定期配信とトランザクション配信の場合、カウントは親配信と子配信の両方に関連付けられます。

**R1** という定期的な配信の例として、毎日1日（RC1）、日2（RC2）および3日目（RC3）という名前の定期配信があります。

1人のユーザーのみがすべての子配信を複数回開いていると仮定します。In this case, the individual recurring child deliveries will show the **[!UICONTROL Open]** count as 1 for each.

However, since the same person clicked on all the deliveries, the parent recurring delivery will also have **[!UICONTROL Unique open]** as 1.

After the Adobe Campaign Standard 19.2.1 release, the definition of **Unique counts** is changed from **Number of unique persons interacting with the delivery** to **Number of unique messages interacted**.

Adobe Campaign Standard19.2.1リリースより前のレポートは、次のようになりました。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>配信</strong><br /> </th> 
   <th align="center"> <strong>送信済み</strong><br /> </th> 
   <th align="center"> <strong>配信済み</strong><br /> </th>
   <th align="center"> <strong>開く</strong><br /> </th> 
   <th align="center"> <strong>個別開封</strong><br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1<br/> </td> 
   <td align="center"> <strong>100<br/> </td> 
   <td align="center"> <strong>90<br/> </td> 
   <td align="center"> <strong>10<br/> </td> 
   <td align="center"> <strong>1<br/> </td> 
  </tr> 
  <tr> 
   <td align="center"> RC1<br/> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
    <tr> 
   <td align="center"> RC2<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 30<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
    <tr> 
   <td align="center"> RC3<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
 </tbody> 
</table>

Adobe Campaign Standard19.2.1リリース以降、レポートは次のようになります。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>配信</strong><br /> </th> 
   <th align="center"> <strong>送信済み</strong><br /> </th> 
   <th align="center"> <strong>配信済み</strong><br /> </th>
   <th align="center"> <strong>開く</strong><br /> </th> 
   <th align="center"> <strong>個別開封</strong><br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1<br/> </td> 
   <td align="center"> <strong>100<br/> </td> 
   <td align="center"> <strong>90<br/> </td> 
   <td align="center"> <strong>10<br/> </td> 
   <td align="center"> <strong>3<br/> </td> 
  </tr> 
  <tr> 
   <td align="center"> RC1<br/> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
    <tr> 
   <td align="center"> RC2<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 30<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
    <tr> 
   <td align="center"> RC3<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

## What is the colors' signification in my reports' table? {#reports-color-signification}

レポートに表示される色はランダムに表示され、パーソナライズすることはできません。これらはプログレスバーを表し、レポートで最大値に達したときに表示されるように表示されます。

次の例では、セルの値は100%のため、同じ色になっています。

![](assets/troubleshooting_1.png)

**条件付き書式をカスタム** に変更すると、値が上限に達するとセルがグレーになります。一方、下限に達すると、修正されます。

For example, here, we set the **Upper limit** to 500 and **Lower limit** to 0.

![](assets/troubleshooting_2.png)
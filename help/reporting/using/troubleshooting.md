---
solution: Campaign Standard
product: campaign
title: トラブルシューティング
description: 動的レポートに関するよくある質問を見つけます。
audience: reporting
content-type: reference
topic-tags: troubleshooting
feature: レポート
role: Leader
level: Intermediate
exl-id: 0f99a109-2923-4e64-8131-80fcacf79c82
source-git-commit: 81ffe6a7e59a745a6f61941dff69be85edf4fe45
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 5%

---

# トラブルシューティング{#troubleshooting}

この節では、動的レポートに関するよくある質問を確認できます。

## ユニーク開封数とユニーククリック数の場合、集計行のカウントが個々の行のカウントと一致しません{#unique-open-clicks-no-match}

これは期待された動作です。
次の例で、この動作を説明します。

プロファイルP1、P2にEメールが送信されます。

P1では最初の日に2回Eメールが開かれ、2日目にはツリー回が開かれます。

一方、P2では、最初の日に1回Eメールを開き、次の日には再度開きません。
次に、送信されたEメールとのプロファイルのインタラクションを視覚的に示します。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>開封数</strong> <br /> </th> 
   <th align="center"> <strong>個別開封数</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> 1日目<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> 2日目<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

ユニーク開封の総数を把握するには、値3を示す&#x200B;**[!UICONTROL Unique Opens]**&#x200B;の行数を合計する必要があります。 ただし、Eメールのターゲットは2つのプロファイルのみなので、開封率は150%を示すはずです。

100を超える割合を取得しないように、**[!UICONTROL Unique Opens]**&#x200B;の定義は、開かれた一意のbroadlogの数に維持されます。 この場合、P1が1日目と2日目にEメールを開封しても、そのユニーク開封数は1となります。

これにより、次の表が作成されます。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong></strong> <br /> </th> 
   <th align="center"> <strong>開封数</strong> <br /> </th> 
   <th align="center"> <strong>個別開封数</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong> Day </strong><br /> </td> 
   <td align="center"> <strong> 6  </strong><br /> </td> 
   <td align="center"> <strong> 2</strong><br /> </td>
  </tr> 
  <tr> 
   <td align="center"> 1日目<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> 2日目<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>ユニーク数はHLLベースのスケッチに基づいているので、大量のスケッチでは少し誤りが生じる可能性があります。

## 開封数がデータベース数{#open-counts-no-match-database}と一致しない

これは、**[!UICONTROL Open]**&#x200B;アクションを追跡できない場合でも、開封を追跡するために動的レポートでヒューリスティックが使用されるためです。

例えば、ユーザーがクライアント上の画像を無効にし、Eメール内のリンクをクリックした場合、**[!UICONTROL Open]**&#x200B;はデータベースで追跡されない可能性がありますが、**[!UICONTROL Click]**&#x200B;は追跡します。

したがって、**[!UICONTROL Open]**&#x200B;トラッキングログのカウントがデータベース内で同じカウントにならない場合があります。

このような発生は、**「電子メールのクリックは電子メールの開封を意味する」**&#x200B;として追加されます。

>[!NOTE]
>
>ユニークカウントはHLLベースのスケッチに基づいているので、カウント間に小さな不整合が生じる可能性があります。

## 繰り返し/トランザクション配信の件数はどのように計算されますか。{#counts-recurring-deliveries}

繰り返し配信とトランザクション配信を扱う場合、カウントは親配信と子配信の両方に関連付けられます。
**R1**という繰り返し配信を、1日目(RC1)、2日目(RC2)、3日目(RC3)に毎日実行するように設定した例を見てみましょう。
1人のユーザーのみが、すべての子配信を複数回開いたとします。 この場合、個々の繰り返し子配信では、それぞれに対して**[!UICONTROL Open]**カウントが1と表示されます。
ただし、同じ人がすべての配信をクリックしたので、親の繰り返し配信でも**[!UICONTROL Unique open]**&#x200B;が1になります。

レポートは次のようになります。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>配信</strong> <br /> </th> 
   <th align="center"> <strong>送信済み</strong> <br /> </th> 
   <th align="center"> <strong>配信済み</strong> <br /> </th>
   <th align="center"> <strong>開封数</strong> <br /> </th> 
   <th align="center"> <strong>個別開封数</strong> <br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1</strong><br/> </td> 
   <td align="center"> <strong>100</strong><br/> </td> 
   <td align="center"> <strong>90</strong><br/> </td> 
   <td align="center"> <strong>10</strong><br/> </td> 
   <td align="center"> <strong>1</strong><br/> </td> 
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

## レポートの表での色の意味は何ですか。{#reports-color-signification}

レポートに表示される色はランダム化され、パーソナライズできません。 これらは進行状況バーを表し、レポートで最大値に達した場合に強調表示されます。

次の例では、値が100%なので、セルの色が同じです。

![](assets/troubleshooting_1.png)

**[!UICONTROL Conditional formatting]**&#x200B;をカスタムに変更すると、値が上限に達した場合、セルが緑色になります。 一方、下限に達すると、値が小さくなります。

例えば、ここでは、**[!UICONTROL Upper limit]**&#x200B;を500に、**[!UICONTROL Lower limit]**&#x200B;を0に設定します。

![](assets/troubleshooting_2.png)

## レポートに「 N/A 」という値が表示されるのはなぜですか。

![](assets/troubleshooting_3.png)

値&#x200B;**N/A**&#x200B;は、動的レポートに表示される場合があります。 これは、次の3つの理由で表示できます。

* 配信は削除され、結果に矛盾が生じないように、ここに&#x200B;**N/A**&#x200B;と表示されます。
* **[!UICONTROL Transactional Delivery]**&#x200B;ディメンションをレポートにドラッグ&amp;ドロップすると、結果として&#x200B;**N/A**&#x200B;という値が表示される場合があります。 これは、動的レポートがトランザクションでない場合でもすべての配信を取得するからです。 これは、**[!UICONTROL Delivery]**&#x200B;ディメンションをレポートにドラッグ&amp;ドロップした場合にも発生しますが、この場合、**N/A**&#x200B;値はトランザクション配信を表します。
* ディメンションに関連しない指標でディメンションが使用される場合。 次の例では、この配信で&#x200B;**[!UICONTROL Click]**&#x200B;カウントが0に設定されている場合でも、**[!UICONTROL Tracking URL]**&#x200B;ディメンションで分類が追加されます。

   ![](assets/troubleshooting_4.png)


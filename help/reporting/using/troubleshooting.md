---
solution: Campaign Standard
product: campaign
title: トラブルシューティング
description: 動的なレポートに関するよくある質問を以下に示します。
audience: reporting
content-type: reference
topic-tags: troubleshooting
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# トラブルシューティング{#troubleshooting}

動的なレポートに関するよくある質問は、この節で確認できます。

## 個別の開封数と個別のクリック数の場合、集計行のカウントが個々の行のカウント{#unique-open-clicks-no-match}と一致しません

これは期待された動作です。
この動作について、次の例で説明します。

プロファイルP1,P2に電子メールを送る。

P1では、最初の日に2回電子メールを開き、2日目には2回目にツリー回を開きます。

一方、P2は最初の日に1回電子メールを開き、次の日に再度開くことはありません。
以下に、送信された電子メールとプロファイルのインタラクションを視覚的に示します。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>開封数</strong> <br /> </th> 
   <th align="center"> <strong>個別オープン</strong> <br /> </th> 
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

個別オープンの総数を把握するには、**[!UICONTROL Unique Opens]**&#x200B;の行数を合計し、値3を与える必要があります。 ただし、電子メールが2プロファイルしかターゲットにされていないので、開始率は150%と表示されます。

100を超える割合を取得しないように、**[!UICONTROL Unique Opens]**&#x200B;の定義は、開かれた一意のブロードログの数に維持されます。 この場合、P1が1日目と2日目に電子メールを開いたとしても、その個別オープンは1となります。

次の表が表示されます。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>日</strong> <br /> </th> 
   <th align="center"> <strong>開封数</strong> <br /> </th> 
   <th align="center"> <strong>個別オープン</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> 1日目<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> 2日目<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>ユニーク数は、HLLベースのスケッチに基づいているため、大きな数に関してわずかな不正確な情報が生じる場合があります。

## オープンカウントがデータベースカウント{#open-counts-no-match-database}と一致しません

これは、**[!UICONTROL Open]**&#x200B;アクションを追跡できない場合でも、ヒューリスティクスが動的レポートで開きを追跡するために使用されているためです。

例えば、ユーザーがクライアントでイメージを無効にし、電子メール内のリンクをクリックした場合、**[!UICONTROL Open]**&#x200B;はデータベースで追跡されない場合がありますが、**[!UICONTROL Click]**&#x200B;は追跡します。

したがって、**[!UICONTROL Open]**&#x200B;トラッキングログ数がデータベース内で同じ数にならない場合があります。

このような回数は&#x200B;**&quot;電子メールクリックは電子メールを開くことを意味します&quot;**&quot;と追加されます。

>[!NOTE]
>
>ユニーク数はHLLベースのスケッチに基づくので、カウント間にわずかな不一致が生じる可能性があります。

## 定期的/トランザクション配信のカウントはどのように計算されますか。{#counts-recurring-deliveries}

定期的な配信とトランザクションの配信を扱う場合、カウントは親要素と子の両方に関連付けられます。
毎日1日(RC1)、2日目(RC2)、3日目(RC3)に実行するように設定された**R1**という反復配信の例を見てみましょう。
1人の人が子配信を何度も開いたとします。 この場合、個々の繰り返し子配信には、**[!UICONTROL Open]**のカウントがそれぞれ1として表示されます。
ただし、同じ人がすべての配信をクリックしたので、親の定期的な配信の**[!UICONTROL Unique open]**&#x200B;も1になります。

レポートは次のようになります。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>配信</strong> <br /> </th> 
   <th align="center"> <strong>送信済み</strong> <br /> </th> 
   <th align="center"> <strong>配信済み</strong> <br /> </th>
   <th align="center"> <strong>開封数</strong> <br /> </th> 
   <th align="center"> <strong>個別オープン</strong> <br /> </th>
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

## 私のレポートの表には色の意味が何色で示されていますか。{#reports-color-signification}

レポートに表示される色はランダム化され、パーソナライズできません。 これらは進行状況バーを表し、レポート内で最大値に達した箇所を強調表示しやすくします。

次の例では、値が100%なので、セルの色は同じです。

![](assets/troubleshooting_1.png)

**[!UICONTROL Conditional formatting]**&#x200B;を「カスタム」に変更すると、値が上限に達した場合、セルの色が変化します。 一方、下限に達すると、値は低くなります。

例えば、ここでは、**[!UICONTROL Upper limit]**&#x200B;を500に、**[!UICONTROL Lower limit]**&#x200B;を0に設定します。

![](assets/troubleshooting_2.png)

## レポートに該当なしという値が表示されるのはなぜですか。

![](assets/troubleshooting_3.png)

値&#x200B;**N/A**&#x200B;は、動的レポートに表示される場合があります。 これは、次の2つの理由で表示される場合があります。

* 配信は削除され、**N/A**&#x200B;と表示され、結果に食い違いが生じません。
* **[!UICONTROL Transactional Delivery]**&#x200B;ディメンションをレポートにドラッグ&amp;ドロップすると、**N/A**という値が結果として表示される場合があります。 これは、動的レポートがトランザクションでない場合でもすべての配信を取得するためです。
これは、**[!UICONTROL Delivery]**&#x200B;ディメンションをレポートにドラッグ&amp;ドロップした場合にも発生しますが、この場合、**N/A**&#x200B;値はトランザクション配信を表します。

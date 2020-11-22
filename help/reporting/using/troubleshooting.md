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
source-wordcount: '665'
ht-degree: 5%

---


# トラブルシューティング{#troubleshooting}

動的なレポートに関するよくある質問は、この節で確認できます。

## 個別オープン数と個別クリック数の場合、集計行のカウントが個々の行のカウントと一致しません {#unique-open-clicks-no-match}

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

個別オープンの総数を把握するには、行数を合計し、値3を求め **[!UICONTROL Unique Opens]** る必要があります。 ただし、電子メールが2プロファイルしかターゲットにされていないので、開始率は150%と表示されます。

100を超える割合を取得しないように、の定義は、開かれた一意のブロードログの数 **[!UICONTROL Unique Opens]** に維持されます。 この場合、P1が1日目と2日目に電子メールを開いたとしても、その個別オープンは1となります。

次の表が表示されます。

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
>ユニーク数は、HLLベースのスケッチに基づいているため、大きな数に関してわずかな不正確な情報が生じる場合があります。

## オープン数がデータベース数と一致しません {#open-counts-no-match-database}

これは、アクションを追跡できない場合でも、開封を追跡するために動的レポートでヒューリスティックが使用されていることが原因である可能性があり **[!UICONTROL Open]** ます。

例えば、ユーザーがクライアントでイメージを無効にし、電子メール内のリンクをクリックした場合、データベースではイメージが追跡され **[!UICONTROL Open]** ない場合がありますが、 **[!UICONTROL Click]** ウィルでは追跡されません。

したがって、 **[!UICONTROL Open]** トラッキングログ数がデータベース内で同じ数でない場合があります。

このような回数は、「電子メールのクリックは電子メールを開くことを意味する」 **として追加され**&#x200B;ます。

>[!NOTE]
>
>ユニーク数はHLLベースのスケッチに基づくので、カウント間にわずかな不一致が生じる可能性があります。

## 定期的/トランザクション配信のカウントはどのように計算されますか。 {#counts-recurring-deliveries}

定期的な配信とトランザクションの配信を扱う場合、カウントは親要素と子の両方に関連付けられます。
毎日1日(RC1)、2日目(RC2)、3日目(RC3)に実行する **R1** という名前の反復配信の例を見てみましょう。
1人の人が子配信を何度も開いたとします。 この場合、繰り返し子配信の個々には、それぞれ1として **[!UICONTROL Open]** 数えられます。
ただし、同じ人がすべての配信をクリックしたので、親の定期的な配信にも1が割り当てら **[!UICONTROL Unique open]** れます。

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

## 私のレポートの表には色の意味が何色で示されていますか。 {#reports-color-signification}

レポートに表示される色はランダム化され、パーソナライズできません。 これらは進行状況バーを表し、レポート内で最大値に達した箇所を強調表示しやすくします。

次の例では、値が100%なので、セルの色は同じです。

![](assets/troubleshooting_1.png)

を「カスタム」 **[!UICONTROL Conditional formatting]** に変更すると、値が上限に達した場合、セルの色が変化します。 一方、下限に達すると、値は低くなります。

例えば、ここでは、を500に、 **[!UICONTROL Upper limit]** を0に設定 **[!UICONTROL Lower limit]** します。

![](assets/troubleshooting_2.png)

## レポートに該当なしという値が表示されるのはなぜですか。

![](assets/troubleshooting_3.png)

値 **N/A** は、動的レポートに表示される場合があります。 これは、次の2つの理由で表示される場合があります。

* 配信が削除され、結果に食い違いが生じないように **N/A** と表示されます。
* ディメンションをレポートにドラッグ&amp;ドロップすると **[!UICONTROL Transactional Delivery]** 、結果として値 **N/A** が表示される場合があります。 これは、動的レポートがトランザクションでない場合でもすべての配信を取得するためです。
これは、ディメンションをレポートにドラッグ&amp;ドロップした場合にも発生する可能性があり **[!UICONTROL Delivery]** ますが、この場合、 **該当なし** 値はトランザクション配信を表します。

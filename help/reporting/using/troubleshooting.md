---
title: トラブルシューティング
description: 動的なレポートに関するよくある質問を見つけます。
page-status-flag: never-activated
uuid: a84a18bd-4e33-466e-a6ce-d7008fe12746
contentOwner: beneat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: troubleshooting
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 001fc2df11e32bdcc31dfe917884460b4d3de541

---


# トラブルシューティング{#troubleshooting}

この節では、動的なレポートに関するよくある質問を示します。

## 個別オープン数と個別クリック数の場合、集計行のカウントが個々の行のカウントと一致しません {#unique-open-clicks-no-match}

これは期待された動作です。
この動作を説明するには、次の例を使用します。

電子メールがプロファイルP1,P2に送信される。

P1は最初の日に電子メールを2回開き、2日目には2回目の電子メールをツリーします。

一方、P2は最初の日に1回電子メールを開き、次の日に再度開くことはありません。
送信された電子メールとのプロファイルのインタラクションを視覚的に示します。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>開封数</strong> <br /> </th> 
   <th align="center"> <strong>個別オープン</strong><br /> </th> 
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

ユニークオープンの総数を把握するには、行数を合計し、値3 **[!UICONTROL Unique Opens]** を得る必要があります。 ただし、電子メールのターゲットは2プロファイルのみなので、開封率は150%と表示されます。

100を超える割合を取得しない場合、の定義は、開か **[!UICONTROL Unique Opens]** れた一意のブロードログの数に維持されます。 この場合、P1が1日目と2日目に電子メールを開いた場合でも、ユニークオープンは1となります。

次の表が表示されます。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>開封数</strong> <br /> </th> 
   <th align="center"> <strong>個別オープン</strong><br /> </th> 
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
>ユニーク数はHLLベースのスケッチに基づいているので、大きな数に関しては若干の不正確さが生じる可能性があります。

## オープン数がデータベース数と一致しません {#open-counts-no-match-database}

これは、アクションを追跡できない場合でも、開封を追跡するために、ヒューリスティクスが動的レポートで使用されることが原因の可能性があ **[!UICONTROL Open]** ります。

例えば、ユーザーがクライアントで画像を無効にし、電子メール内のリンクをクリックした場合、データベースでは追跡さ **[!UICONTROL Open]** れない場合がありますが、その場合は追跡され **[!UICONTROL Click]** ません。

したがって、トラッキングログ数 **[!UICONTROL Open]** がデータベース内で同じ数でない場合があります。

このような回数は、「電子メールのク **リックは電子メールを開くことを意味します」として追加されま**&#x200B;す。

>[!NOTE]
>
>ユニーク数はHLLベースのスケッチに基づくので、カウント間にわずかな矛盾が生じる可能性があります。

## 私の報告書の表の中の色の意味は何ですか？ {#reports-color-signification}

レポートに表示される色はランダム化され、パーソナライズできません。 レポート内で最大値に達した場合に強調表示され、進捗バーが表示されます。

次の例では、値が100%なので、セルの色は同じです。

![](assets/troubleshooting_1.png)

を「カスタム」に変 **[!UICONTROL Conditional formatting]** 更すると、値が上限に達すると、セルの色が変わります。 一方、下限に達すると、値が低くなります。

例えば、ここではを500に設定し、 **[!UICONTROL Upper limit]** を0に設定 **[!UICONTROL Lower limit]** します。

![](assets/troubleshooting_2.png)

## 値N/Aがレポートに表示されるのはなぜですか。

![](assets/troubleshooting_3.png)

値 **N/Aは、動的レ** ポートに表示されることがあります。 これは、次の2つの理由で表示されます。

* 配信が削除され、結果に不一致が生じないように **N/A** （該当なし）と表示されます。
* ディメンションをレポー **[!UICONTROL Transactional Delivery]** トにドラッグ&amp;ドロップすると、 **N/A** という値が結果として表示されます。 これは、動的レポートがトランザクションでない場合でも、すべての配信を取得するためです。
これは、ディメンションをレポートにドラッグ&amp;ドロ **[!UICONTROL Delivery]** ップした場合にも発生する可能性がありますが、この場合、 **** N/A値はトランザクション配信を表します。

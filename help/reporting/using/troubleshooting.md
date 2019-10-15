---
title: トラブルシューティング
seo-title: トラブルシューティング
description: トラブルシューティング
seo-description: 動的レポートに関するよくある質問を以下に示します。
page-status-flag: 非活性化の
uuid: a84a18bd-4e33-466e-a6ce-d7008fe12746
contentOwner: 楽しい
products: SG_CAMPAIGN/STANDARD
audience: レポート
content-type: 参照
topic-tags: トラブルシューティング
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0ccb6df9b3de49baf1a230547c33f5d2246c0e85

---


# トラブルシューティング{#troubleshooting}

この節では、動的レポートに関するよくある質問を示します。

## 個別オープンと個別クリックの場合、集計行のカウントが個々の行のカウントと一致しません {#unique-open-clicks-no-match}

これは期待された動作です。
この動作を説明するには、次の例を使用します。

プロファイルP1、P2に電子メールが送信される。

P1では、最初の日に電子メールを2回開き、2日目には2回目の電子メールをツリー表示します。

一方、P2は最初の日に1回電子メールを開き、翌日に再び開くことはありません。
送信された電子メールとのプロファイルのインタラクションを視覚的に表したものを次に示します。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>日</strong><br /> </th> 
   <th align="center"> <strong>開く</strong><br /> </th> 
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

ユニークオープンの総数を把握するには、行数を合計し、値3 **[!UICONTROL Unique Opens]** を得る必要があります。 しかし、電子メールが2つのプロファイルのみをターゲットにしているので、オープン率は150%と表示されます。

100を超える割合を取得しない場合、の定義は、開か **[!UICONTROL Unique Opens]** れた一意のブロードログの数に維持されます。 この場合、P1が1日目と2日目に電子メールを開いたとしても、その個別オープンは1となります。

これにより、次の表が作成されます。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>日</strong><br /> </th> 
   <th align="center"> <strong>開く</strong><br /> </th> 
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
>ユニーク数はHLLベースのスケッチに基づいているので、多くの場合にわずかな不正確さが生じる可能性があります。

## オープン数がデータベース数と一致しません {#open-counts-no-match-database}

これは、アクションを追跡できない場合でも、開封を追跡するために動的レポートでヒューリスティックが使用されることが原因の可能性があ **[!UICONTROL Open]** ります。

例えば、ユーザーがクライアントでイメージを無効にし、電子メール内のリンクをクリックした場合、データベースではイメージが追跡されな **[!UICONTROL Open]** い場合がありますが、その場合はウィル **[!UICONTROL Click]** です。

したがって、トラッ **[!UICONTROL Open]** キングログのカウントがデータベース内で同じカウントにならない場合があります。

このような回数は、「電子メールのク **リックは電子メールを開くことを意味します」として追加されま**&#x200B;す。

>[!NOTE]
>
>ユニーク数はHLLベースのスケッチに基づくので、カウント間に小さな不整合が生じる可能性があります。

## 定期的/トランザクション配信の数はどのように計算されますか。

繰り返し配信とトランザクション配信を扱う場合、カウントは親配信と子配信の両方に関連付けられます。

毎日1日目(RC1)、2日目 **(RC2)、3日目(RC3)に実行するように設定された** R1という反復配信の例を見てみましょう。

1人の人だけが、すべての子供の配達を複数回開いたとします。 この場合、繰り返し配信される個々の子の配信では、それぞれに対し **[!UICONTROL Open]** て1としてカウントされます。

ただし、同じ人がすべての配信をクリックしたので、親の定期的な配信も1にな **[!UICONTROL Unique open]** ります。

Adobe Campaign Standard 19.2.1リリース以降、実数の定義は、配信と対話する実人数から **実行される実メッセージ数** ( **Number of unique persons interacted with** Nuque **of** Messages interacted)に変更されました。

Adobe Campaign Standard 19.2.1リリースより前のレポートは次のようになりました。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>配信</strong><br /> </th> 
   <th align="center"> <strong>送信済</strong><br /> </th> 
   <th align="center"> <strong>配信済</strong><br /> </th>
   <th align="center"> <strong>開く</strong><br /> </th> 
   <th align="center"> <strong>個別オープン</strong><br /> </th>
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

Adobe Campaign Standard 19.2.1リリース以降のレポートは次のようになります。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>配信</strong><br /> </th> 
   <th align="center"> <strong>送信済</strong><br /> </th> 
   <th align="center"> <strong>配信済</strong><br /> </th>
   <th align="center"> <strong>開く</strong><br /> </th> 
   <th align="center"> <strong>個別オープン</strong><br /> </th>
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

## 私の報告書の表には、色の意味は何でしょう？ {#reports-color-signification}

レポートに表示される色はランダム化され、パーソナライズできません。 これらはプログレスバーを表し、レポートで最大限に達した値を強調表示するのに役立ちます。

次の例では、値が100%なので、セルの色は同じです。

![](assets/troubleshooting_1.png)

を「カスタム」に変 **[!UICONTROL Conditional formatting]** 更すると、値が上限に達した場合、セルの色が変わります。 一方、下限に達すると、値が低下します。

例えば、ここでは、を500に、 **[!UICONTROL Upper limit]** **を0に設定します[!UICONTROL Lower limit**] 。

![](assets/troubleshooting_2.png)

## レポートに該当なしという値が表示されるのはなぜですか。

![](assets/troubleshooting_3.png)

値 **N/Aは、動的レ** ポートに表示されることがあります。 これは、次の2つの理由で表示されます。

* 配信が削除され、結果に不一致が生じないよう **に「該当なし** 」と表示されます。
* ディメンションをレポートにド **[!UICONTROL Transactional Delivery]** ラッグ&amp;ドロップすると、結果とし **てN/A** という値が表示される場合があります。 これは、動的レポートがトランザクションでない場合でもすべての配信を取得するためです。
これは、ディメンションをレポートにドラッグ&amp;ドロ **[!UICONTROL Delivery]** ップした場合にも発生する可能性がありますが、この場合、 **** N/A値はトランザクション配信を表します。

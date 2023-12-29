---
title: 動的レポートのトラブルシューティング
description: 動的レポートに関するよくある質問を見つけます。
audience: reporting
content-type: reference
topic-tags: troubleshooting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 0f99a109-2923-4e64-8131-80fcacf79c82
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 1%

---

# トラブルシューティング{#troubleshooting}

この節では、動的レポートに関するよくある質問を示します。

## ユニーク開封数およびユニーククリック数の場合、集計行の数が個々の行の数と一致しません {#unique-open-clicks-no-match}

これは期待された動作です。
次の例で、この動作を説明します。

プロファイル P1 および P2 に E メールが送信されます。

P1 は最初の日に E メールを 2 回開き、2 日目にはツリー回開きます。

一方、P2 では、最初の日に 1 回 E メールを開き、次の日には E メールを再度開きません。
以下は、送信された E メールとのプロファイルのインタラクションを視覚的に表したものです。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>日</strong> <br /> </th> 
   <th align="center"> <strong>開封数</strong> <br /> </th> 
   <th align="center"> <strong>ユニーク開封数</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> 1 日目<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> 2 日目<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

ユニーク開封数全体を把握するには、行数を合計する必要があります。 **[!UICONTROL Unique Opens]** これは 3 の値を与えます。 ただし、E メールのターゲットは 2 つのプロファイルのみなので、開封率は 150%と表示されます。

100 を超える割合を取得しない場合、 **[!UICONTROL Unique Opens]** は、開かれた一意の broadlog の数で維持されます。 この場合、P1 が Day 1 と Day 2 で E メールを開封しても、そのユニーク開封数は 1 となります。

これにより、次の表が作成されます。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong></strong> <br /> </th> 
   <th align="center"> <strong>開封数</strong> <br /> </th> 
   <th align="center"> <strong>ユニーク開封数</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong> 日 </strong><br /> </td> 
   <td align="center"> <strong> 6 </strong><br /> </td> 
   <td align="center"> <strong> 2</strong><br /> </td>
  </tr> 
  <tr> 
   <td align="center"> 1 日目<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> 2 日目<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>ユニーク数は HLL ベースのスケッチに基づいているため、大きな数では少し誤りが生じる場合があります。

## 開封数がデータベース数と一致しません {#open-counts-no-match-database}

これは、追跡できない場合でも、開封を追跡するために動的レポートでヒューリスティックが使用されることが原因である可能性があります **[!UICONTROL Open]** アクション。

例えば、ユーザーがクライアント上の画像を無効にし、E メール内のリンクをクリックした場合、 **[!UICONTROL Open]** はデータベースで追跡できないが、 **[!UICONTROL Click]** は、

したがって、 **[!UICONTROL Open]** トラッキングログの数がデータベース内で同じ数でない可能性があります。

このような発生は、次のように追加されます。 **「メールのクリックはメールの開封を意味する」**.

>[!NOTE]
>
>ユニーク数は HLL ベースのスケッチに基づくため、カウント間に小さな不整合が生じる可能性があります。

## 繰り返し配信/トランザクション配信のカウントはどのように計算されますか？ {#counts-recurring-deliveries}

繰り返し配信とトランザクション配信を扱う場合、カウントは親配信と子配信の両方に関連付けられます。
例えば、という名前の繰り返し配信の場合、 **R1** は、毎日 1 日目 (RC1)、2 日目 (RC2)、3 日目 (RC3) に実行するように設定されます。
1 人のユーザーのみがすべての子配信を複数回開いたとします。 この場合、個々の繰り返し子配信には **[!UICONTROL Open]** はそれぞれ 1 としてカウントされます。
ただし、同じ人がすべての配信をクリックしたので、親の繰り返し配信にも **[!UICONTROL Unique open]** を 1 として設定します。

レポートは次のようになります。

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>配信</strong> <br /> </th> 
   <th align="center"> <strong>送信済み</strong> <br /> </th> 
   <th align="center"> <strong>配信済み</strong> <br /> </th>
   <th align="center"> <strong>開封数</strong> <br /> </th> 
   <th align="center"> <strong>ユニーク開封数</strong> <br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1</strong><br/> </td> 
   <td align="center"> <strong>100</strong><br/> </td> 
   <td align="center"> <strong>90</strong><br/> </td> 
   <td align="center"> <strong>10</strong><br/> </td> 
   <td align="center"> <strong>3</strong><br/> </td> 
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

## レポートの表での色の意味は何ですか。 {#reports-color-signification}

レポートに表示される色はランダム化されており、パーソナライズできません。 これらは進行状況バーを表し、レポートで最大到達値をより適切に強調表示するために表示されます。

次の例では、値が 100%なので、セルの色が同じです。

![](assets/troubleshooting_1.png)

次の項目を変更した場合、 **[!UICONTROL Conditional formatting]** をカスタムに設定すると、値が上限に達した場合、セルの色が緑に変わります。 一方、下限に達すると、低下します。

例えば、ここでは、 **[!UICONTROL Upper limit]** を 500 に設定し、 **[!UICONTROL Lower limit]** を 0 に設定します。

![](assets/troubleshooting_2.png)

## レポートに値「 N/A 」が表示されるのはなぜですか。

![](assets/troubleshooting_3.png)

値 **該当なし** は、動的レポートに表示されることがあります。 これは、次の 3 つの理由で表示できます。

* 配信は削除され、ここには次のように表示されます。 **該当なし** 結果に食い違いを生じさせない
* ドラッグ&amp;ドロップ時に、 **[!UICONTROL Transactional Delivery]** ディメンションをレポートに適用する場合は、値 **該当なし** 結果として表示される場合があります。 これは、動的レポートがトランザクションでない場合でもすべての配信を取得するからです。 この問題は、 **[!UICONTROL Delivery]** ディメンションを指定しますが、この場合は **該当なし** 値はトランザクション配信を表します。
* ディメンションと関連しない指標でディメンションが使用される場合。 以下の例では、 **[!UICONTROL Tracking URL]** 次元 ( **[!UICONTROL Click]** この配信で count が 0 に設定されています。

  ![](assets/troubleshooting_4.png)

## 配信のレポートで、カスタムターゲットマッピングを使用すると不完全なデータが表示される

読み込まれたカスタムの Target マッピングを配信で使用していて、異なるレポートにデータが表示されない場合は、それらの Target マッピングに対してレポートエンリッチメントが作成されていなかった可能性があります。

これを解決するには：

* XML から Target マッピングを読み込んだ後、レポートエンリッチメントも読み込む必要があります。

* Target マッピングを読み込む代わりに、Adobe Campaign Standardで直接作成して、レポートエンリッチメントを自動的に作成できます。

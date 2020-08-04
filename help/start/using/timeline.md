---
title: タイムライン
description: Adobe Campaign Standard インターフェイスを使用して、進行中のプログラムとそのコンテンツを視覚化する方法について説明します。
page-status-flag: never-activated
uuid: ffa0a63a-2e77-45c0-8e60-212f7aaeb447
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: marketing-plans
discoiquuid: 53e3db10-5fed-4fc3-b41e-5226f1e05246
context-tags: campaignCalendar,main
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '380'
ht-degree: 100%

---


# タイムライン{#timeline}

**[!UICONTROL Timeline]**&#x200B;により、進行中のプログラムとそのコンテンツを視覚化できます。

タイムラインにアクセスするには、ホームページで対応するカードをクリックします。

デフォルトの場合、タイムラインには単にプログラムの詳細が表示され、定義された開始日から終了日までの間の時系列が示されます。

各プログラムは、それぞれ対応するサムネールとラベルが入ったボックスで表されます。表示する画面のサイズと要素の数に応じて、ラベルはプログラム ID に置き換えることができます。

![](assets/timeline_1.png)

青い縦線は、現在の日付をハイライト表示する時系列マーカーです。デフォルトでは、画面の中央に置かれます。画面上で左右にスクロールすると、表示期間を変更することができます。

![](assets/timeline_zoom_in.png) ボタンと ![](assets/timeline_zoom_out.png) ボタンを使用すると、境界を広げたり、狭めたりすることができます。![](assets/timeline_zoom_in.png) ボタンは、期間を限定しながら、日にち単位が表示されるまで詳細レベルを上げます。一方、![](assets/timeline_zoom_out.png) ボタンではより長い期間を表示することができます。

各プログラム名の右にある矢印をクリックして、対応するコンテンツを表示します。プログラムには、サブプログラム、キャンペーン、ランディングページを含めることができます。キャンペーンは、プログラムと同じ方法でデプロイされ、内部に E メール、SMS、ランディングページを組み込むことができます。

>[!NOTE]
>
>ワークフローには日付に関する特定の概念がないため、タイムラインには表示されません。

プログラムやキャンペーンのコンテンツが表示されている場合、対応するボックスが青に変わり、右側の矢印が逆になります。矢印を再度クリックすると、コンテンツが非表示になります。

![](assets/timeline_2.png)

各要素には、それぞれのタイプに対応するアイコンがあります。

* ![](assets/timeline_program_icon.png)：プログラム
* ![](assets/timeline_campaign_icon.png)：キャンペーン
* ![](assets/timeline_lp_icon.png)：ランディングページ
* ![](assets/timeline_email_icon.png)：E メール
* ![](assets/timeline_sms_icon.png)：SMS
* ![](assets/timeline_push_icon.png)：プッシュ通知

各ボックスの左の境界線にある色付きの線は、関連する要素のステータスを示しています。

* 要素がまだ開始されていない場合、線はグレーになります。
* 要素が進行中の場合、線は青色で表示されます。
* 要素が完了すると、線が緑色に変わります。

プログラム、または表示されたその他の要素をクリックすると、対応するカードが表示されます。次に、カードをクリックして、選択された要素のコンテンツに直接移動し、変更します。

![](assets/timeline_3.png)

画面内の任意の場所をクリックすると、カードが非表示になります。

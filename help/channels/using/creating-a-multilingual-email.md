---
solution: Campaign Standard
product: campaign
title: 多言語 E メールの作成
description: 異なる好みの言語を使用して、多言語の電子メールターゲット受信者を作成するには、次の手順に従います。
audience: channels
content-type: reference
topic-tags: email-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 25%

---


# 多言語 E メールの作成{#creating-a-multilingual-email}

希望する言語が異なるプロファイルには、多言語の電子メールを送信できます。各プロファイルは、好みの言語で電子メールのバリエーションを受け取ります。

これを行うには、多言語の電子メールテンプレートが使用可能であることを確認します。 そうでない場合は、[このセクション](../../channels/using/multilingual-messages-template.md)で作成する方法を学びます。

オーディエンスは、完成した優先言語情報を持つプロファイルに基づいている。

1. [多言語テンプレート](../../channels/using/multilingual-messages-template.md)を基にして新しい電子メールを作成します。

   ![](assets/multi_create1.png)

1. 通常の E メールと同様に、E メールの一般的なプロパティとターゲットオーディエンスを定義します。[オーディエンスの作成](../../audiences/using/creating-audiences.md)の節を参照してください。
1. 作成ウィザードの4番目の手順で、バリアントオプションを定義します。 [多言語テンプレート](../../channels/using/multilingual-messages-template.md)にすべての適切なパラメーターが既に含まれている場合は、「**[!UICONTROL Create]**」ボタンを直接クリックできます。

   ![](assets/multi_create4.png)

   必要に応じて、**[!UICONTROL Add an element]**&#x200B;ボタンを使用してバリアントを追加します。 **[!UICONTROL Default]** バリアントは削除できません。**[!UICONTROL default]**&#x200B;に設定した場合、[プロファイルの推奨言語](../../audiences/using/creating-profiles.md)を使用して、バリアントが選択されます。 **[!UICONTROL Default]**&#x200B;バリアントを他の言語に設定することもできます。

1. 電子メールの作成を確認する：電子メールダッシュボードが表示されます。
1. 各バリアントの電子メールコンテンツを定義します。 選択したテンプレートに応じて、複数の件名、複数の送信者名または複数の異なる内容を定義できます。ドロップダウンメニューを使用して、要素の異なるバリエーション間を移動します。 詳しくは、[コンテンツエディター](../../designing/using/designing-content-in-adobe-campaign.md)の節を参照してください。

   ![](assets/multi_selectcontent.png)

1. メッセージをテストし、検証します。 [配達確認](../../sending/using/sending-proofs.md)の送信の節を参照してください。
1. **[!UICONTROL Send after confirmation option]**&#x200B;で送信のスケジュールを設定します。
1. 電子メールが送信されたら、その電子メールのログやレポートにアクセスして、キャンペーンの成功度を測定できます。 レポートについて詳しくは、[この節](../../reporting/using/about-dynamic-reports.md)を参照してください。

**関連トピック：**

* [1つのワークフローで多言語オーディエンスにアクセス](https://helpx.adobe.com/jp/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)

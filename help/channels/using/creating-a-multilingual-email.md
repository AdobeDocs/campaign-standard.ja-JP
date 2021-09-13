---
title: 多言語 E メールの作成
description: 優先言語が異なる受信者をターゲティングする多言語のEメールを作成するには、次の手順に従います。
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Intermediate
exl-id: fcf192cb-f2d5-4340-bc2f-add0c195ad4e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 25%

---

# 多言語 E メールの作成{#creating-a-multilingual-email}

様々な優先言語のプロファイルに多言語のEメールを送信できます。各プロファイルは、優先言語のeメールのバリアントを受け取ります。

これをおこなうには、多言語のEメールテンプレートが使用可能であることを確認します。 そうでない場合は、[この節](../../channels/using/multilingual-messages-template.md)で作成する方法を学びます。

オーディエンスは、完成した優先言語情報を持つプロファイルに基づきます。

1. [多言語テンプレート](../../channels/using/multilingual-messages-template.md)に基づいて新しいEメールを作成します。

   ![](assets/multi_create1.png)

1. 通常の E メールと同様に、E メールの一般的なプロパティとターゲットオーディエンスを定義します。[オーディエンスの作成](../../audiences/using/creating-audiences.md)の節を参照してください。
1. 作成ウィザードの4番目の手順で、バリアントオプションを定義します。 [多言語テンプレート](../../channels/using/multilingual-messages-template.md)に既に正しいパラメーターがすべて含まれている場合は、「**[!UICONTROL Create]**」ボタンを直接クリックできます。

   ![](assets/multi_create4.png)

   必要に応じて、**[!UICONTROL Add an element]**&#x200B;ボタンを使用してバリアントを追加します。 **[!UICONTROL Default]** バリアントは削除できません。**[!UICONTROL default]**&#x200B;に設定した場合、[プロファイルの優先言語](../../audiences/using/creating-profiles.md)を使用してバリアントが選択されます。 **[!UICONTROL Default]**&#x200B;バリアントを他の言語に設定することもできます。

1. Eメールの作成を確認します。eメールダッシュボードが表示されます。
1. 各バリアントのEメールコンテンツを定義します。 選択したテンプレートに応じて、複数の件名、複数の送信者名または複数の異なる内容を定義できます。ドロップダウンメニューを使用して、要素の様々なバリエーション間を移動します。 詳しくは、[コンテンツエディター](../../designing/using/designing-content-in-adobe-campaign.md)の節を参照してください。

   ![](assets/multi_selectcontent.png)

1. メッセージをテストして検証します。 [配達確認の送信](../../sending/using/sending-proofs.md)の節を参照してください。
1. **[!UICONTROL Send after confirmation option]**&#x200B;で送信のスケジュールを設定します。
1. Eメールが送信されたら、ログとレポートにアクセスして、キャンペーンの成功を測定できます。 レポートについて詳しくは、[この節](../../reporting/using/about-dynamic-reports.md)を参照してください。

**関連トピック：**

* [1つのワークフローを使用した多言語オーディエンスへのリーチ](https://helpx.adobe.com/jp/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)

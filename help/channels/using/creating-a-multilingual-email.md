---
title: 多言語メールの作成
description: 次の手順に従って、様々な優先言語を持つ受信者をターゲットとする多言語メールを作成します。
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Intermediate
exl-id: fcf192cb-f2d5-4340-bc2f-add0c195ad4e
TQID: https://experienceleague.adobe.com/dz14KptzZtyP8Oo-RaYvZKP5D3L4akcJJmY2f-p1nuE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 24%

---

# 多言語メールの作成{#creating-a-multilingual-email}

多言語メールを異なる優先言語のプロファイルに送信できます。各プロファイルには、それぞれの優先言語のメールのバリエーションが送信されます。

これには、多言語メールテンプレートが用意されていることを確認します。 そうでない場合は、[このセクション ](../../channels/using/multilingual-messages-template.md)で作成方法を説明します。

オーディエンスは、完了した優先言語情報を持つプロファイルにもとづいています。

1. [多言語テンプレート ](../../channels/using/multilingual-messages-template.md)に基づいて新しいメールを作成します。

   ![](assets/multi_create1.png)

1. 通常のメールと同様に、メールの一般的なプロパティとターゲットオーディエンスを定義します。 [オーディエンスの作成](../../audiences/using/creating-audiences.md)の節を参照してください。

1. 作成ウィザードの4番目の手順で、バリエーションのオプションを定義します。 [多言語テンプレート ](../../channels/using/multilingual-messages-template.md)に適切なパラメーターがすべて既に含まれている場合は、**[!UICONTROL Create]** ボタンを直接クリックできます。

   ![](assets/multi_create4.png)

   必要に応じて、**[!UICONTROL Add an element]** ボタンを使用してバリエーションを追加します。 **[!UICONTROL Default]** バリアントは削除できません。 **[!UICONTROL default]**&#x200B;に設定すると、[ プロファイルの優先言語](../../audiences/using/creating-profiles.md)がバリエーションの選択に使用されます。 **[!UICONTROL Default]** バリエーションを他の言語に設定することもできます。

1. メール作成を確認する：メールダッシュボードが表示されます。
1. 各バリエーションに合わせて電子メールコンテンツを定義： 選択したテンプレートに応じて、複数の件名、複数の送信者名または複数の異なる内容を定義できます。 ドロップダウンメニューを使用して、エレメントの様々なバリエーション間を移動します。 詳しくは、[コンテンツエディター](../../designing/using/designing-content-in-adobe-campaign.md)の節を参照してください。

   ![](assets/multi_selectcontent.png)

1. メッセージをテストして検証する。 「[ プルーフの送信](../../sending/using/sending-proofs.md)」セクションを参照してください。
1. **[!UICONTROL Send after confirmation option]**&#x200B;との送信をスケジュールします。
1. 電子メールを送信した後は、そのログやレポートにアクセスして、キャンペーンの成果を測定できます。 レポートについて詳しくは、[この節](../../reporting/using/about-dynamic-reports.md)を参照してください。


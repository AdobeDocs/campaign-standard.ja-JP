---
title: 多言語電子メールの作成
description: 様々な言語を使用する受信者を対象とした多言語電子メールを作成するには、次の手順に従います。
page-status-flag: never-activated
uuid: e90f4ec8-14e3-4304-b5fc-bce0ba08a4ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: 79231445-1d51-499a-adcf-0c0f6db1cfa3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b70e18be29fd48d102313f6d741e9ffe053cc34

---


# 多言語電子メールの作成{#creating-a-multilingual-email}

様々な言語のプロファイルに多言語電子メールを送信できます。各プロファイルは、好みの言語で電子メールのバリエーションを受け取ります。

これを行うには、多言語の電子メールテンプレートが使用可能であることを確認します。 そうでない場合は、この節で作成方法を説 [明します](../../start/using/creating-a-multilingual-template.md)。

オーディエンスは、完成した優先言語情報を持つプロファイルに基づいています。

1. 多言語テンプレートに基づいて新しい電子メ [ールを作成](../../start/using/creating-a-multilingual-template.md)。

   ![](assets/multi_create1.png)

1. 標準電子メールと同様に、電子メールの一般プロパティとターゲットオーディエンスを定義します。 「オーディエンスの作成 [」の節を参照](../../audiences/using/creating-audiences.md) 。
1. 作成ウィザードの4番目の手順で、バリアントオプションを定義します。 多言語テンプ [レートに](../../start/using/creating-a-multilingual-template.md) 、すべての適切なパラメーターが既に含まれている場合は、ボタンを直接クリックで **[!UICONTROL Create]** きます。

   ![](assets/multi_create4.png)

   必要に応じて、ボタンを使用してバリアントを追 **[!UICONTROL Add an element]** 加します。 **[!UICONTROL Default]** バリアントは削除できません。 に設定すると、プロ **[!UICONTROL default]**&#x200B;ファ [イルの優先言語を使用して](../../audiences/using/creating-profiles.md) 、バリアントが選択されます。 バリアントを他の言語に設 **[!UICONTROL Default]** 定することもできます。

1. 電子メールの作成を確認：電子メールダッシュボードが表示されます。
1. 各バリアントの電子メールコンテンツを定義します。 選択したテンプレートに応じて、複数の主題、複数の送信者名、または複数の異なるコンテンツを定義できます。 ドロップダウンメニューを使用して、要素の異なるバリエーション間を移動します。 詳しくは、「コンテンツエディター」の節 [を参照してくださ](../../designing/using/designing-content-in-adobe-campaign.md) い。

   ![](assets/multi_selectcontent.png)

1. メッセージをテストし、検証します。 「証明の送信」の節 [を参照してください](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) 。
1. と共に送信をスケジュールしま **[!UICONTROL Send after confirmation option]**&#x200B;す。
1. 電子メールの送信後は、その電子メールのログやレポートにアクセスして、キャンペーンの成功度を測定できます。 For more on reporting, refer to [this section](../../reporting/using/about-dynamic-reports.md).

**関連トピック：**

* [1つのワークフローを使用した多言語オーディエンスの提供](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)

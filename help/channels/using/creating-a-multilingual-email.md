---
title: 多言語メールの作成
description: 次の手順に従って、様々な優先言語を使用して多言語のメールターゲティング受信者を作成します。
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Intermediate
exl-id: fcf192cb-f2d5-4340-bc2f-add0c195ad4e
source-git-commit: d234d7fab039b602eff06c03ba0d8f7ce2a0cf3f
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 24%

---

# 多言語メールの作成{#creating-a-multilingual-email}

優先言語が異なるプロファイルに多言語メールを送信できます。各プロファイルは、優先言語のメールのバリアントを受け取ります。

そのためには、多言語のメールテンプレートが使用可能であることを確認します。 そうでない場合は、[ この節 ](../../channels/using/multilingual-messages-template.md) で作成する方法を参照してください。

オーディエンスは、設定言語情報が完了したプロファイルに基づいています。

1. [ 多言語テンプレート ](../../channels/using/multilingual-messages-template.md) に基づいて新規メールを作成します。

   ![](assets/multi_create1.png)

1. 通常のメールと同様に、メールの一般的なプロパティとターゲットオーディエンスを定義します。[オーディエンスの作成](../../audiences/using/creating-audiences.md)の節を参照してください。

1. 作成ウィザードの 4 番目の手順で、バリアントオプションを定義します。 [ 多言語テンプレート ](../../channels/using/multilingual-messages-template.md) にすべての適切なパラメーターが既に含まれている場合は、「**[!UICONTROL Create]**」ボタンを直接クリックできます。

   ![](assets/multi_create4.png)

   必要に応じて、「**[!UICONTROL Add an element]**」ボタンでバリアントを追加します。 バ **[!UICONTROL Default]** アントは削除できません。 **[!UICONTROL default]** に設定すると、[ プロファイルの優先言語 ](../../audiences/using/creating-profiles.md) を使用してバリアントが選択されます。 **[!UICONTROL Default]** バリアントを他の言語に設定することもできます。

1. メールの作成を確認：メールダッシュボードが表示されます。
1. 各バリアントのメールコンテンツを定義します。 選択したテンプレートに応じて、複数の件名、複数の送信者名または複数の異なる内容を定義できます。ドロップダウンメニューを使用して、要素の異なるバリアント間を移動します。 詳しくは、[コンテンツエディター](../../designing/using/designing-content-in-adobe-campaign.md)の節を参照してください。

   ![](assets/multi_selectcontent.png)

1. メッセージをテストし検証します。 [ 配達確認の送信 ](../../sending/using/sending-proofs.md) の節を参照してください。
1. **[!UICONTROL Send after confirmation option]** での送信のスケジュールを設定します。
1. メールが送信されると、そのログとレポートにアクセスして、キャンペーンの成功を測定できます。 レポートについて詳しくは、[この節](../../reporting/using/about-dynamic-reports.md)を参照してください。


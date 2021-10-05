---
title: 多言語 E メールの作成
description: 次の手順に従って、優先言語が異なる受信者をターゲティングする多言語の E メールを作成します。
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Intermediate
exl-id: fcf192cb-f2d5-4340-bc2f-add0c195ad4e
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 24%

---

# 多言語 E メールの作成{#creating-a-multilingual-email}

多言語の E メールを、様々な優先言語のプロファイルに送信できます。各プロファイルは、E メールのバリエーションを優先言語で受け取ります。

これをおこなうには、多言語の E メールテンプレートが使用可能であることを確認します。 そうでない場合は、[ この節 ](../../channels/using/multilingual-messages-template.md) で作成する方法を学びます。

オーディエンスは、優先言語に関する完全な情報を持つプロファイルに基づいています。

1. [ 多言語テンプレート ](../../channels/using/multilingual-messages-template.md) に基づいて新しい E メールを作成します。

   ![](assets/multi_create1.png)

1. 通常の E メールと同様に、E メールの一般的なプロパティとターゲットオーディエンスを定義します。[オーディエンスの作成](../../audiences/using/creating-audiences.md)の節を参照してください。
1. 作成ウィザードの 4 番目の手順で、バリアントオプションを定義します。 [ 多言語テンプレート ](../../channels/using/multilingual-messages-template.md) に既に正しいパラメーターがすべて含まれている場合は、「**[!UICONTROL Create]**」ボタンを直接クリックできます。

   ![](assets/multi_create4.png)

   必要に応じて、**[!UICONTROL Add an element]** ボタンを使用してバリアントを追加します。 **[!UICONTROL Default]** バリアントは削除できません。**[!UICONTROL default]** に設定した場合、[ プロファイルの優先言語 ](../../audiences/using/creating-profiles.md) を使用してバリアントが選択されます。 **[!UICONTROL Default]** バリアントを他の言語に設定することもできます。

1. E メールの作成を確認します。電子メールダッシュボードが表示されます。
1. 各バリアントの E メールコンテンツを定義します。 選択したテンプレートに応じて、複数の件名、複数の送信者名または複数の異なる内容を定義できます。ドロップダウンメニューを使用して、要素の様々なバリエーション間を移動します。 詳しくは、[コンテンツエディター](../../designing/using/designing-content-in-adobe-campaign.md)の節を参照してください。

   ![](assets/multi_selectcontent.png)

1. メッセージをテストして検証します。 [ 配達確認の送信 ](../../sending/using/sending-proofs.md) の節を参照してください。
1. **[!UICONTROL Send after confirmation option]** で送信のスケジュールを設定します。
1. E メールが送信されたら、ログとレポートにアクセスして、キャンペーンの成功を測定できます。 レポートについて詳しくは、[この節](../../reporting/using/about-dynamic-reports.md)を参照してください。


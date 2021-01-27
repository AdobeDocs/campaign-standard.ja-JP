---
solution: Campaign Standard
product: campaign
title: 送信者に返信
description: 間違ったアドレスを通知し、それを今後の通信から除外する方法を説明します。
audience: channels
content-type: reference
topic-tags: direct-mail
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---


# 送信者に返信{#return-to-sender}

「Return to Sender」情報を組み込んだダイレクトメールプロバイダとのフラットファイル交換がサポートされます。 これにより、対応する住所を今後の通信から除外できます。 また、間違った住所を通知され、他のチャネルを通じて顧客と連絡を取ったり、住所の更新を促したりすることもできます。

例えば、連絡先が新しい場所に移動し、新しい住所が提供されなかったとします。 プロバイダは、誤ったアドレスのリストを検索し、この情報をAdobe Campaignに送信し、誤ったアドレスブロックリストを自動的にする。

この機能を動作させるために、ダイレクトメールのデフォルト配信テンプレートには、配信ログIDがコンテンツに含まれています。 これにより、Adobe Campaignは、プロファイルと配信のデータをプロバイダから返された情報と同期させることができる。

![](assets/direct_mail_return_sender_1.png)

**[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**&#x200B;の下にインポートテンプレートがあります。 独自のテンプレートを作成するには、このテンプレートに重複します。 インポートテンプレートの使用について詳しくは、[インポートテンプレートの使用](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)を参照してください。

![](assets/direct_mail_return_sender_2.png)

読み込みが完了すると、Adobe Campaignは次の操作を自動的に実行します。

* プロファイルレベルで、正しくないアドレスがブロックリストに追加される
* 配信の主要指標(KPI)が更新されます
* 配信ログが更新されます

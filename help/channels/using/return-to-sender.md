---
solution: Campaign Standard
product: campaign
title: 送信者に返信
description: 間違ったアドレスを通知し、今後の通信から除外する方法を説明します。
audience: channels
content-type: reference
topic-tags: direct-mail
feature: ダイレクトメール
role: User
level: Intermediate
exl-id: 6783aa68-7fd7-4f53-86bf-853c0fea5899
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 3%

---

# 送信者に返信{#return-to-sender}

Return to Sender情報を組み込んだダイレクトメールプロバイダーとのフラットファイル交換がサポートされています。 これにより、対応する郵送先住所を今後の通信から除外できます。 また、間違った住所を通知され、他のチャネルを通じて顧客と関わったり、郵送先住所の更新を促したりすることもできます。

例えば、新しい住所を指定していない連絡先が新しい場所に移動したとします。 プロバイダーは、誤ったアドレスのリストを取得し、この情報をAdobe Campaignに送信します。これにより、誤ったアドブロックリストレスが自動的にされます。

この機能を動作させるために、ダイレクトメールのデフォルトの配信テンプレートには、配信ログIDがコンテンツに含まれます。 したがって、Adobe Campaignは、プロバイダーから返される情報とプロファイルおよび配信データを同期できます。

![](assets/direct_mail_return_sender_1.png)

**[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**&#x200B;の下にインポートテンプレートがあります。 このテンプレートを複製して、独自のテンプレートを作成します。 インポートテンプレートの使用について詳しくは、[インポートテンプレートの使用](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)を参照してください。

![](assets/direct_mail_return_sender_2.png)

読み込みが完了すると、Adobe Campaignは自動的に次の操作を実行します。

* 正しくないアドレスがプロファブロックリストイルレベルで追加される
* 配信の主要指標(KPI)が更新されました
* 配信ログが更新されます

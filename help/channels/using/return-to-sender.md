---
title: 送信者に返信
description: 間違ったアドレスを通知され、今後の通信から除外する方法を説明します。
audience: channels
content-type: reference
topic-tags: direct-mail
feature: Direct Mail
role: User
level: Intermediate
exl-id: 6783aa68-7fd7-4f53-86bf-853c0fea5899
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---

# 送信者に返信{#return-to-sender}

Return to Sender 情報を組み込んだダイレクトメールプロバイダーとのフラットファイルの交換がサポートされています。 これにより、対応する郵送先住所を今後の通信から除外できます。 これにより、誤った住所を通知され、他のチャネルを通じて顧客と関わったり、郵送先住所の更新を促したりできます。

例えば、ある連絡先が新しい場所に移動し、新しい郵送先住所を提供しなかったとします。 プロバイダーは、誤ったアドレスのリストを取得し、この情報をAdobe Campaignに送信します。これにより、誤ったアドレスが自動的にブロックリストに加えるされます。

この機能を機能させるために、ダイレクトメールのデフォルト配信テンプレートには、コンテンツに配信ログ ID が含まれています。 これにより、Adobe Campaignは、プロファイルと配信データを、プロバイダーから返された情報と同期させることができます。

![](assets/direct_mail_return_sender_1.png)

インポートテンプレートは、「**[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**」の下で使用できます。 このテンプレートを複製して、独自のテンプレートを作成します。 インポートテンプレートの使用について詳しくは、[ インポートテンプレートの使用 ](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates) を参照してください。

![](assets/direct_mail_return_sender_2.png)

読み込みが完了すると、Adobe Campaignは自動的に次の操作を実行します。

* 間違ったアドレスがプロファイルレベルでブロックリストに追加される
* 配信のメイン指標（KPI）が更新されます
* 配信ログが更新されます

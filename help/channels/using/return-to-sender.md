---
title: 送信者に返信
description: 誤ったアドレスの通知を受け取り、今後の通信から除外する方法について説明します。
audience: channels
content-type: reference
topic-tags: direct-mail
feature: Direct Mail
role: User
level: Intermediate
exl-id: 6783aa68-7fd7-4f53-86bf-853c0fea5899
TQID: 'https://experienceleague.adobe.com/g-0yLI3-qYRfbF-gXuO8AtyCI3Qr5F7an5hqVzaQCE8'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: ede6e1ec-9279-415e-b828-a09735018d48
    internal-label: Direct mail
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%
---
# 送信者に返信{#return-to-sender}

Return to Sender情報を組み込んだダイレクトメールプロバイダーとのフラットファイル交換がサポートされています。 これにより、対応する郵便アドレスを今後の通信から除外することができます。 これにより、誤った住所の通知を受け、他のチャネルを通じて顧客とエンゲージしたり、住所の更新を促したりすることもできます。

例えば、連絡先が新しい場所に移動し、新しい住所を提供しなかったとします。 プロバイダーは、誤ったアドレスのリストを取得し、この情報をAdobe Campaignに送信します。これにより、誤ったアドレスが自動的にブロックリストに加えるされます。

この機能を機能させるには、ダイレクトメールのデフォルト配信テンプレートに、コンテンツに配信ログ IDが含まれます。 したがって、Adobe Campaignは、プロファイルデータと配信データをプロバイダーから返された情報と同期させることができます。

![](assets/direct_mail_return_sender_1.png)

インポートテンプレートは&#x200B;**[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**&#x200B;で利用できます。 このテンプレートを複製して、独自のテンプレートを作成します。 インポートテンプレートの使用について詳しくは、[ インポートテンプレートの使用](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)を参照してください。

![](assets/direct_mail_return_sender_2.png)

読み込みが完了すると、Adobe Campaignは自動的に次のアクションを実行します。

* プロファイルレベルで誤ったアドレスがブロックリストに加えるされる
* 配信の主要指標（KPI）が更新されます
* 配信ログが更新されます

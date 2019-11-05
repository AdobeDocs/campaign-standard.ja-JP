---
title: 送信者に戻る
description: 間違ったアドレスを通知し、それを今後の通信から除外する方法を説明します。
page-status-flag: 非活性化の
uuid: 11981c2f-0b7f-4166-9daa-ec6a6b4d5367
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: ダイレクトメール
discoiquuid: 5f20ff3f-8242-4735-8c60-c57610edff52
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 送信者に戻る{#return-to-sender}

Return to Sender情報を組み込んだダイレクトメールプロバイダとのフラットなファイル交換がサポートされます。 これにより、対応する住所を今後の通信から除外できます。 また、間違った住所の通知を受け取り、他のチャネルを通じて顧客と連絡を取り合ったり、住所の更新を促したりできます。

例えば、連絡先が新しい場所に移動し、新しい住所が提供されなかったとします。 プロバイダーは、エラーのあるアドレスのリストを取得し、この情報をAdobe Campaignに送信します。Adobe Campaignは、エラーのあるアドレスを自動的にブラックリストします。

この機能を動作させるために、ダイレクトメールのデフォルトの配信テンプレートには、配信ログIDがコンテンツに含まれています。 したがって、Adobe Campaignでは、プロファイルと配信データを、プロバイダーから返された情報と同期できます。

![](assets/direct_mail_return_sender_1.png)

インポートテンプレートは、で使用できま **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**&#x200B;す。 このテンプレートを複製して、独自のテンプレートを作成します。 インポートテンプレートの使用方法の詳細については、「インポートテンプレートの使 [用」を参照してくださ](../../automating/using/defining-import-templates.md)い。

![](assets/direct_mail_return_sender_2.png)

インポートが完了すると、Adobe Campaignは自動的に次の操作を実行します。

* 不正なアドレスがプロファイルレベルでブラックリストに表示される
* 配信のメインインジケーター(KPI)が更新されます
* 配信ログが更新されます


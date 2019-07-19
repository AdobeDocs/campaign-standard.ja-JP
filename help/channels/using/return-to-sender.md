---
title: 送信者に戻る
seo-title: 送信者に戻る
description: 送信者に戻る
seo-description: 間違ったアドレスを通知し、今後の通信から除外する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 11981c2f-0b7f-4166-9daya- ec6a6b4d5367
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: ダイレクトメール
discoiquuid: 5f20ff3f-8242-4735-8c60- c57610edff52
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Return to sender{#return-to-sender}

「送信者に戻る」情報を組み込むダイレクトメールプロバイダーとのフラットなファイル交換がサポートされています。これにより、対応する郵便番号を将来の通信から除外することができます。また、間違った住所を通知したり、他のチャネル経由で顧客に関わることや、住所の更新を促すことができます。

例えば、連絡先が新しい場所に移動し、新しい住所を提供していないとします。プロバイダーは、誤ったアドレスのリストを取得し、この情報をAdobe Campaignに送信して、誤ったアドレスを自動的にブラックリストに入れます。

この機能を機能させるために、ダイレクトメールのデフォルト配信テンプレートには、コンテンツの配信ログIDが含まれます。そのため、Adobe Campaignでは、プロファイルと配信データをプロバイダーから返された情報と同期できます。

![](assets/direct_mail_return_sender_1.png)

An import template is available under **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. このテンプレートを複製して独自のテンプレートを作成してください。For more on using import templates, refer to [Using import templates](../../automating/using/defining-import-templates.md).

![](assets/direct_mail_return_sender_2.png)

インポートが完了すると、Adobe Campaignは自動的に次のアクションを実行します。

* 正しいアドレスがプロファイルレベルでブラックリストに記載されている
* 配信メインインジケーター（KPI）が更新されます
* 配信ログが更新されます


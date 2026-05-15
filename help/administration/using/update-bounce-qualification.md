---
title: ISP の機能停止後にバウンス選定条件を更新
description: ISP が機能停止した後にバウンス選定を更新する方法を説明します。
audience: delivery
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
TQID: https://experienceleague.adobe.com/PcNbVFzTVJhadANGQ5uogj16VHiaNIf7HVn-7X-EbJA
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 441
ht-degree: 58%

---

# ISP の機能停止後にバウンス選定条件を更新 {#update-bounce-qualification.md}

## コンテキスト

ISP が機能停止した場合、Campaign 経由で送信されたメールは、受信者に正常に届きません。これらのメールは、誤ってバウンスと見なされます。

2020 年 12 月、Gmail の グローバルな問題により、Gmail の有効なメールアドレスに送信されたメールメッセージの一部が、無効なメールアドレスとして Gmail サーバーから誤ってハードバウンスされ、「*550-5.1.1 送信先のメールアカウントは存在しません*」という応答が返されました。

Googleは、この問題を引き起こしたGmailの停止と中断は、12月14日の6:55AMに始まり、12月15日の6:09PM ESTに終わったと述べています。 当社のデータ分析では、12月16日のEST 2:06AM、EST 2:00、EST 6:30、EST 12月15日の午後2、EST 6の間にGmailのバウンスが非常に短期間に増加したことも示されています。

>[!NOTE]
>
>[このページ](https://www.google.com/appsstatus#hl=ja&v=status)で Google Workspace ステータスダッシュボードを確認できます。


標準的なバウンス処理ロジックごとに、Adobe Campaignはこれらの受信者を自動的に強制隔離リストに追加し、**[!UICONTROL Status]**&#x200B;設定は&#x200B;**[!UICONTROL Quarantine]**&#x200B;でした。 これを修正するには、これらの受信者を検索して削除するか、夜間のクリーンアップワークフローで削除できるように&#x200B;**[!UICONTROL Status]**&#x200B;を&#x200B;**[!UICONTROL Valid]**&#x200B;に変更して、Campaignの強制隔離テーブルを更新する必要があります。

この Gmail の問題の影響を受けた受信者を特定する場合や、他の ISP で同じ状況が発生した場合は、以下の手順を参照してください。

## 更新処理

強制隔離テーブルに対してクエリを実行して、機能停止の影響を受けた可能性のある Gmail（または他の ISP）の受信者をすべて除外する必要があります。それにより、該当する受信者を強制隔離リストから削除し、Campaign による今後のメール配信の対象に含めることができるようになります。

インシデントの期間に基づいて、このクエリの推奨ガイドラインを以下に示します。

>[!IMPORTANT]
>
>これらの日時は、米国東部標準時（EST）に基づいています。 お使いのインスタンスのタイムゾーンに合わせて調整してください。

強制隔離リストの&#x200B;**[!UICONTROL Error text]** フィールドにSMTP バウンス応答情報があるCampaign インスタンスの場合：

* **エラーテキスト（強制隔離テキスト）**&#x200B;に「550-5.1.1 The email account that you tried does not exist」が含まれ、かつ、**エラーテキスト（強制隔離テキスト）**&#x200B;に「support.google.com」が含まれる**
* **2020年6月2日午前12日以降の更新ステータス （@lastModified）**:55:
* **2020年6月16日午前6時:00:00分以前のステータス（@lastModified）**&#x200B;の更新

影響を受ける受信者のリストを取得したら、ステータスを&#x200B;**[!UICONTROL Valid]**&#x200B;に設定して、**[!UICONTROL Database cleanup]** ワークフローで強制隔離リストから削除するか、テーブルから削除します。

**関連トピック：**
* [配信エラーについて](../../sending/using/understanding-delivery-failures.md)
* [バウンスメール選定](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)

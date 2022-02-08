---
title: ISP 機能停止後のバウンス認定条件の更新
description: ISP が機能停止した後にバウンスの認定条件を更新する方法を説明します。
audience: delivery
hidefromtoc: true
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 70%

---

# ISP 機能停止後のバウンス認定条件の更新 {#update-bounce-qualification.md}

最新バージョンの Campaign を実行していない場合は、この節が適用される場合があります。 Adobe Campaignの担当者にお問い合わせください。

## コンテキスト

ISP が機能停止した場合、Campaign 経由で送信された E メールは、受信者に正常に届きません。これらの E メールは、誤ってバウンスと見なされます。

2020 年 12 月、Gmail の グローバルな問題により、Gmail の有効な E メールアドレスに送信された E メールメッセージの一部が、無効な E メールアドレスとして Gmail サーバーから誤ってハードバウンスされ、「*550-5.1.1 送信先の E メールアカウントは存在しません*」という応答が返されました。

Google は、この問題の原因となった Gmail の機能停止とサービス中断は米国東部標準時の 12 月 14 日午前 6 時 55 分に始まり、12 月 15 日午後 6 時 9 分に終了したと発表しています。 当社のデータ分析でも、米国東部標準時の 12 月 16 日の午前 2 時 6 分に Gmail のバウンスが瞬間的に急増しました。大部分は 12 月 15 日の午後 2 時から午後 6 時 30 分に発生しています。

>[!NOTE]
>
>[このページ](https://www.google.com/appsstatus#hl=ja&amp;v=status)で Google Workspace ステータスダッシュボードを確認できます。


Adobe Campaignは、標準のバウンス処理ロジックに従って、これらの受信者を強制隔離リストに自動的に追加し、 **[!UICONTROL Status]** 設定 **[!UICONTROL Quarantine]**. これを修正するには、Campaign で強制隔離テーブルを更新し、それらの受信者を検索および削除するか、テーブルの **[!UICONTROL Status]** から **[!UICONTROL Valid]** そのため、毎晩のクリーンアップワークフローによって削除されます。

この Gmail の問題の影響を受けた受信者を特定する場合や、他の ISP で同じ状況が発生した場合は、以下の手順を参照してください。

## 更新処理

強制隔離テーブルに対してクエリを実行して、機能停止の影響を受けた可能性のある Gmail（または他の ISP）の受信者をすべて除外する必要があります。それにより、該当する受信者を強制隔離リストから削除し、Campaign による今後の E メール配信の対象に含めることができるようになります。

インシデントの期間に基づいて、このクエリの推奨ガイドラインを以下に示します。

>[!IMPORTANT]
>
>これらの日時は、米国東部標準時（EST）に基づいています。 お使いのインスタンスのタイムゾーンに合わせて調整してください。

SMTP バウンス応答情報が **[!UICONTROL Error text]** 強制隔離リストのフィールド：

* **エラーテキスト（強制隔離テキスト）**&#x200B;に「550-5.1.1 The email account that you tried does not exist」が含まれ、かつ、**エラーテキスト（強制隔離テキスト）**&#x200B;に「support.google.com」が含まれる**
* **更新ステータス（@lastModified）**&#x200B;が 2020 年 12 月 14 日午前 6:55:00 以降
* **ステータスを更新 (@lastModified)** 12/16/2020 6 以前:00:午前 00 時

影響を受ける受信者のリストが用意できたら、ステータスを **[!UICONTROL Valid]** したがって、これらは、 **[!UICONTROL Database cleanup]** ワークフローを作成するか、単にテーブルから削除します。

**関連トピック：**
* [配信エラーについて](../../sending/using/understanding-delivery-failures.md)
* [バウンスメールの認定](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)

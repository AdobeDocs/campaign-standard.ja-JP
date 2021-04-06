---
solution: Campaign Standard
product: campaign
title: ISPの使用停止後にバウンスの資格を更新する
description: ISPが停止した後にバウンス条件を更新する方法を説明します。
audience: delivery
content-type: reference
topic-tags: monitoring-deliveries
hidefromtoc: true
translation-type: tm+mt
source-git-commit: 9edf26fa933e9faedecef3b381cb160230a51668
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 1%

---


# ISPの停止後にバウンスの資格を更新{#update-bounce-qualification.md}

最新バージョンのキャンペーンを実行していない場合は、この節が適用される場合があります。 Adobe Campaignの担当者にお問い合わせください。

## コンテキスト

ISPが使用不能になった場合、キャンペーン経由で送信された電子メールは、受信者に正常に配信できません。これらの電子メールは、バウンスとして誤ってマークされます。

2020年12月、Gmailのグローバルな問題により、有効なGmail電子メールアドレスに送信された電子メールメッセージの一部が、Gmailサーバーから無効な電子メールアドレスとして誤ってハードバウンスされ、次のバウンスが返されました。*&quot;550-5.1.1に到達しようとした電子メールアカウントは存在しません。&quot;*

Googleは、この問題の原因となったGmailの障害と混乱を12月14日午前6時55分に始め、12月15日の米国東部標準時6時9分に終了したと述べています。 また、データ分析では、12月16日の午前2時6分（米国東部標準時）にGmailのバウンスが非常に短いスパイクが見られました。大部分は12月15日の午後2時から午後6時30分に発生しています。

>[!NOTE]
>
>[このページ](https://www.google.com/appsstatus#hl=en&amp;v=status)でGoogle Workspaceのステータスダッシュボードを確認できます。


標準のバウンス処理ロジックに従って、Adobe Campaignは、**[!UICONTROL Status]**&#x200B;設定&#x200B;**[!UICONTROL Quarantine]**&#x200B;を使用して、これらの受信者を強制隔離リストに自動的に追加しました。 この問題を修正するには、キャンペーンで強制隔離テーブルを更新する必要があります。これらの受信者を見つけて削除するか、夜間のクリーンアップワークフローで削除されるように&#x200B;**[!UICONTROL Status]**&#x200B;を&#x200B;**[!UICONTROL Valid]**&#x200B;に変更します。

このGmailの問題の影響を受けた受信者や、他のISPで再び発生した場合に備えて、以下の手順を参照してください。

## 更新するプロセス

強制隔離テーブルのクエリを実行して、機能停止の影響を受けた可能性のあるGmail（または他のISP）受信者をすべて除外し、強制隔離リストから削除したり、将来のキャンペーンの電子メール配信に含めたりする必要があります。

インシデントの時間枠に基づき、このクエリで推奨されるガイドラインを以下に示します。

>[!IMPORTANT]
>
>これらの日時は、東部標準タイムゾーン(EST)に基づいています。 インスタンスのタイムゾーンに合わせて調整してください。

SMTPバウンス応答情報を持つキャンペーンインスタンスの場合、強制隔離リストの&#x200B;**[!UICONTROL Error text]**&#x200B;フィールドに次のように入力します。

* **エラーテキスト(強制隔離テキスト)** に「550-5.1.1 The email account that you tried does not exist」が **含まれ、** エラーテキスト(強制隔離テキスト)に「support.google.com」が含まれています**
* **2020年12月14日6:55:00 AM以降** の更新ステータス(@lastModified)
* **2020年12月16日6:00:00 AM** 以前の更新ステータス(@lastModified)

影響を受ける受信者のリストを取得したら、**[!UICONTROL Database cleanup]**&#x200B;ワークフローによって強制隔離リストから削除されるように&#x200B;**[!UICONTROL Valid]**&#x200B;のステータスに設定するか、表から削除します。

**関連トピック：**
* [配信障害の把握](../../sending/using/understanding-delivery-failures.md)
* [バウンスメールの選定](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)


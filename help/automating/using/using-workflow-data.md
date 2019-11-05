---
title: ワークフローデータの使用
description: 読み込んだデータやターゲット設定したデータを使用する様々な可能性について説明します。
page-status-flag: 非活性化の
uuid: 3dd66aeb-3a26-4214-b6a0-242c2b7fbc49
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: workflow-general-operation
discoiquuid: 90b250f1-f32d-4256-83ea-4c0627628610
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# ワークフローデータの使用{#using-workflow-data}

識別され、準備されたデータは、次のコンテキストで使用できます。

* アクテ **[!UICONTROL Update data]** ィビティを使用すると、データベース内のフィールドに対して一括更新を実行できます。
* アクティビティ **[!UICONTROL Save audience]** を使用すると、既存のオーディエンスを更新したり、ワークフローの上流で計算された訪問者から新しいオーディエンスを作成したりできます。 このアクティビティから作成または更新されるオーディエンスは **リスト** または **ファイル** オーディエンスです。 また、このアクティビティでは、プロファイルをAdobe Experience cloudオーディエンス/セグメントとしてエクスポートできます。
* アクティビティ **[!UICONTROL Subscription Services]** では、プロファイルを一括して取得し、サービスに登録したり、サービスから登録を解除したりできます。
* このア **[!UICONTROL Extract file]** クティビティでは、外部ファイルの形式でAdobe Campaignからデータをエクスポートできます。

プロファイルターゲットを定義した後、複数のアクティビティを使用して配信を作成および送信できます。

* このア **[!UICONTROL Email delivery]** クティビティでは、ワークフローでの電子メールの送信を設定できます。 1回の送信電子メ **ールで** 1回だけ送信することも、繰り返し送信する電子メールでもかまい **ません** 。
* アクティビティ **[!UICONTROL SMS delivery]** を使用すると、ワークフローでSMSを送信するように設定できます。 1回の送信SMSで1回 **送信するか** 、定期的なSMSで **す** 。
* アクティビテ **[!UICONTROL Mobile app delivery]** ィを使用すると、ワークフローでプッシュ通知を送信するように設定できます。 1回の送信通知で1 **回だけ送信する** か **、繰り返し送信することがで** きます。


---
title: Adobe Experience Platform SDK への SDK v4 モバイルアプリケーションの移行
description: SDK v4 からAdobe Experience Platform SDK にモバイルアプリケーションを移行する方法を説明します
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: 620ae1adc6f804e90c10daeb5fa4df42ce106885
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 1%

---

# SDK v4 からAdobe Experience Platform SDK にモバイルアプリケーションを移行する方法 {#sdkv4-migration}


Adobe Experience Platform Mobile version 4 SDK のサポートは 2021 年 8 月 31 日（PT）をもって終了しました。 引き続きこのレガシーバージョンの SDK を使用する場合は、**2024 年 6 月末までに**、Adobe Experience Platform SDK で実装を更新する必要があります。 Adobe Experience Platform SDK に移行する方法については、この記事を参照してください。

>[!IMPORTANT]
>
> SDK V4 モバイルアプリケーションのAdobe Experience Platform SDK への移行を開始する前に、ドキュメントをよくお読みください。

## SDK V4 の移行について

Adobe Campaign Standardは、Adobe Experience Platform SDK を使用するアプリケーションとは別のアプリケーションとして、SDK V4 を使用するモバイルアプリケーションを処理します。

Adobe SDK バージョンを v4 からAdobe Experience Platformにアップグレードした後、モバイルアプリケーションでは既存のアプリケーション購読者データとキャンペーンを引き続き使用する必要があります。そのため、移行が必要です。

>[!NOTE]
>
> このページでは、新しく作成したAdobe Experience Platform SDK アプリケーションへの SDK v4 モバイルアプリケーションの移行について説明します。 SDK v4 モバイルアプリケーションは、**[!UICONTROL Configured]** **[!UICONTROL Property status]** を持つAdobe Experience Platform SDK モバイルアプリケーションとは結合されません。

| 移行後に変更されない内容 |
|:-:|
| 移行された SDK V4 アプリケーションを使用している既存の配信およびキャンペーンには影響はありません。 |
| モバイルアプリケーションの名前は同じままです。 |
| iOSとAndroidのプラットフォーム資格情報は保持されます。 |
| アプリケーションのすべてのサブスクライバーとそのデータは保持されます。 |
| 既存の SDK v4 モバイルアプリケーションは、データ（PII データ、購読者およびトークン情報）を引き続きAdobe Campaign Standardに送信します。 |
| モバイルアプリケーションの **[!UICONTROL Organizational unit]** は同じままです。 |

| 移行後の変更点 |
|:-:|
| モバイルアプリケーションは、**[!UICONTROL Administration]**/**[!UICONTROL Channels]**/**[!UICONTROL Mobile app (Adobe Experience Platform SDK)]** で使用できます。 移行前は、**[!UICONTROL Administration]**/**[!UICONTROL Channels]**/**[!UICONTROL Mobile app (SDK V4)]** で使用できました。 |
| アプリケーションの **[!UICONTROL Collect PII Endpoint]** が変更されます。 古い **[!UICONTROL Collect PII Endpoint]** は引き続き機能し、送信されたデータは失われません。 |
| アプリケーションはタグ **[!UICONTROL Mobile Property]** に関連付けられます。 新しく作成されたモバイルアプリケーションとして処理されます。 |
| 移行で使用される元のAdobe Experience Platform SDK アプリケーションは、別のアプリケーションとしては存在しません。 移行された SDK v4 アプリケーションのみ使用できます。 |

## SDK v4 からAdobe Experience Platform SDK へのモバイルアプリケーションの移行 {#how-to-migrate}

移行する前に、次の推奨事項を考慮に入れる必要があります。

* 移行プロセスは元に戻せません。
* 複数のアプリケーションの移行を同時に実行しないでください。 また、同じアプリケーションの移行が複数のウィンドウで同時にトリガーされないようにしてください。
* 移行前に、移行するモバイルアプリケーションと、移行に使用するAdobe Experience Platform アプリケーションの **[!UICONTROL Organizational unit]** が割り当てられていることを確認してください。
* 移行後、アプリケーションはAdobe Experience Platform SDK アプリケーションになります。 変更内容は、対応するタグ **[!UICONTROL Mobile Property]** にリンクされます。

1. データ収集 UI で新しい **[!UICONTROL Mobile property]** を作成します。 詳しくは、[ ドキュメント ](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/) を参照してください。

1. Adobe Campaign Standardで、詳細メニューから **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** を選択し、**[!UICONTROL syncWithLaunch]** ワークフローを開きます。 ワークフローがエラーなく終了したかどうかを確認します。

1. ワークフロー完了後、**[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]** メニューから、モバイルアプリケーションがAdobe Campaign Standardで使用可能で、ステータスが **[!UICONTROL Ready to Configure]** しいかどうかを確認します。

   ![](assets/aep_v4_2.png)

1. **[!UICONTROL Administration]**/**[!UICONTROL Channels]**/**[!UICONTROL Mobile app (SDK V4)]** で、移行する SDK V4 アプリケーションを選択します。

1. 「**[!UICONTROL Mobile application migration to AEP SDK]**」タブを選択します。

   ![](assets/aep_v4_3.png)

1. **[!UICONTROL Select AEP SDK mobile application to merge current application with]** ドロップダウンから、以前に作成したAdobe Experience Platform SDK モバイルアプリケーションを選択します。

1. 「**[!UICONTROL Migrate]**」をクリックします。

   ![](assets/aep_v4_4.png)

1. **[!UICONTROL Migration application]** ウィンドウで、「**[!UICONTROL Ok]**」をクリックします。

   ![](assets/aep_v4_5.png)

1. 正常な完了ウィンドウが表示されたら、「**[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**」をクリックします。

1. Adobe Experience Platform SDK チャネルリストページで、以前の V4 モバイルアプリケーションが **[!UICONTROL Ready To Configure]** に設定されていることを確認します。

1. モバイルアプリケーションを選択し、「**[!UICONTROL Save]**」をクリックして移行を完了します。

この移行後、モバイルアプリケーションの V4 バージョンで収集されたサブスクライバーと、モバイルアプリケーションの AEP バージョンで収集された新しいサブスクライバーは、移行されたアプリケーションで使用できます。

2 つの異なるタイプのサブスクライバーを区別するには、カスタムリソースフィールドを拡張する際に、**[!UICONTROL Text]** タイプの新しいカスタムフ **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** ールドを、例えば `sdkversion` や `appVersion` のように追加できます。 カスタムリソースの拡張方法について詳しくは、この [ ページ ](../../developing/using/creating-or-extending-the-resource.md) を参照してください。
次に、関連するタグ **[!UICONTROL Mobile property]** を設定して、PII 呼び出しを収集でこのカスタムフィールド値を送信し、それに応じてモバイルアプリケーション設定を変更する必要があります。

## FAQ {#faq}

### Q:SDK v4 モバイルアプリケーションで、「Adobe Experience Platform SDK へのモバイルアプリケーションの移行」タブが表示されません。 {#tab-not-visible}

A：詳細メニュー **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]** で、「**[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]**」オプションの値をチェックします。 1 に設定し、デフォルトで有効にする必要があります。 管理者が手動で無効にしている可能性があります。

![](assets/aep_v4_1.png)

### Q: 「モバイルアプリケーションのAdobe Experience Platform SDK への移行」タブで、「データがありません」というメッセージが表示されます。 {#no-data}

回答：**[!UICONTROL Organizational unit]** ールの適格なアプリケーションのみがリストに表示されます。 移行用の正しいAdobe Experience Platform アプリケーションがあることを確認してください。 Adobe Experience Platform アプリケーションの **[!UICONTROL Property Status]** を **[!UICONTROL Ready to Configure]** に設定し、**[!UICONTROL Mobile app migration status]** を **[!UICONTROL Not Migrated]** に設定する必要があります。

![](assets/aep_v4_6.png)

### Q：設定済みプロパティのステータスを持つAdobe Experience Platform SDK アプリケーションを移行に使用できないのはなぜですか？ {#property-status}

回答：移行プロセスでは、SDK v4 サブスクライバーと属性が保持されます。 Adobe Experience Platform SDK アプリケーションから取得したタグ関連情報のみを保持します。 Adobe Experience Platform SDK アプリケーションの購読者とその他のデータは失われます。 データ損失を避けるために、**[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]** を持つAdobe Experience Platform SDK アプリケーションのみが移行の対象となります。

### Q：移行後、以前の SDK v4 モバイルアプリケーションはどこにありますか？ {#v4-app-not-visible}

回答：移行後のモバイルアプリケーションが、詳細メニュー **[!UICONTROL Administration]**/**[!UICONTROL Channels]**/**[!UICONTROL Mobile app (Adobe Experience Platform SDK)]** に表示されます。

### Q：移行後、新しく作成したAdobe Experience Platform SDK アプリケーションはどこで見つけられますか？ {#aep-not-visible}

回答：移行に使用される、新しく作成されたAdobe Experience Platform SDK アプリケーションは、個別のアプリケーションとしては存在しません。 移行された SDK v4 アプリケーションのみ使用できます。

### Q:SDK v4 モバイルアプリケーションの組織単位が A （組織単位 ALL の子）に設定されていて、Adobe Experience Platform SDK が ALL に設定されている場合。 モバイルアプリケーションを移行するにはどうすればよいですか？ {#v4-org-unit}

A:**[!UICONTROL Organizational unit]** の管理者は、モバイルアプリケーションの両方を管理する権限を持ち、移行を担当します。

### Q:SDK v4 モバイルアプリケーションの組織単位が A に設定されていて、Adobe Experience Platform SDK アプリケーションが B （組織単位 A の兄弟）に設定されている場合。 モバイルアプリケーションを移行するにはどうすればよいですか？ {#aep-org-unit}

回答：Adobe Experience Platform SDK アプリケーションは兄弟 **[!UICONTROL Organizational unit]** ーザーのアセットなので、**[!UICONTROL Organizational unit]** A のユーザーにはモバイルアプリケーションは表示されません。モバイルアプリケーションは、**[!UICONTROL Organizational unit]** ALL の管理者が使用できますが、これらの管理者にモバイルアプリケーションを移行することはお勧めしません。
この場合、モバイルアプリケーションを同じ **[!UICONTROL Organizational unit]**、または親リンクを持つ **[!UICONTROL Organizational unit]** 内で移動する必要があります。
**[!UICONTROL Organizational unit]** について詳しくは、この [ 節 ](../../administration/using/organizational-units.md) を参照してください。

### 質問：Adobe Experience Platform SDK モバイルアプリケーション（v4 モバイルアプリケーションから移行）ページの「プッシュチャネル設定」ドロップダウンに、Android キーやiOS証明書のアップロード日や名前などの情報が表示されません {#no-information-v5}

回答：SDK V4 モバイルアプリケーションの作成時には、この情報は保存されません。 SDK V4 モバイルアプリケーションをAdobe Experience Platform SDK モバイルアプリケーションに移行する場合、移行されたモバイルアプリケーションにもこのような情報は含まれません。 新しいiOS証明書またはAndroid キーをアップロードするとすぐに、キーまたは証明書の様々な詳細が保存され、**[!UICONTROL Push channel settings]** ドロップダウンに正しく表示されます。

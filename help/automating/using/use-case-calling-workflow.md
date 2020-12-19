---
solution: Campaign Standard
product: campaign
title: 外部パラメーターを使用したワークフローの呼び出し
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 1%

---


# 使用例 {#use-case}

次の使用例は、ワークフロー内のパラメーターを使用してワークフローを呼び出す方法を示しています。

目的は、外部パラメーターを使用したAPI呼び出しからワークフローをトリガーすることです。 このワークフローは、データをファイルからデータベースに読み込み、関連するオーディエンスを作成します。 オーディエンスが作成されると、API呼び出しで定義された外部パラメーターと共にパーソナル化されたメッセージを送信するために、2つ目のワークフローがトリガーされます。

この使用例を実行するには、次の操作を実行する必要があります。

1. **外部パラメーターを使用してワークフロー1をトリガーするAPI** 呼び出しを作成します。[手順1を参照：API呼び出し](../../automating/using/use-case-calling-workflow.md#step-1--configuring-the-api-call)を設定する
1. **ワークフロー1の構築**:ワークフローはファイルを転送し、データベースに読み込みます。その後、データが空かどうかをテストし、最終的にプロファイルをオーディエンスに保存します。 最後に、ワークフロー2がトリガーされます。 [手順2を参照：ワークフロー1](../../automating/using/use-case-calling-workflow.md#step-2--configuring-workflow-1)を設定しています。
1. **ワークフローの構築2**:ワークフローは、Workflow 1で作成されたオーディエンスを読み取り、プロファイルにパーソナライズされたメッセージを送信します。パラメーターと共にカスタマイズされたセグメントコードーが含まれます。[手順3を参照：ワークフロー2](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2)を設定しています。

![](assets/extsignal_uc_process.png)

## 前提条件 {#prerequisites}

ワークフローを設定する前に、それぞれに&#x200B;**[!UICONTROL External signal]**&#x200B;アクティビティを含むWorkflow 1と2を作成する必要があります。 これにより、ワークフローの呼び出し時にこれらのシグナルアクティビティをターゲットできます。

## 手順1:API呼び出しの設定{#step-1--configuring-the-api-call}

API呼び出しを行い、パラメーターを使用してワークフロー1をトリガーします。 API呼び出しの構文について詳しくは、[Campaign StandardREST APIのドキュメント](../../api/using/triggering-a-signal-activity.md)を参照してください。

この場合、以下のパラメーターを使用してワークフローを呼び出します。

* **fileToTarget**:データベースにインポートするファイルの名前。
* **discountDesc**:割引の配信に表示する説明。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/<TRIGGER_URL>
-H 'Authorization: Bearer <ACCESS_TOKEN>' 
-H 'Cache-Control: no-cache' 
-H 'X-Api-Key: <API_KEY>' 
-H 'Content-Type: application/json;charset=utf-8' 
-H 'Content-Length:79' 
-i
-d {
-d "source:":"API",
-d "parameters":{
-d "fileToTarget":"profile.txt",
-d "discountDesc":"Running shoes"
-d } 
```

## 手順2:ワークフロー1の構成{#step-2--configuring-workflow-1}

ワークフロー1は次のように構築されます。

* **[!UICONTROL External signal]** アクティビティ:ワークフロー内で使用するために外部パラメーターを宣言する必要がある場合。
* **[!UICONTROL Transfer file]** アクティビティ:パラメーターで定義された名前のファイルを読み込みます。
* **[!UICONTROL Load file]** アクティビティ:読み込んだファイルのデータをデータベースに読み込みます。
* **[!UICONTROL Update data]** アクティビティ:インポートしたファイルのデータを使用してデータベースを挿入または更新します。
* **[!UICONTROL Test]** アクティビティ:データがインポートされているかどうかを確認します。
* **[!UICONTROL Save audience]** アクティビティ:ファイルにデータが含まれる場合は、プロファイルをオーディエンスに保存します。
* **[!UICONTROL End activity]** アクティビティ:ワークフロー2内で使用するパラメーターを指定して呼び出します。

![](assets/extsignal_uc_wkf1.png)

次の手順に従って、ワークフローを設定します。

1. API呼び出しで定義されたパラメーターを宣言します。 これを行うには、**[!UICONTROL External signal]**&#x200B;アクティビティを開き、パラメーターの名前と型を追加します。

   ![](assets/extsignal_uc1.png)

1. データをデータベースにインポートする追加&#x200B;**[!UICONTROL Transfer file]**&#x200B;アクティビティ。これを行うには、アクティビティをドラッグ&amp;ドロップして開き、「**[!UICONTROL Protocol]**」タブを選択します。
1. **[!UICONTROL Use a dynamic file path]**&#x200B;オプションを選択し、**fileToTarget**&#x200B;パラメーターを転送するファイルとして使用します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. ファイルからデータベースにデータを読み込みます。

   これを行うには、**[!UICONTROL Load file]**&#x200B;アクティビティをワークフローにドラッグ&amp;ドロップし、必要に応じて設定します。

1. インポートしたファイルのデータを使用してデータベースを挿入し、更新します。

   これを行うには、**[!UICONTROL Update data]**&#x200B;アクティビティをドラッグ&amp;ドロップし、「**[!UICONTROL Identification]**」タブを選択して調整条件を追加します（この例では、**email**&#x200B;フィールド）。

   ![](assets/extsignal_uc3.png)

1. 「**[!UICONTROL Fields to update]**」タブを選択し、データベースで更新するフィールドを指定します（この例では、**firstname**&#x200B;と&#x200B;**email**&#x200B;の各フィールド）。

   ![](assets/extsignal_uc4.png)

1. データがファイルから取得されるかどうかを確認します。 これを行うには、**[!UICONTROL Test]**&#x200B;アクティビティをワークフローにドラッグ&amp;ドロップし、**[!UICONTROL Add an element]**&#x200B;ボタンをクリックして条件を追加します。
1. 条件に名前を付けて定義します。 この場合、アウトバウンドトランジションに次の構文のデータが含まれているかどうかをテストします。

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. データが取得された場合は、オーディエンスに保存します。 これを行うには、**[!UICONTROL Save audience]**&#x200B;アクティビティを&#x200B;**ターゲットに追加し、空ではない**&#x200B;トランジションを開きます。
1. **[!UICONTROL Use a dynamic label]**&#x200B;オプションを選択し、**fileToTarget**&#x200B;パラメーターをオーディエンスのラベルとして使用します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. **[!UICONTROL End]**&#x200B;アクティビティをドラッグ&amp;ドロップし、パラメーターを指定してWorkflow 2を呼び出してから開きます。
1. 「**[!UICONTROL External signal]**」タブを選択し、トリガするワークフローとそれに関連する信号アクティビティを指定します。
1. ワークフロー2内で使用するパラメーターと、それに関連する値を定義します。

   この場合、API呼び出しで元々定義されていたパラメーター（**fileToTarget**&#x200B;と&#x200B;**discountDesc**）と、定数値(&quot;20% discount&quot;)を持つ追加の&#x200B;**segmentCode**&#x200B;パラメーターを渡します。

   ![](assets/extsignal_uc7.png)

ワークフロー1が設定され、ワークフロー2を構築できるようになりました。 詳しくは、[こちらの節](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2)を参照してください。

## 手順3:ワークフロー2の構成{#step-3--configuring-workflow-2}

ワークフロー2は次のように構築されます。

* **[!UICONTROL External signal]** アクティビティ:ここで、ワークフロー内で使用するためにパラメーターを宣言する必要があります。
* **[!UICONTROL Read audience]** アクティビティ:は、ワークフロー1に保存されたオーディエンスを読み上げます。
* **[!UICONTROL Email delivery]** アクティビティ:パラメーターを使用してパーソナライズされたターゲットオーディエンスに定期的なメッセージを送信します。

![](assets/extsignal_uc_wkf2.png)

次の手順に従って、ワークフローを設定します。

1. ワークフロー1で定義したパラメーターを宣言します。

   これを行うには、**[!UICONTROL External signal]**&#x200B;アクティビティを開き、Workflow 1の&#x200B;**[!UICONTROL End]**&#x200B;アクティビティで定義されている各パラメーターの名前とタイプを追加します。

   ![](assets/extsignal_uc8.png)

1. ワークフロー1に保存されたオーディエンスを使用します。 これを行うには、**[!UICONTROL Read audience]**&#x200B;アクティビティをワークフローにドラッグ&amp;ドロップし、開きます。
1. **[!UICONTROL Use a dynamic audience]**&#x200B;オプションを選択し、**fileToTarget**&#x200B;パラメーターを読み取るオーディエンスの名前として使用します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. **segmentCode**&#x200B;トランジションーに従って送信パラメーターに名前を付けます。

   これを行うには、「**[!UICONTROL Transition]**」タブを選択し、「**[!UICONTROL Use a dynamic segment code]**」オプションを選択します。

1. **segmentCode**&#x200B;パラメーターを送信トランジションの名前として使用します。

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. **[!UICONTROL Email delivery]**&#x200B;アクティビティをドラッグ&amp;ドロップして、オーディエンスにメッセージを送信します。
1. メッセージで使用するパラメーターを指定し、**discountDesc**&#x200B;パラメーターを使用してカスタマイズします。 これを行うには、アクティビティの詳細オプションを開き、パラメータ名と値を追加します。

   ![](assets/extsignal_uc10b.png)

1. これで、メッセージを設定できます。 アクティビティを開き、**[!UICONTROL Recurring email]**&#x200B;を選択します。

   ![](assets/extsignal_uc11.png)

1. 使用するテンプレートを選択し、必要に応じて電子メールのプロパティを定義します。
1. **discountDesc**&#x200B;パラメーターをパーソナライゼーションフィールドとして使用します。 これを行うには、パーソナライゼーションフィールドリストから選択します。

   ![](assets/extsignal_uc13.png)

1. これで、メッセージの設定を完了し、通常どおり送信できます。

   ![](assets/extsignal_uc14.png)

## ワークフロー{#executing-the-workflows}の実行

ワークフローを構築したら、それらを実行できます。 API呼び出しを実行する前に、2つのワークフローが起動していることを確認します。

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

1. **外部パラメーターを使用してワークフロー** 1をトリガーするAPI呼び出しを行います。 詳しくは、 [手順1を参照してください。API呼び出しの設定](../../automating/using/use-case-calling-workflow.md#step-1--configuring-the-api-call)。
1. **ワークフロー1の構築**:ワークフローはファイルを転送し、データベースに読み込みます。 その後、データが空かどうかをテストし、最終的にプロファイルをオーディエンスに保存します。 最後に、ワークフロー2がトリガーされます。 手順2を参照 [してください。ワークフロー1の設定](../../automating/using/use-case-calling-workflow.md#step-2--configuring-workflow-1)。
1. **ワークフローの構築2**:ワークフローは、Workflow 1で作成されたオーディエンスを読み取り、プロファイルにパーソナライズされたメッセージを送信します。パラメーターと共にカスタマイズされたセグメントコードーが含まれます。 詳しくは、 [手順3を参照してください。ワークフローの設定2](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2)。

![](assets/extsignal_uc_process.png)

## 前提条件 {#prerequisites}

ワークフローを設定する前に、それぞれにアクティビティを含むワークフロー1と2を作成する必要があり **[!UICONTROL External signal]** ます。 これにより、ワークフローの呼び出し時にこれらのシグナルアクティビティをターゲットできます。

## 手順1:API呼び出しの設定 {#step-1--configuring-the-api-call}

API呼び出しを行い、パラメーターを使用してワークフロー1をトリガーします。 API呼び出しの構文について詳しくは、 [Campaign StandardREST APIのドキュメントを参照してください](../../api/using/triggering-a-signal-activity.md)。

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

## 手順2:ワークフローの設定1 {#step-2--configuring-workflow-1}

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

1. API呼び出しで定義されたパラメーターを宣言します。 これを行うには、 **[!UICONTROL External signal]** アクティビティを開き、パラメーターの名前とタイプを追加します。

   ![](assets/extsignal_uc1.png)

1. データをデータベースにインポートする **[!UICONTROL Transfer file]** アクティビティです。これを行うには、アクティビティをドラッグ&amp;ドロップして開き、 **[!UICONTROL Protocol]** タブを選択します。
1. この **[!UICONTROL Use a dynamic file path]** オプションを選択し、 **fileToTarget** パラメーターを転送するファイルとして使用します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. ファイルからデータベースにデータを読み込みます。

   これを行うには、ワークフローに **[!UICONTROL Load file]** アクティビティをドラッグ&amp;ドロップし、必要に応じて設定します。

1. インポートしたファイルのデータを使用してデータベースを挿入し、更新します。

   これを行うには、 **[!UICONTROL Update data]** アクティビティをドラッグ&amp;ドロップし、 **[!UICONTROL Identification]** タブを選択して調整条件(この場合は **電子メール** フィールド)を追加します。

   ![](assets/extsignal_uc3.png)

1. 「 **[!UICONTROL Fields to update]** 」タブを選択し、データベースで更新するフィールド( **firstname** フィールドと **email** フィールド)を指定します。

   ![](assets/extsignal_uc4.png)

1. データがファイルから取得されるかどうかを確認します。 これを行うには、ワークフローに **[!UICONTROL Test]** アクティビティをドラッグ&amp;ドロップし、ボタンをクリックして条件を追加し **[!UICONTROL Add an element]** ます。
1. 条件に名前を付けて定義します。 この場合、アウトバウンドトランジションに次の構文のデータが含まれているかどうかをテストします。

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. データが取得された場合は、オーディエンスに保存します。 これを行うには、空ではない **[!UICONTROL Save audience]** ターゲットに **** アクティビティを追加し、トランジションを開きます。
1. この **[!UICONTROL Use a dynamic label]** オプションを選択し、 **fileToTarget** オーディエンスーのラベルとして使用します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. Workflow 2を呼び出すアクティビティをパラメーターと共にドラッグ&amp;ドロップし、開きます。 **[!UICONTROL End]**
1. タブを選択し、トリガするワークフローとそれに関連する信号アクティビティを指定し **[!UICONTROL External signal]** ます。
1. ワークフロー2内で使用するパラメーターと、それに関連する値を定義します。

   この例では、最初にAPI呼び出しで定義されたパラメーター(**fileToTarget** と **discountDesc**)と、追加の **segmentCode** パラメーター(「20% discount」)を一定値で渡します。

   ![](assets/extsignal_uc7.png)

ワークフロー1が設定され、ワークフロー2を構築できるようになりました。 詳しくは、[この節](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2)を参照してください。

## 手順3:ワークフローの設定2 {#step-3--configuring-workflow-2}

ワークフロー2は次のように構築されます。

* **[!UICONTROL External signal]** アクティビティ:ここで、ワークフロー内で使用するためにパラメーターを宣言する必要があります。
* **[!UICONTROL Read audience]** アクティビティ:は、ワークフロー1に保存されたオーディエンスを読み上げます。
* **[!UICONTROL Email delivery]** アクティビティ:パラメーターを使用してパーソナライズされたターゲットオーディエンスに定期的なメッセージを送信します。

![](assets/extsignal_uc_wkf2.png)

次の手順に従って、ワークフローを設定します。

1. ワークフロー1で定義したパラメーターを宣言します。

   これを行うには、 **[!UICONTROL External signal]** アクティビティを開き、ワークフロー1の **[!UICONTROL End]** アクティビティで定義されている各パラメータの名前とタイプを追加します。

   ![](assets/extsignal_uc8.png)

1. ワークフロー1に保存されたオーディエンスを使用します。 これを行うには、ワークフロー内に **[!UICONTROL Read audience]** アクティビティをドラッグ&amp;ドロップしてから開きます。
1. この **[!UICONTROL Use a dynamic audience]** オプションを選択し、読み取るオーディエンスの名前として **fileToTarget** パラメーターを使用します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. segmentCodeパラメーターに従って、送信トランジションに **名前を付けます** 。

   To do this, select the **[!UICONTROL Transition]** tab, then the **[!UICONTROL Use a dynamic segment code]** option.

1. 外部トランジションの名前として **segmentCode** パラメーターを使用します。

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. メッセージをオーディエンスに送信するには、 **[!UICONTROL Email delivery]** アクティビティをドラッグ&amp;ドロップします。
1. メッセージで使用するパラメータを指定し、discountDesc **** パラメータを使用してパーソナライズします。 これを行うには、アクティビティの詳細オプションを開き、パラメータ名と値を追加します。

   ![](assets/extsignal_uc10b.png)

1. これで、メッセージを設定できます。 アクティビティを開き、を選択し **[!UICONTROL Recurring email]**&#x200B;ます。

   ![](assets/extsignal_uc11.png)

1. 使用するテンプレートを選択し、必要に応じて電子メールのプロパティを定義します。
1. パーソナライゼーションフィールドとして **discountDesc** パラメータを使用します。 これを行うには、パーソナライゼーションフィールドリストから選択します。

   ![](assets/extsignal_uc13.png)

1. これで、メッセージの設定を完了し、通常どおり送信できます。

   ![](assets/extsignal_uc14.png)

## ワークフローの実行 {#executing-the-workflows}

ワークフローを構築したら、それらを実行できます。 API呼び出しを実行する前に、2つのワークフローが起動していることを確認します。

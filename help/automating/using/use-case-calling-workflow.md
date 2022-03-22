---
title: ワークフロー呼び出しの使用例
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 7a21f4f6-316f-4f3d-9d53-37d406a46aae
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 1%

---

# ユースケース {#use-case}

以下の使用例は、ワークフロー内でパラメーターを使用してワークフローを呼び出す方法を示しています。

目的は、外部パラメーターを使用して API 呼び出しからトリガーーを作成することです。 このワークフローは、ファイルからデータベースにデータを読み込み、関連するオーディエンスを作成します。 オーディエンスが作成されると、2 つ目のワークフローがトリガーされ、API 呼び出しで定義された外部パラメーターを使用してパーソナライズされたメッセージを送信します。

この使用例を実行するには、次の操作を実行する必要があります。

1. **API 呼び出しを実行する** 外部パラメーターを使用してトリガーワークフロー 1 に追加します。 詳しくは、 [手順 1:API 呼び出しの設定](../../automating/using/use-case-calling-workflow.md#step-1--configuring-the-api-call).
1. **ワークフロー 1 を作成**:ワークフローはファイルを転送し、データベースに読み込みます。 次に、データが空かどうかをテストし、最終的にプロファイルをオーディエンスに保存します。 最後に、トリガーWorkflow 2 です。 詳しくは、 [手順 2:ワークフロー 1 の設定](../../automating/using/use-case-calling-workflow.md#step-2--configuring-workflow-1).
1. **ワークフローを作成 2**:ワークフローは、Workflow 1 で作成されたオーディエンスを読み取り、パラメーターを使用してカスタマイズされたセグメントコードと共に、パーソナライズされたメッセージをプロファイルに送信します。 詳しくは、 [手順 3:ワークフロー 2 の設定](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

![](assets/extsignal_uc_process.png)

## 前提条件 {#prerequisites}

ワークフローを設定する前に、 **[!UICONTROL External signal]** 各アクティビティに含まれています。 これにより、ワークフローの呼び出し時に、これらのシグナルアクティビティをターゲットに設定できます。

## 手順 1:API 呼び出しの設定 {#step-1--configuring-the-api-call}

パラメーターを指定して、トリガーワークフロー 1 に対する API 呼び出しを実行します。 API 呼び出しの構文について詳しくは、 [Campaign StandardREST API のドキュメント](../../api/using/triggering-a-signal-activity.md).

この場合、次のパラメーターを使用してワークフローを呼び出します。

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

## 手順 2:ワークフロー 1 の設定 {#step-2--configuring-workflow-1}

ワークフロー 1 は次のように構築されます。

* **[!UICONTROL External signal]** アクティビティ：ワークフロー内で使用するには、外部パラメーターを宣言する必要があります。
* **[!UICONTROL Transfer file]** アクティビティ：は、パラメーターで定義された名前でファイルをインポートします。
* **[!UICONTROL Load file]** アクティビティ：は、インポートしたファイルからデータベースにデータを読み込みます。
* **[!UICONTROL Update data]** アクティビティ：インポートしたファイルのデータを使用してデータベースを挿入または更新します。
* **[!UICONTROL Test]** アクティビティ：読み込まれたデータがあるかどうかを確認します。
* **[!UICONTROL Save audience]** アクティビティ：ファイルにデータが含まれている場合、はプロファイルをオーディエンスに保存します。
* **[!UICONTROL End activity]** アクティビティ：内で使用するパラメーターを指定して、ワークフロー 2 を呼び出します。

![](assets/extsignal_uc_wkf1.png)

次の手順に従って、ワークフローを設定します。

1. API 呼び出しで定義されたパラメーターを宣言します。 これをおこなうには、 **[!UICONTROL External signal]** 「 」アクティビティを開き、パラメーターの名前とタイプを追加します。

   ![](assets/extsignal_uc1.png)

1. を追加します。 **[!UICONTROL Transfer file]** 「 」アクティビティを使用してデータをデータベースにインポートします。それには、「 」アクティビティをドラッグ&amp;ドロップして開き、 **[!UICONTROL Protocol]** タブをクリックします。
1. を選択します。 **[!UICONTROL Use a dynamic file path]** オプションを選択した場合、 **fileToTarget** パラメーターを次のように指定して転送します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. ファイルからデータベースにデータを読み込みます。

   これをおこなうには、 **[!UICONTROL Load file]** 「 」アクティビティをワークフローに追加し、必要に応じて設定します。

1. データベースを挿入し、インポートしたファイルのデータで更新します。

   これをおこなうには、 **[!UICONTROL Update data]** 「 」アクティビティで、 **[!UICONTROL Identification]** タブをクリックして紐付け条件 ( **電子メール** フィールド ) に書き込まれます。

   ![](assets/extsignal_uc3.png)

1. を選択します。 **[!UICONTROL Fields to update]** 」タブをクリックし、更新するフィールドをデータベース内で指定します ( この場合は **名** および **電子メール** フィールド ) を参照してください。

   ![](assets/extsignal_uc4.png)

1. データがファイルから取得されるかどうかを確認します。 これをおこなうには、 **[!UICONTROL Test]** 「 」アクティビティをワークフローに追加し、 **[!UICONTROL Add an element]** ボタンを使用して条件を追加します。
1. 条件に名前を付けて定義します。 この例では、アウトバウンドトランジションに次の構文のデータが含まれているかどうかをテストします。

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. データが取得された場合は、そのデータをオーディエンスに保存します。 これをおこなうには、 **[!UICONTROL Save audience]** アクティビティの **ターゲットが空ではありません** トランジションを選択し、開きます。
1. を選択します。 **[!UICONTROL Use a dynamic label]** オプションを選択した場合、 **fileToTarget** パラメーターをオーディエンスのラベルとして使用します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. ドラッグ&amp;ドロップ **[!UICONTROL End]** 「 」アクティビティを開きます。
1. を選択します。 **[!UICONTROL External signal]** 「 」タブをクリックし、ワークフローを指定して、「 」トリガーとそれに関連するシグナルアクティビティを設定します。
1. ワークフロー 2 内で使用するパラメーターと、それに関連する値を定義します。

   ここでは、元々 API 呼び出し (**fileToTarget** および **discountDesc**)、および追加の **segmentCode** パラメーターに定数値（「20%割引」）を割り当てます。

   ![](assets/extsignal_uc7.png)

ワークフロー 1 が設定され、ワークフロー 2 を作成できるようになりました。 詳しくは、[この節](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2)を参照してください。

## 手順 3:ワークフロー 2 の設定 {#step-3--configuring-workflow-2}

ワークフロー 2 は、次のように構築されます。

* **[!UICONTROL External signal]** アクティビティ：ワークフロー内で使用するには、ここでパラメーターを宣言する必要があります。
* **[!UICONTROL Read audience]** アクティビティ：は、Workflow 1 に保存されたオーディエンスを読み取ります。
* **[!UICONTROL Email delivery]** アクティビティ：は、パラメーターを使用してパーソナライズされた、ターゲットオーディエンスに繰り返しメッセージを送信します。

![](assets/extsignal_uc_wkf2.png)

次の手順に従って、ワークフローを設定します。

1. ワークフロー 1 で定義したパラメーターを宣言します。

   これをおこなうには、 **[!UICONTROL External signal]** 「 」アクティビティを追加し、 **[!UICONTROL End]** ワークフロー 1 の「 」アクティビティ

   ![](assets/extsignal_uc8.png)

1. ワークフロー 1 に保存されたオーディエンスを使用します。 これをおこなうには、 **[!UICONTROL Read audience]** 「 」アクティビティをワークフローに追加し、開きます。
1. を選択します。 **[!UICONTROL Use a dynamic audience]** オプションを選択した場合、 **fileToTarget** 読み取るオーディエンスの名前としてのパラメーター：

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. 以下に従ってアウトバウンドトランジションに名前を付けます。 **segmentCode** パラメーター。

   これをおこなうには、「 **[!UICONTROL Transition]** タブ、 **[!UICONTROL Use a dynamic segment code]** オプション。

1. 以下を使用： **segmentCode** アウトバウンドトランジションの名前としてのパラメーター：

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. ドラッグ&amp;ドロップ **[!UICONTROL Email delivery]** アクティビティを使用して、オーディエンスにメッセージを送信します。
1. メッセージ内で使用するパラメーターを特定し、 **discountDesc** パラメーター。 これをおこなうには、アクティビティの詳細設定オプションを開き、パラメーター名と値を追加します。

   ![](assets/extsignal_uc10b.png)

1. これで、メッセージを設定できます。 アクティビティを開き、「 」を選択します。 **[!UICONTROL Recurring email]**.

   ![](assets/extsignal_uc11.png)

1. 使用するテンプレートを選択し、必要に応じて E メールのプロパティを定義します。
1. 以下を使用： **discountDesc** パーソナライゼーションフィールドとしてのパラメーター。 これをおこなうには、パーソナライゼーションフィールドリストから選択します。

   ![](assets/extsignal_uc13.png)

1. これで、メッセージの設定を完了し、通常どおりに送信できます。

   ![](assets/extsignal_uc14.png)

## ワークフローの実行 {#executing-the-workflows}

ワークフローを作成したら、ワークフローを実行できます。 API 呼び出しを実行する前に、2 つのワークフローが開始されていることを確認します。

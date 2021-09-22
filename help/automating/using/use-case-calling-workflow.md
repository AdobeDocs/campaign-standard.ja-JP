---
title: 外部パラメーターを使用したワークフローの呼び出し
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 7a21f4f6-316f-4f3d-9d53-37d406a46aae
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 1%

---

# ユースケース {#use-case}

以下の使用例は、ワークフロー内でパラメーターを使用してワークフローを呼び出す方法を示しています。

目的は、外部パラメーターを使用してAPI呼び出しからトリガーを作成することです。 このワークフローは、ファイルからデータベースにデータを読み込み、関連するオーディエンスを作成します。 オーディエンスが作成されると、2つ目のワークフローがトリガーされ、API呼び出しで定義された外部パラメーターを使用してパーソナライズされたメッセージが送信されます。

この使用例を実行するには、次の操作を実行する必要があります。

1. **外部パラメーターを使用し** て、トリガーワークフロー1へのAPI呼び出しを行います。[手順1を参照してください。API呼び出し](../../automating/using/use-case-calling-workflow.md#step-1--configuring-the-api-call)を設定します。
1. **ワークフロー1の作成**:ワークフローは、ファイルを転送し、データベースに読み込みます。次に、データが空かどうかをテストし、最終的にプロファイルをオーディエンスに保存します。 最後に、ワークフロー2をトリガーします。 [手順2を参照してください。ワークフロー1](../../automating/using/use-case-calling-workflow.md#step-2--configuring-workflow-1)を設定します。
1. **ビルドワークフロー2**:ワークフローは、ワークフロー1で作成されたオーディエンスを読み取り、パラメーターを使用してカスタマイズされたセグメントコードと共に、パーソナライズされたメッセージをプロファイルに送信します。[手順3を参照してください。ワークフロー2](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2)を設定します。

![](assets/extsignal_uc_process.png)

## 前提条件 {#prerequisites}

ワークフローを設定する前に、それぞれに&#x200B;**[!UICONTROL External signal]**&#x200B;アクティビティを含むワークフロー1と2を作成する必要があります。 これにより、ワークフローを呼び出す際に、これらのシグナルアクティビティをターゲットに設定できます。

## 手順1:API呼び出しの設定 {#step-1--configuring-the-api-call}

パラメーターを使用して、トリガーワークフロー1へのAPI呼び出しを実行します。 API呼び出しの構文について詳しくは、[Campaign StandardREST APIのドキュメント](../../api/using/triggering-a-signal-activity.md)を参照してください。

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

## 手順2:ワークフロー1の設定 {#step-2--configuring-workflow-1}

ワークフロー1は次のように構築されます。

* **[!UICONTROL External signal]** アクティビティ：ワークフロー内で使用するには、外部パラメーターを宣言する必要があります。
* **[!UICONTROL Transfer file]** アクティビティ：は、パラメーターで定義された名前でファイルをインポートします。
* **[!UICONTROL Load file]** アクティビティ：は、インポートしたファイルからデータベースにデータを読み込みます。
* **[!UICONTROL Update data]** アクティビティ：インポートしたファイルのデータをデータベースに挿入または更新します。
* **[!UICONTROL Test]** アクティビティ：は、読み込まれたデータがあるかどうかを確認します。
* **[!UICONTROL Save audience]** アクティビティ：ファイルにデータが含まれている場合、はプロファイルをオーディエンスに保存します。
* **[!UICONTROL End activity]** アクティビティ：内で使用するパラメーターを指定して、ワークフロー2を呼び出します。

![](assets/extsignal_uc_wkf1.png)

次の手順に従って、ワークフローを設定します。

1. API呼び出しで定義されたパラメーターを宣言します。 これをおこなうには、**[!UICONTROL External signal]**&#x200B;アクティビティを開き、パラメーターの名前とタイプを追加します。

   ![](assets/extsignal_uc1.png)

1. データをデータベースにインポートする&#x200B;**[!UICONTROL Transfer file]**&#x200B;アクティビティを追加します。それには、アクティビティをドラッグ&amp;ドロップして開き、「**[!UICONTROL Protocol]**」タブを選択します。
1. **[!UICONTROL Use a dynamic file path]**&#x200B;オプションを選択し、**fileToTarget**&#x200B;パラメーターを転送するファイルとして使用します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. ファイルからデータベースにデータを読み込みます。

   これをおこなうには、ワークフローに「**[!UICONTROL Load file]**」アクティビティをドラッグ&amp;ドロップし、必要に応じて設定します。

1. インポートしたファイルのデータをデータベースに挿入し、更新します。

   これをおこなうには、**[!UICONTROL Update data]**&#x200B;アクティビティをドラッグ&amp;ドロップし、「**[!UICONTROL Identification]**」タブを選択して紐付け条件（この場合は「**email**」フィールド）を追加します。

   ![](assets/extsignal_uc3.png)

1. 「**[!UICONTROL Fields to update]**」タブを選択し、データベースで更新するフィールドを指定します（この例では、**firstname**&#x200B;フィールドと&#x200B;**email**&#x200B;フィールド）。

   ![](assets/extsignal_uc4.png)

1. データがファイルから取得されたかどうかを確認します。 これをおこなうには、ワークフローに「**[!UICONTROL Test]**」アクティビティをドラッグ&amp;ドロップしてから、「**[!UICONTROL Add an element]**」ボタンをクリックして条件を追加します。
1. 条件に名前を付けて定義します。 この例では、アウトバウンドトランジションに次の構文のデータが含まれているかどうかをテストします。

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. データが取得された場合は、そのデータをオーディエンスに保存します。 それには、**[!UICONTROL Save audience]**&#x200B;アクティビティを&#x200B;**Target not empty**&#x200B;トランジションに追加してから開きます。
1. **[!UICONTROL Use a dynamic label]**&#x200B;オプションを選択し、 **fileToTarget**&#x200B;パラメーターをオーディエンスのラベルとして使用します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. パラメーターを指定してワークフロー2を呼び出す&#x200B;**[!UICONTROL End]**&#x200B;アクティビティをドラッグ&amp;ドロップし、開きます。
1. 「 **[!UICONTROL External signal]** 」タブを選択し、ワークフローとそれに関連するシグナルアクティビティをトリガーします。
1. ワークフロー2内で使用するパラメーターと、それに関連する値を定義します。

   この例では、API呼び出し（**fileToTarget**&#x200B;と&#x200B;**discountDesc**）で最初に定義したパラメーターと、定数値（「20%割引」）を持つ追加の&#x200B;**segmentCode**&#x200B;パラメーターを渡します。

   ![](assets/extsignal_uc7.png)

ワークフロー1が設定され、ワークフロー2を作成できるようになりました。 詳しくは、[この節](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2)を参照してください。

## 手順3:ワークフローの設定2 {#step-3--configuring-workflow-2}

ワークフロー2は、次のように構築されます。

* **[!UICONTROL External signal]** アクティビティ：ワークフロー内で使用するには、パラメーターを宣言する必要があります。
* **[!UICONTROL Read audience]** アクティビティ：は、ワークフロー1に保存されたオーディエンスを読み取ります。
* **[!UICONTROL Email delivery]** アクティビティ：パラメーターを使用してパーソナライズされた、ターゲットオーディエンスに繰り返しメッセージを送信します。

![](assets/extsignal_uc_wkf2.png)

次の手順に従って、ワークフローを設定します。

1. ワークフロー1で定義したパラメーターを宣言します。

   これをおこなうには、**[!UICONTROL External signal]**&#x200B;アクティビティを開き、ワークフロー1の&#x200B;**[!UICONTROL End]**&#x200B;アクティビティで定義された各パラメーターの名前とタイプを追加します。

   ![](assets/extsignal_uc8.png)

1. ワークフロー1に保存されたオーディエンスを使用します。 これをおこなうには、**[!UICONTROL Read audience]**&#x200B;アクティビティをワークフローにドラッグ&amp;ドロップして開きます。
1. **[!UICONTROL Use a dynamic audience]**&#x200B;オプションを選択し、読み取るオーディエンスの名前として&#x200B;**fileToTarget**&#x200B;パラメーターを使用します。

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. **segmentCode**&#x200B;パラメーターに従って、アウトバウンドトランジションの名前を付けます。

   それには、「**[!UICONTROL Transition]**」タブを選択し、「**[!UICONTROL Use a dynamic segment code]**」オプションを選択します。

1. アウトバウンドトランジションの名前として、**segmentCode**&#x200B;パラメーターを使用します。

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. **[!UICONTROL Email delivery]**&#x200B;アクティビティをドラッグ&amp;ドロップして、オーディエンスにメッセージを送信します。
1. メッセージ内で使用するパラメーターを指定し、 **discountDesc**&#x200B;パラメーターを使用してパーソナライズします。 これをおこなうには、アクティビティの詳細設定オプションを開き、パラメーター名と値を追加します。

   ![](assets/extsignal_uc10b.png)

1. これで、メッセージを設定できます。 アクティビティを開き、「**[!UICONTROL Recurring email]**」を選択します。

   ![](assets/extsignal_uc11.png)

1. 使用するテンプレートを選択し、必要に応じてEメールのプロパティを定義します。
1. **discountDesc**&#x200B;パラメーターをパーソナライゼーションフィールドとして使用します。 これをおこなうには、パーソナライゼーションフィールドリストから選択します。

   ![](assets/extsignal_uc13.png)

1. これで、メッセージの設定を完了し、通常どおりに送信できます。

   ![](assets/extsignal_uc14.png)

## ワークフローの実行 {#executing-the-workflows}

ワークフローを作成したら、ワークフローを実行できます。 API呼び出しを実行する前に、2つのワークフローが開始されていることを確認します。

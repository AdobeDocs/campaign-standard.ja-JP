---
title: 関係を使用したデータ調整
description: 次の例は、ファイル内の購入データを使用してデータベースを更新するワークフローを示しています。
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---


# 関係を使用したデータ調整 {#reconciliation-relations}

次の例は、ファイル内の購入データを使用してデータベースを更新するワークフローを示しています。 購入データには、クライアントの電子メールや製品コードなど、他のディメンションからの要素を参照するデータが含まれます。

>[!NOTE]
>
>この例で使用される **Transactions** と **Products** （商品）リソースは、デフォルトではAdobe Campaignデータベースに存在しません。 したがって、これらは [カスタムリソース](../../developing/using/data-model-concepts.md) 関数を使用してあらかじめ作成されています。 読み込んだファイルの電子メールアドレスに対応するプロファイルと製品は、事前にデータベースに読み込まれていました。

ワークフローは、次のアクティビティで構成されています。

![](assets/reconciliation_example1.png)

* 読み込むファイル [アクティビティ](../../automating/using/load-file.md) 。読み込むファイルのデータを読み込んで検出します。 読み込まれたファイルには次のデータが含まれています。

   * トランザクション日
   * クライアントの電子メールアドレス
   * 購入した製品のコード

   ```
   date;client;product
   2015-05-19 09:00:00;mail1@email.com;ZZ1
   2015-05-19 09:01:00;mail2@email.com;ZZ2
   2015-05-19 09:01:01;mail3@email.com;ZZ2
   2015-05-19 09:01:02;mail4@email.com;ZZ2
   2015-05-19 09:02:00;mail5@email.com;ZZ3
   2015-05-19 09:03:00;mail6@email.com;ZZ4
   2015-05-19 09:04:00;mail7@email.com;ZZ5
   2015-05-19 09:05:00;mail8@email.com;ZZ7
   2015-05-19 09:06:00;mail9@email.com;ZZ6
   ```

* 購買データを製品だけでなくデータベースプロファイルに連結する [](../../automating/using/reconciliation.md) 調整アクティビティ。 したがって、ファイルデータとプロファイルテーブル、および製品テーブルとの間の関係を定義する必要があります。 この設定は、アクティビティの **[!UICONTROL Relations]** タブで行われます。

   * プロファイルとの関係 ****: ファイルの **client** 列は、 **プロファイルディメンションの** email **** フィールドにリンクされます。
   * 製品との関係 ****: ファイルの **product** 列は、 **プロファイルディメンションのproductCode** フィールドにリンクされています **** 。
   列は、リンクされたディメンションの外部キーを参照するために、受信データに追加されます。

   ![](assets/reconciliation_example3.png)

* 「 [データを更新](../../automating/using/update-data.md) 」アクティビティを使用すると、インポートしたデータを使用して更新するデータベースフィールドを定義できます。 前のアクティビティの **Transactions** （トランザクション）ディメンションに属するデータが既に識別されているので、次の **[!UICONTROL Directly using the targeting dimension]** IDオプションを使用できます。

   更新するフィールドを自動的に検出するオプションを使用すると、以前のアクティビティで設定したリンク(プロファイルや商品へのリンク)がのリストに追加され **[!UICONTROL Fields to update]**&#x200B;ます。 また、取引日に対応するフィールドがこのリストに正しく追加されていることを確認する必要があります。

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)

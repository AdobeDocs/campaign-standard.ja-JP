---
title: 関数のリスト
description: クエリ編集ツールを使用すると、高度な関数を使用して複雑なフィルタリングを実行できます。
page-status-flag: 非活性化の
uuid: fd50fc99-1e7a-479b-beb7-1f246b419d46
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: filtering-data
discoiquuid: 3cdbe962-1c59-4cd8-b29e-36aa2562fac6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 関数のリスト{#list-of-functions}

## 関数について {#about-functions}

クエリ編集ツールを使用すると、高度な関数を使用して複雑なフィルタリングを実行できます。 これを行うには、ワークスペースで使用で **[!UICONTROL Expression]** きる要素がツールパレットに含まれます。 この要素の詳細については、各節で説 [明します](../../automating/using/advanced-expression-editing.md)。

この要素を使用すると、手動で条件を入力できます。 ここでは、以下の節で定義した関数を使用できます。

目的の結果と操作データのタイプに応じて、次の関数タイプを使用できます。

* 日付
* Geomarketing
* 数値
* その他の関数
* 集計
* 文字列操作
* 並べ替え

## 日付 {#dates}

日付関数は、日付や時間の値を操作するために使用します。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名前</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddDays</strong><br /> </td> 
   <td> 日付に日数を追加します<br /> </td> 
   <td> AddDays(&lt;日付&gt;, &lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddHours</strong><br /> </td> 
   <td> 日付に時間数を追加します<br /> </td> 
   <td> AddHours(&lt;日付&gt;, &lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMinutes</strong><br /> </td> 
   <td> 日付に分数を追加します<br /> </td> 
   <td> AddMinutes(&lt;日付&gt;, &lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMonths</strong><br /> </td> 
   <td> 日付に月数を追加します<br /> </td> 
   <td> AddMonths(&lt;日付&gt;, &lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddSeconds</strong><br /> </td> 
   <td> 日付に秒数を追加します<br /> </td> 
   <td> AddSeconds(&lt;日付&gt;, &lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddYears</strong><br /> </td> 
   <td> 日付に年数を追加します<br /> </td> 
   <td> AddYears(&lt;日付&gt;, &lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DateOnly</strong><br /> </td> 
   <td> 日付のみを返します（時刻は 0:00）<br /> </td> 
   <td> DateOnly(&lt;日付&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>日</strong><br /> </td> 
   <td> 日付の日を表す数を返します<br /> </td> 
   <td> Day(&lt;日付&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DayOfYear</strong><br /> </td> 
   <td> 日付の年を表す数を返します<br /> </td> 
   <td> DayOfYear(&lt;日付&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgo</strong><br /> </td> 
   <td> 現在の日付 - n 日を返します<br /> </td> 
   <td> DaysAgo(&lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgoInt</strong><br /> </td> 
   <td> 現在の日付 - n 日を (整数 yyyymmdd として) 返します<br /> </td> 
   <td> DaysAgoInt(&lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysDiff</strong><br /> </td> 
   <td> 2 つの日付の間の日数を返します<br /> </td> 
   <td> DaysDiff(&lt;終了日&gt;, &lt;開始日&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysOld</strong><br /> </td> 
   <td> 年齢（日数）を返します<br /> </td> 
   <td> DaysOld(&lt;日付&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetDate</strong><br /> </td> 
   <td> サーバーの現在のシステム日付を返します<br /> </td> 
   <td> GetDate()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>時間</strong><br /> </td> 
   <td> 日付の時間を返します<br /> </td> 
   <td> Hour(&lt;日付&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HoursDiff</strong><br /> </td> 
   <td> 2 つの日付の間の時間数を返します<br /> </td> 
   <td> HoursDiff(&lt;終了日&gt;, &lt;開始日&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LocalToUTC</strong><br /> </td> 
   <td> 現地の日時をUTCに変換します。<br /> </td> 
   <td> LocalToUTC（&lt;日付&gt;, &lt;タイムゾーン&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>分</strong><br /> </td> 
   <td> 日付の分を返します<br /> </td> 
   <td> Minute(&lt;日付&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MinutesDiff</strong><br /> </td> 
   <td> 2 つの日付の間の分数を返します<br /> </td> 
   <td> MinutesDiff(&lt;終了日&gt;, &lt;開始日&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>月</strong><br /> </td> 
   <td> 日付の月を表す数を返します<br /> </td> 
   <td> Month(&lt;日付&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsAgo</strong><br /> </td> 
   <td> 現在の日付 - n ヶ月に対応する日付を返します<br /> </td> 
   <td> MonthsAgo(&lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsDiff</strong><br /> </td> 
   <td> 2 つの日付の間の月数を返します<br /> </td> 
   <td> MonthsDiff(&lt;終了日&gt;, &lt;開始日&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsOld</strong><br /> </td> 
   <td> 年齢（月数）を返します<br /> </td> 
   <td> MonthsOld(&lt;日付&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>秒</strong><br /> </td> 
   <td> 日付の秒を返します<br /> </td> 
   <td> Second(&lt;日付&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>古い</strong><br /> </td> 
   <td> 最も古い日付を返します。 </td> 
   <td> 最も古い（&lt;日付&gt;, &lt;日付&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SecondsDiff</strong><br /> </td> 
   <td> 2 つの日付の間の秒数を返します<br /> </td> 
   <td> SecondsDiff(&lt;終了日&gt;, &lt;開始日&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubDays</strong><br /> </td> 
   <td> 日付から日数を引きます<br /> </td> 
   <td> SubDays(&lt;日付&gt;, &lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubHours</strong><br /> </td> 
   <td> 日付から時間数を引きます<br /> </td> 
   <td> SubHours(&lt;日付&gt;, &lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubMinutes</strong><br /> </td> 
   <td> 日付から分数を引きます<br /> </td> 
   <td> SubMinutes(&lt;日付&gt;, &lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubMonths</strong><br /> </td> 
   <td> 日付から月数を引きます<br /> </td> 
   <td> SubMonths(&lt;日付&gt;, &lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubSeconds</strong><br /> </td> 
   <td> 日付から秒数を引きます<br /> </td> 
   <td> SubSeconds(&lt;日付&gt;, &lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>サブ年</strong><br /> </td> 
   <td> 日付から年数を引きます<br /> </td> 
   <td> SubYears(&lt;日付&gt;, &lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>終了日</strong><br /> </td> 
   <td> 日付 + 時間を日付に変換します<br /> </td> 
   <td> ToDate(&lt;日付 + 時刻&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTime</strong><br /> </td> 
   <td> 文字列を日付 + 時刻に変換します<br /> </td> 
   <td> ToDateTime(&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTimeWithTimezone</strong><br /> </td> 
   <td> 文字列を日付+タイムゾーンに変換します。<br /> 例：ToDateTimeWithTimezone ("2019-02-19 08:09:00", "Asia/Theran")<br /> </td> 
   <td> ToDateTimeWithTimezone（&lt;文字列&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDate</strong><br /> </td> 
   <td> 日付 + 時刻を最も近い秒に丸めます<br /> </td> 
   <td> TruncDate(@lastModified, &lt;秒数&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDateTZ</strong><br /> </td> 
   <td> 日付と時刻を指定された精度（秒）に丸めます<br /> </td> 
   <td> TruncDateTZ(&lt;日付&gt;, &lt;秒数&gt;, &lt;タイムゾーン&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncQuarter</strong><br /> </td> 
   <td> 日付を四半期に丸めます<br /> </td> 
   <td> TruncQuarter(&lt;日付&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncTime</strong><br /> </td> 
   <td> 時刻部分を最も近い秒に丸めます<br /> </td> 
   <td> TruncTime(&lt;日付&gt;, &lt;秒数&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncWeek</strong><br /> </td> 
   <td> 日付を週に丸めます<br /> </td> 
   <td> TruncWeek(&lt;日付&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncYear</strong><br /> </td> 
   <td> 日付 + 時刻をその年の 1 月 1 日に丸めます<br /> </td> 
   <td> TruncYear(&lt;日付&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>WeekDay</strong><br /> </td> 
   <td> 日付の週の日を表す数を返します<br /> </td> 
   <td> WeekDay(&lt;日付&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>年</strong><br /> </td> 
   <td> 日付の年を表す数を返します<br /> </td> 
   <td> Year(&lt;日付&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearAnd Month</strong><br /> </td> 
   <td> 日付の年と月を表す数を返します<br /> </td> 
   <td> YearAndMonth(&lt;日付&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsDiff</strong><br /> </td> 
   <td> 2 つの日付の間の年数を返します<br /> </td> 
   <td> YearsDiff(&lt;終了日&gt;, &lt;開始日&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsOld</strong><br /> </td> 
   <td> 満年齢を返します<br /> </td> 
   <td> YearsOld(&lt;日付&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Geomarketing {#geomarketing}

ジオマーケティング関数は、地理的な値を操作するために使用します。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名前</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>距離</strong><br /> </td> 
   <td> Returns the distance in kilometers between two points defined by their longitude and latitude (expressed in degrees)<br /> </td> 
   <td> Distance(&lt;経度 A&gt;, &lt;緯度 A&gt;, &lt;経度 B&gt;, &lt;緯度 B&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 数値 {#numerical}

数値関数は、テキストを数値に変換するために使用します。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名前</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Abs</strong><br /> </td> 
   <td> 数値の絶対値を返します<br /> </td> 
   <td> Abs(&lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>セイル</strong><br /> </td> 
   <td> ある特定の数値以上の最小の整数を返します<br /> </td> 
   <td> Ceil(&lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>床</strong><br /> </td> 
   <td> ある特定の数値以上の最大の整数を返します<br /> </td> 
   <td> Floor(&lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最大</strong><br /> </td> 
   <td> 2 つの数のうち大きい方を返します<br /> </td> 
   <td> Greatest(&lt;数値 1&gt;, &lt;数値 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最小</strong><br /> </td> 
   <td> 2 つの数のうち小さい方を返します<br /> </td> 
   <td> Least(&lt;数値 1&gt;, &lt;数値 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> 整数の割り算 n1 ÷ n2 の余りを返します<br /> </td> 
   <td> Mod（&lt;数値1&gt;, &lt;数値2&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>パーセント</strong><br /> </td> 
   <td> 割合で表される 2 つの数の比率を返します<br /> </td> 
   <td> Percent(&lt;数値 1&gt;, &lt;数値 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ランダム</strong><br /> </td> 
   <td> ランダムな値を返します<br /> </td> 
   <td> Random()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>丸</strong><br /> </td> 
   <td> 数値を n 桁に丸めます<br /> </td> 
   <td> TruncTime(&lt;数値&gt;, &lt;小数点以下の桁数&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>署名</strong><br /> </td> 
   <td> 数値の符号を返します<br /> </td> 
   <td> Sign(&lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDouble</strong><br /> </td> 
   <td> 整数を浮動小数に変換します<br /> </td> 
   <td> ToDouble(&lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> 浮動小数を 64 ビットの整数に変換します<br /> </td> 
   <td> ToInt64(&lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInteger</strong><br /> </td> 
   <td> 浮動小数を整数に変換します<br /> </td> 
   <td> ToInteger(&lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>トルンク</strong><br /> </td> 
   <td> n1 を n2 の桁数に切り捨てます<br /> </td> 
   <td> Trunc(&lt;n1&gt;, &lt;n2&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## その他 {#others}

この表には、使用可能な残りの関数が含まれています。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名前</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ケース</strong><br /> </td> 
   <td> 条件が検証された場合、値1を返します。 それ以外の場合は、値2を返します。<br /> </td> 
   <td> (When(&lt;条件&gt;, &lt;値 1&gt;), Else(&lt;値 2&gt;))<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ClearBit</strong><br /> </td> 
   <td> 値のフラグを削除します<br /> </td> 
   <td> ClearBit(&lt;識別子&gt;, &lt;フラグ&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Coalesce</strong><br /> </td> 
   <td> 値 1 がゼロまたは null の場合は値 2 を返し、それ以外の場合は値 1 を返します<br /> </td> 
   <td> Coalesce(&lt;値 1&gt;, &lt;値 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>デコード</strong><br /> </td> 
   <td> 戻り値3は値1 =値2、それ以外の場合は4<br /> </td> 
   <td> Decode(&lt;値 1&gt;, &lt;値 2&gt;, &lt;値 3&gt;, &lt;値 4&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Else</strong><br /> </td> 
   <td> 値 1 を返します（case 関数のパラメーターとしてのみ使用できます）<br /> </td> 
   <td> Else(&lt;値 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetEmailDomain</strong><br /> </td> 
   <td> Extracts the domain from an email address<br /> </td> 
   <td> GetEmailDomain(&lt;値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetMirrorURL</strong><br /> </td> 
   <td> ミラーページサーバーの URL を取得します<br /> </td> 
   <td> GetMirrorURL(&lt;値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Iif</strong><br /> </td> 
   <td> 式がtrueの場合は値1を返し、それ以外の場合は値2を返します<br /> </td> 
   <td> Iif(&lt;条件&gt;, &lt;値 1&gt;, &lt;値 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsBitSet</strong><br /> </td> 
   <td> 値にフラグが含まれているかどうかを示します<br /> </td> 
   <td> IsBitSet(&lt;識別子&gt;, &lt;フラグ&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsEmptyString</strong><br /> </td> 
   <td> Returns value 2 if the string is empty, otherwise returns value 3<br /> </td> 
   <td> IsEmptyString(&lt;string&gt;, &lt;value 2&gt;, &lt;value 3&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>NoNull</strong><br /> </td> 
   <td> 引数が NULL の場合は、空の文字列を返します<br /> </td> 
   <td> NoNull(&lt;値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowId</strong><br /> </td> 
   <td> ライン番号を返します<br /> </td> 
   <td> RowId<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SetBit</strong><br /> </td> 
   <td> 値に強制的にフラグを指定します<br /> </td> 
   <td> SetBit(&lt;識別子&gt;, &lt;フラグ&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToBoolean</strong><br /> </td> 
   <td> 数値をブール値に変換します<br /> </td> 
   <td> ToBoolean(&lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>タイミング</strong><br /> </td> 
   <td> 式が検証された場合、値1を返します。 Otherwise, returns value 2 (may only be used as a parameter of the case function)<br /> </td> 
   <td> When(&lt;条件&gt;, &lt;値 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>newUUID</strong><br /> </td> 
   <td> 新しいUUIDを返します。<br /> </td> 
   <td> newUUID<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 文字列 {#string}

文字列関数は、一連の文字列を操作するために使用されます。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名前</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull2</strong><br /> </td> 
   <td> すべてのパラメーターが null でなく空でもないかどうかを示します<br /> </td> 
   <td> AllNonNull2(&lt;文字列&gt;, &lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> すべてのパラメーターが null でなく空でもないかどうかを示します<br /> </td> 
   <td> AllNonNull3(&lt;文字列&gt;, &lt;文字列&gt;, &lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> Returns the ASCII value of the first character in the string<br /> </td> 
   <td> Ascii(&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>文字</strong><br /> </td> 
   <td> ASCII コード「n」に対応する文字を返します<br /> </td> 
   <td> Char(&lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> 文字列 1 における文字列 2 の位置を返します<br /> </td> 
   <td> Charindex(&lt;文字列&gt;, &lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DataLength</strong><br /> </td> 
   <td> 文字列内の文字数を返します。<br /> </td> 
   <td> DataLength(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetLine</strong><br /> </td> 
   <td> 文字列の n 番目（1 から n）のラインを返します<br /> </td> 
   <td> GetLine(&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IfEquals</strong><br /> </td> 
   <td> 最初の 2 つのパラメーターが等しい場合は 3 番目のパラメーターを返し、それ以外の場合は最後のパラメーターを返します<br /> </td> 
   <td> IfEquals(&lt;文字列&gt;, &lt;文字列&gt;, &lt;文字列&gt;, &lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsMemoNull</strong><br /> </td> 
   <td> パラメーターとして渡されたメモが null かどうかを示します<br /> </td> 
   <td> IsMemoNull(&lt;メモ&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords</strong><br /> </td> 
   <td> パラメーターとして渡された2つの文字列を含めます。 戻り値の各文字列の間にスペースが追加されます。<br /> </td> 
   <td> JuxtWords(&lt;文字列&gt;, &lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> パラメーターとして渡された3つの文字列を含めます。 戻り値の各文字列の間にスペースが追加されます。<br /> </td> 
   <td> JuxtWords3(&lt;string&gt;, &lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LPad</strong><br /> </td> 
   <td> 左側の完成した文字列を返します<br /> </td> 
   <td> LPad(&lt;文字列&gt;, &lt;数値&gt;, &lt;文字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>左</strong><br /> </td> 
   <td> 文字列の最初の n 文字を返します<br /> </td> 
   <td> Left(&lt;文字列&gt;, &lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>長さ</strong><br /> </td> 
   <td> 文字列の長さを返す<br /> </td> 
   <td> Length(&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>下</strong><br /> </td> 
   <td> 文字列を小文字で返します<br /> </td> 
   <td> Lower(&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ltrim</strong><br /> </td> 
   <td> 文字列の左側の空白を削除します<br /> </td> 
   <td> Ltrim(&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> 文字列の MD5 キーの 16 進数表現を返します<br /> </td> 
   <td> Md5Digest(&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MemoContains</strong><br /> </td> 
   <td> パラメーターとして渡す文字列をメモに含めるかどうかを指定します<br /> </td> 
   <td> MemoContains(&lt;メモ&gt;、&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RPad</strong><br /> </td> 
   <td> 右側の完成した文字列を返します<br /> </td> 
   <td> RPad(&lt;文字列&gt;, &lt;数値&gt;, &lt;文字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>置換</strong><br /> </td> 
   <td> 文字列（1番目のパラメータ）内で指定した文字列（2番目のパラメータ）値を別の文字列値（3番目のパラメータ）に置き換えます。<br /> </td> 
   <td> Replace(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>右</strong><br /> </td> 
   <td> 文字列の最後の n 文字を返します<br /> </td> 
   <td> Right(&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rtrim</strong><br /> </td> 
   <td> 文字列の右側の空白を削除します<br /> </td> 
   <td> Rtrim(&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> 指定されたUTF8文字 <strong>列の標準SHA256</strong> ハッシュを計算します<br /> </td> 
   <td> Sha256Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> 指定されたUTF8文字 <strong>列の標準SHA384</strong> ハッシュを計算します<br /> </td> 
   <td> Sha384Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> 指定されたUTF8文字 <strong>列の標準SHA512</strong> ハッシュを計算します<br /> </td> 
   <td> Sha512Digest（&lt;文字列&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>スマート</strong><br /> </td> 
   <td> 各単語の最初の文字を大文字にして文字列を返します<br /> </td> 
   <td> Smart(&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>サブ文字列</strong><br /> </td> 
   <td> 文字列の n1 文字目から始まる長さ n2 文字の部分文字列を抽出します<br /> </td> 
   <td> Substring(&lt;文字列&gt;, &lt;オフセット&gt;, &lt;長さ&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToIntlString</strong><br /> </td> 
   <td> 数値を文字列に変換します<br /> </td> 
   <td> ToIntlString（&lt;数値&gt;）<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToString</strong><br /> </td> 
   <td> 数値を文字列に変換します<br /> </td> 
   <td> ToString(&lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Upper</strong><br /> </td> 
   <td> 文字列を大文字で返します<br /> </td> 
   <td> Upper(&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLink</strong><br /> </td> 
   <td> 他の 2 つのパラメーターが等しい場合に、パラメーターとして渡されたリンクの外部キーを返します<br /> </td> 
   <td> VirtualLink(&lt;数値&gt;, &lt;数値&gt;, &lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLinkStr</strong><br /> </td> 
   <td> 他の 2 つのパラメーターが等しい場合に、パラメーターとして渡されたリンクの外部（テキスト）キーを返します<br /> </td> 
   <td> VirtualLinkStr(&lt;文字列&gt;, &lt;数値&gt;, &lt;数値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcDecrypt</strong><br /> </td> 
   <td> 暗号化された値を16進数形式（2番目のパラメーター）で<strong>x</strong>(x)プレフィックスを付け、初期化ベクトルを16進数形式（3番目のパラメーター）で復号します。<br /> </td> 
   <td> encryption_aescbcDecrypt(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcEncrypt</strong><br /> </td> 
   <td> AESアルゴリズム（CBCブロックモード）を使用して暗号化します。文字列（第1パラメータ）とキー（第2パラメータ）および初期化ベクトル（第3パラメータ）を使用します。 キーと初期化ベクトルは、( <strong>\x</strong>)16進数で示す必要があります。 結果は、 <strong>\xを含まない16進数で表されます</strong>。<br /> キーサイズは128ビット、192ビット、256ビット（16、24、32文字の16進数）でもかまいませんが、キーと同じ長さのランダム化IVを使用することをお勧めします。<br /> </td> 
   <td> encryption_aescbcEncrypt(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> 。例：encryption_aescbcEncrypt(johndoe@example.com, "<strong>\x0123456789ABCDEF0123456789ABCDEF</strong>", "<strong>\x0123456789ABCDEFFba9876543210</strong>”)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 集計 {#aggregates}

集計関数は、ワークフローのアクティビティ [から追加のデータを](../../automating/using/query.md#enriching-data) 追加する場合にのみ使用で **[!UICONTROL Query]** きます。

集計関数は、値のセットに対して計算を実行するために使用されます。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名前</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Avg</strong>、Average<br /> </td> 
   <td> 数値列の平均を返します。<br /> </td> 
   <td> Avg(&lt;値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Count</strong>、Count（NULLを除く）<br /> </td> 
   <td> Counts the non-null values in a column.<br /> </td> 
   <td> Count(&lt;値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>CountAll</strong>、Count all<br /> </td> 
   <td> すべての値（null値と重複を含む）をカウントします。<br /> </td> 
   <td> CountAll()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Countdistinct</strong>, Distinct count<br /> </td> 
   <td> 列内のnull以外の個別の値をカウントします。<br /> </td> 
   <td> Countdistinct(&lt;値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最大</strong>、最大<br /> </td> 
   <td> 数値、文字列、または日付列の最大値を返します。<br /> </td> 
   <td> Max(&lt;値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最小</strong>、最小<br /> </td> 
   <td> 数値、文字列、または日付列の最小値を返します。<br /> </td> 
   <td> Min(&lt;値&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sum</strong>、Sum<br /> </td> 
   <td> 数値列の値の合計を返します。<br /> </td> 
   <td> Sum(&lt;値&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 表示域 {#representation}

表現関数は、値の順序付けに使用されます。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名前</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Desc</strong><br /> </td> 
   <td> 降順ソートを適用します<br /> </td> 
   <td> Desc(&lt;値 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>OrderBy</strong><br /> </td> 
   <td> パーティション内の結果を並べ替えます<br /> </td> 
   <td> OrderBy(&lt;値 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>PartitionBy</strong><br /> </td> 
   <td> テーブルのクエリの結果を区分します<br /> </td> 
   <td> PartitionBy(&lt;値 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowNum</strong><br /> </td> 
   <td> テーブルのパーティションと並べ替えシーケンスに基づいてライン番号を生成しますこの関数はMySQLではサポートされていません<br /> </td> 
   <td> RowNum(PartitionBy(&lt;値 1&gt;), OrderBy(&lt;値 1&gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>


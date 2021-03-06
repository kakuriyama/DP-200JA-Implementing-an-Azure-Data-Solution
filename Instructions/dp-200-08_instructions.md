﻿---
lab:
    title: 'Azure データ プラットフォームの保護'
    module: 'モジュール 8: Azure データ プラットフォームの保護'
---

# DP 200 - データ プラットフォーム ソリューションの実装
# ラボ 8 - Azure データ プラットフォームの保護

**所要時間**: 75 分

**前提条件**: このラボのケース スタディは既に確認していることを前提としています。本ラボは、モジュール 1 から 7 の内容と演習が完了したことを前提としています。

**ラボ ファイル**: このラボのファイルは、_Allfiles\Labfiles\Starter\DP-200.8_のフォルダーにあります。

## ラボの概要

受講者は、多重防御を提供するために講じることできるさまざまなセキュリティ手段を説明し、文書化することができるようになります。これには、本コースでこれまでに設定されたセキュリティの受講者による文書化が含まれます。また、AdventureWorks 内に存在する可能性のあるセキュリティのギャップの識別方法も学びます。

## ラボの目的
  
この課題を完了すると、次のことができるようになります。

1. セキュリティの説明
1. 主要なセキュリティ コンポーネントの説明
1. ストレージ アカウントと Data Lake Storage のセキュリティ保護
1. データ ストアのセキュリティ保護
1. ストリーミング データのセキュリティ保護

## シナリオ
  
あなたは、AdventureWorks のシニア データ エンジニアとして、顧客のデータ エステートが確実に保護されていることを確認する責任があります。必要な場所にセキュリティを確実に配置していることを確認するために、現在のインフラストラクチャのセキュリティ チェックを実行しています。このチェックは、これまでに作成したすべてのサービスとデータの全体的なチェックと、セキュリティの構成に存在する可能性のあるギャップの識別を目的としています。 

また、あなたは SQL Database DeptDatabasesxx のセキュリティを強化するよう要求され、データベースへのアクセスを監視できるように、データベースに対する監査のセットアップを求められています。さらに、イベント ハブの管理アクセス許可が十分に制限されていないことを知り、このアクセス許可を削除したいと思っています。

このラボを完了すると:

1. セキュリティの説明
1. 主要なセキュリティ コンポーネントを説明しました
1. ストレージ アカウントと Data Lake Storage のセキュリティ保護
1. セキュリティで保護されたデータ ストア
1. ストリーミング データのセキュリティ保護

> **重要**: このラボを進めるにつれ、プロビジョニングまたは構成タスクで発生した問題を書き留め、_\Labfiles\DP-200-Issues-Docx_にあるドキュメントの表に記録してください。ラボ番号を文書化し、テクノロジーを書き留め、問題とその解決を説明してください。このドキュメントは、後のモジュールで参照できるように保存します。

## エクササイズ 1: セキュリティの概要

所要時間: 15 分

グループ エクササイズ
  
このエクササイズの主なタスクは次のようになります。

1. 階層化したアプローチとしてのセキュリティ。

1. 講師は、発見内容についてグループと話し合います。

### タスク 1: 階層化アプローチとしてのセキュリティ。

1. 課題の仮想マシンから、**Microsoft Word** を起動し、**Allfiles\Labfiles\Starter\DP-200.8** フォルダーからファイル  **DP-200-Lab08-Ex01.docx** を開きます。

1. コースの内容、ケース スタディ、これまでコースで取り上げられたシナリオから、グループで  **10 分間** かけて、課題で AdventureWorks を保護するためにこれまでに影響を与えたセキュリティ層を特定します。3 つの例をご覧ください。

### タスク 2: 調査結果についてインストラクターと話し合う

1. 講師は、発見内容について話し合うためにグループ作業を中断させます。

> **結果**: このエクササイズを完了すると、Adventureworks でセキュリティを実装した方法と影響を受けたセキュリティ層の少なくとも 3 つの例を含む Microsoft Word ドキュメントが作成されます。

## 実習 2: 主要なセキュリティ コンポーネント
  
所要時間: 10 分

個別エクササイズ
  
このエクササイズの主なタスクは、次のようになります。

1. データとストレージのセキュリティ衛生の評価

### タスク 1: データとストレージのセキュリティ衛生を評価する。

1. Azure portal タブで、 [**Security Center**] をクリックします。

    ![Azure portal の Security Center](Linked_Image_Files/M08-E01-T01-img01.png)

1. 「Security Center - 概要」スクリーンで、[**リソース セキュリティ衛生**] の下にある [データとストレージ] をクリックします。

    ![Security Center - Azure portal のデータ ストレージ](Linked_Image_Files/M08-E01-T01-img02.png)

1. 注意が必要な上位 2 つの主要データおよびストレージ コンポーネントを特定します。

    1. __回答は異なる場合があります_____
    1. __回答は異なる場合があります_____

> **結果**: このエクササイズを完了すると、Azure サブスクリプション内のデータとストレージのセキュリティの弱点を特定する場所を学習することができます。

## エクササイズ 3: ストレージ アカウントと Data Lake Storage のセキュリティ保護
  
所要時間: 15 分

個別実習
  
この実習の主なタスクは次のとおりです。

1. Azure BLOB に対する適切なセキュリティ アプローチの決定

1. 講師と発見内容について話し合う

### タスク 1：Azure BLOB に対する適切なセキュリティ アプローチを決定する

1. あなたは社内の Web 開発者から連絡を受け、サード パーティーの Web デザイン会社が awsastudxx ストレージ アカウントにある Web イメージへアクセスできるようにするのを支援してほしいと頼まれました。AdventureWorks のシニア データ エンジニアとして、正しいデューデリジェンスを適用しながらこれを確実に実現するには、どのような手順が必要となるでしょうか。

1. 課題の仮想マシンから **Microsoft Word** を起動し、**Allfiles\Labfiles\Starter\DP-200.8** フォルダーからファイル **DP-200-Lab08-Ex03.docx** を開きます。

### タスク 2: 発見内容について講師と話し合う

1. 講師は、発見内容について話し合うためにグループ作業を中断させます。

> **結果**: このエクササイズを完了すると、サードパーティーの Web 開発会社に BLOB ストレージ アカウントへの安全なアクセスを提供するための手順を含む Microsoft Word ドキュメントが作成されます。

## 実習 4: データ ストアのセキュリティ保護
  
所要時間: 15 分

個別エクササイズ
  
このエクササイズの主なタスク:

1. 監査の有効化

1. データベースをクエリする

1. 監査ログを表示する

### タスク 1: 監査を有効にする

1. Azure portal 内のブレードで、**[リソース グループ]**、**awrgstudxx** の順にクリックし、**awdlsstudxx** をクリックします (**xx** は自分のイニシャル) 。

1. Azure portal 内のブレードで、リソース グループをクリックしてから、awrgstudxx をクリックし、**AdventureWorksLT** をクリックします。

1. deptdatabasesxx (sqlservicexx/deptdatabasesxx) 画面で、[**監査**] ブレードをクリックします。

1. **[監査]** で、**[オン]** ボタンをクリックします。

1. [**ストレージ**] の横にあるチェックボックスを選択します。

1. [**ストレージの詳細 - 構成**] をクリックします。

1. **ストレージ設定** 画面で、**サブスクリプション - ストレージ サブスクリプションの変更** をクリックし、サブスクリプションをクリックします。

1. **ストレージ設定** 画面で、[**ストレージ設定 - 必要な設定を構成**] をクリックします。**ストレージ アカウントの選択** 画面で、**awsastudxx** をクリックします。

1. **保持日数** テキスト ボックスに **90** と入力し、**OK** をクリックします。

    ![Azure Portal でエンドポイントを構成する](Linked_Image_Files/M08-E04-T01-img01.png)

1. **[保存]** をクリックします。

### タスク 2: データベースをクエリする

1. Windows デスクトップで [**スタート**] をクリックし、「**”SQL Server”**」と入力し、[**Microsoft SQL Server Management Studio 17**] をクリックします。

1. **Connect to Server** (サーバーに接続) ダイアログ ボックスで、次の詳細情報を入力します。
    - サーバー名: **sqlservicexx.database.windows.net**
    - 認証: **SQL Server の認証**
    - ユーザー名: **xxsqladmin**
    - パスワード: **P@ssw0r**

1. [**Connect to Server**] (サーバーに接続) ダイアログ ボックスで、[**Connect**] (接続) をクリックします。 

> **注記**: パスワードが正しくないため、エラー メッセージが返されます。正しいパスワード、**P@Ssw0rd** を入力します。

1. 正しいパスワード、**P@Ssw0rd** を入力します。

1. **SQL Server Management Studio** の Object Explorer で [**AdventureWorksLT**] を展開してから、[**テーブル**] を展開します。

1. [SalesLT].[Customers] を右クリックし、**上位 1000 行の選択** をクリックします。

### タスク 2: 監査ログを表示する

1. Azure portal に戻ります。[AdventureWorksLT (sqlservicexx/AdventureWorksLT) - 監査] 画面で、[**監査ログの表示**] をクリックします。

1. **監査レコード** ログ ファイルの **失敗した認証** レコードに注意してください。[**監査レコード**] 画面を閉じます

    ![Azure portal での監査レコードの表示](Linked_Image_Files/M08-E04-T01-img02.png)

> [**結果**]: このエクササイズを完了すると、データベース監査を有効にし、監査が機能することを確認することができます。

## エクササイズ 5: ストリーミング データのセキュリティ保護
  
予想時間: 15 分

個別エクササイズ
  
このエクササイズの主なタスク:

1. イベント ハブのアクセス許可を変更する

### タスク 1: イベント ハブのアクセス許可を変更する

1. Azure portal 内のブレードで、**Resource groups** (リソース グループ) をクリックし、**awrgstudxx** をクリックし、**xx-phoneanalysis-ehn** をクリックします。**xx** がイニシャルとなります。

1. Azure portal の **xx-phoneanalysis-ehn** では、**xx** が自分のイニシャルとなります。ウィンドウの一番下までスクロールし、**xx-phoneanalysis-eh** イベント ハブをクリックします。

1. イベント ハブへのアクセスを許可するには、**Shared access policies** (共有アクセス ポリシー) をクリックする。

1. [**socialtwitter-eh - Shared アクセス ポリシー**] スクリーンで、[**socialtwitter-eh-sap**] をクリックします。

1. アクセス許可を **管理** の横にあるチェックボックスをオンにして削除し、**保存** をクリックする。

1. Azure portalのブレードで、**ホーム** をクリックする。

> **結果**: この演習を完了した後、イベント ハブ共有アクセス ポリシーのセキュリティを変更した。